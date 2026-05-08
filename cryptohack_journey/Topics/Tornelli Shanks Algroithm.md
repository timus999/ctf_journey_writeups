
## Goal

We want to solve:

### $x^2$ $\equiv$ n (mod p)

where:
- (p) is an odd prime
- (n) is a quadratic residue modulo (p)

In simple words:

> We want to find the square root of (n) modulo (p).

---

# Why do we need Tonelli–Shanks?

When:

### p $\equiv$ 3 (mod 4)


there is an easy shortcut:


### x $\equiv$ $n^{\frac{p+1}{4}}$ (mod p)


But when:
### p $\equiv$ 1 (mod 4)

that shortcut breaks.

Example:

p = 13

Then:
### $\frac{p+1}{4}$ = $\frac{14}{4}$ = 3.5

not an integer.

So we need a more general algorithm.

That algorithm is Tonelli–Shanks.

---

# Big Picture Intuition

Tonelli–Shanks works by:

1. Splitting:

### p-1 = q$2^s$

where:
- (q) is odd
- all powers of 2 are separated out

2. Using powers of two to gradually “fix” the exponent until we obtain a square root.

The algorithm repeatedly removes errors caused by powers of 2.

---

# Step 1 — Factor p−1

Write:

p-1 = q$2^s$

with \(q\) odd.

Example:

p = 13

Then:

p-1 = 12 = 3 $\cdot$ $2^2$

So:

q=3,$\quad$ s=2


---

# Step 2 — Find a quadratic non-residue

We need some number \(z\) such that:

### $\left(\frac{z}{p}\right)$=-1

Meaning:
- \(z\) has NO square root modulo \(p\)

Example modulo 13:

Squares mod 13:

1,4,9,3,12,10

So 2 is NOT there.

Thus:

z=2

is a quadratic non-residue.

---

# Step 3 — Initialize variables

Set:

### c=$z^q$ (mod p)

### t=$n^q$ (mod p)

### r=$n^{\frac{q+1}{2}}$ (mod p)

### m=s

The important invariant is:


### $r^2$ $\equiv$ nt (mod p)


We will repeatedly modify \(t\) until:

### t=1

At that point:

### $r^2$ $\equiv$ n

and \(r\) becomes the square root.

---

# Why does the invariant hold?

Initially:
### r=$n^{\frac{q+1}{2}}$

Squaring:

### $r^2$ = $n^{q+1}$

Factor:

### $r^2$ = n $\cdot$ $n^q$

But:

### t=$n^q$

So:

$r^2$ $\equiv$ nt (mod p)

This relationship stays true during the entire algorithm.

---

# Step 4 — Why does t matter?

Because:
### $t^{2^{s}}4 $\equiv$ 1 (mod p)

So \(t\) lies inside a subgroup whose order is a power of 2.

Tonelli–Shanks repeatedly reduces that order.

Eventually:

### t=1

and then:

### $r^2$ $\equiv$ n


---

# Main Loop

If:

### t=1

we are done.

Otherwise:

Find smallest \(i\) such that:

### $t^{2^i}$ $\equiv$ 1 (mod p)

Then define:

### b=$c^{2^{m-i-1}}$

Update:

### r $\leftarrow$ rb

### t $\leftarrow$ t$b^2$

### c $\leftarrow$ $b^2$

### m $\leftarrow$ i

This reduces the order of \(t\).

Eventually:
### t=1

---

# Why does this work?

This is the heart of the algorithm.

---

## Key Idea: powers of 2

The multiplicative group modulo prime \(p\):


### $(\mathbb Z/p\mathbb Z)^*$

has order:

### p-1=q$2^s$

The algorithm isolates the:
### $2^s$

part.

That means every relevant element has order:

### $2^k$

for some \(k\).

Tonelli–Shanks repeatedly halves this order.

---

# Why choose b this way?

We choose:

### b=$c^{2^{m-i-1}}$

because it creates exactly the correction needed to reduce the order of \(t\).

In fact:
### $b^2$

has the same highest-order power-of-two behavior as \(t\), allowing cancellation.

After update:
### t $\leftarrow tb^2$

its order becomes smaller.

---

# Why does it terminate?

At each iteration:
- the order of \(t\) strictly decreases
- powers of two cannot decrease forever

So eventually:
### t=1

and algorithm stops.

---

# Complete Python Implementation

```python
def legendre_symbol(a, p):
    ls = pow(a, (p - 1) // 2, p)
    return -1 if ls == p - 1 else ls


def tonelli_shanks(n, p):
    if legendre_symbol(n, p) != 1:
        return None

    if p % 4 == 3:
        return pow(n, (p + 1) // 4, p)

    # Factor p-1 = q * 2^s
    q = p - 1
    s = 0

    while q % 2 == 0:
        s += 1
        q //= 2

    # Find quadratic non-residue z
    z = 2
    while legendre_symbol(z, p) != -1:
        z += 1

    m = s
    c = pow(z, q, p)
    t = pow(n, q, p)
    r = pow(n, (q + 1) // 2, p)

    while t != 1:
        i = 1
        temp = pow(t, 2, p)

        while temp != 1:
            temp = pow(temp, 2, p)
            i += 1

        b = pow(c, 2 ** (m - i - 1), p)

        r = (r * b) % p
        t = (t * b * b) % p
        c = (b * b) % p
        m = i

    return r


p = 13
n = 10

x = tonelli_shanks(n, p)

print(x)
print((x * x) % p)
```

# Example

Solve:

### $x^2≡10(mod13)$ 

The algorithm returns:
### x=6  

Check:

### $6^2=36≡10(mod13)$ 

The second root is:
### 13−6=7  

because:
### $7^2=49≡10(mod13)$  

---

# Core Intuition To Remember

Tonelli–Shanks:

1. Separates the power-of-two structure of:
	**p - 1**
2. Uses a quadratic non-residue as a correction tool
3. Gradually forces:

	**t→1**

4. Once:

	**t=1**  

we get:
### $r^2 \equiv n$  

and have the square root.

---

# Important Connection To Cryptography

Tonelli–Shanks appears in:

- Elliptic curve cryptography
- Rabin cryptosystem
- Zero-knowledge proofs
- Quadratic residue problems
- CTF crypto challenges

Especially when:
### $p\equiv 1 (mod 4)$  

where the simple shortcut does not work.

---


