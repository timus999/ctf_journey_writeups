# First understand the encryption

For each bit:

```
n = pow(a, e, p)
```

So:

###  $n=a^e(mod p)$

Then:

- if bit = `1` → ciphertext = n
- if bit = `0` → ciphertext = −n mod  p

So encrypted values are either:

- **$a^e$
- or −$a^e$

---

# Key observation

The only difference is the sign.

So the challenge becomes:

> How do we distinguish:
### $a^e \quad vs \quad - a^e (mod p)$

---

# This is exactly where quadratic residues matter

- A quadratic residue stays residue when squared
- Negating may flip residue/non-residue depending on p

We need to determine whether:

$a^e$

and:

$-a^e$

have different quadratic residue properties.

---

# Important theorem

For prime p:
### $(\frac{−1}{p})= (-1)^{\frac{p-1}{2}}​$

Meaning:

- if p $\equiv$ 1 mod 4, then −1 is a quadratic residue
- if p $\equiv$ 3 mod 4, then −1 is a non-residue

---

# Check the modulus

Compute:

```
p % 4
```

For our value:
### p $\equiv$ 3 (mod 4)

This is HUGE.

Because then:

−1

is a quadratic non-residue.

---

# Why this breaks the scheme

Suppose $a^e$ is a quadratic residue.

Then:
### $-a^e = (-1)(a^e)$

Multiplying by a non-residue flips residue ↔ non-residue.

So:

- encrypted `1` values have one Legendre symbol
- encrypted `0` values have the opposite

Meaning:

> We can recover every bit just by computing Legendre symbols.

No need to know e.

---

# The attack

Use Euler criterion:
### $c^\frac{p-1}{2} (mod p)$

Result:

- 1 → quadratic residue
- p - 1 → non-residue

That directly tells us the bit.

---

# 💻 Solver Script

```python


# p = ...
# cipher = [...]


bits = ""  
  
for c in cipher:  
legendre = pow(c, (p - 1) // 2, p)  
  
if legendre == 1:  
bits += "1"  
else:  
bits += "0"  
  
# Convert bits to bytes  
flag = ""  
  
for i in range(0, len(bits), 8):  
byte = bits[i:i+8]  
flag += chr(int(byte, 2))  
  
print(flag)

```

---

# Why does this work exactly?

Because:

- $a^e$ always belongs to one residue class
- multiplying by −1 flips it

The entire encryption leaks one bit through quadratic residuosity.

---

# ⚡ Important subtlety

This attack relies on:
### $p \equiv 3 \quad(mod 4)$

If:
### $p \equiv 1 \quad (mod 4)$

then:

- −1 would itself be a residue
- multiplying by −1 would NOT flip the class
- attack breaks

---

# 🔥 What this challenge is teaching

This is basically a lesson about:

- Legendre symbols
- quadratic residues
- information leakage

The scheme tries to hide bits using sign changes,  
but modular arithmetic leaks the sign through quadratic residuosity.

This is a classic crypto mistake.