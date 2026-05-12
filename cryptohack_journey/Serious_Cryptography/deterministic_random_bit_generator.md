A **Deterministic Random Bit Generator (DRBG)** is a **cryptographically secure algorithm** that produces a long sequence of pseudorandom bits from a short, secret seed.  It is deterministic because the same seed will always generate the same output sequence. 

DRBGs are a type of **Cryptographically Secure Pseudorandom Number Generator (CSPRNG)** standardized by **NIST SP 800-90A**.  They are not sources of entropy themselves but are used to _expand_ and _condition_ high-entropy input (from a true random source) into a large volume of unpredictable output suitable for cryptographic use, such as generating keys, nonces, and salts. 

NIST specifies three approved DRBG constructions:

1. **Hash_DRBG**: Based on cryptographic hash functions (e.g., SHA-2). 
    
2. **HMAC_DRBG**: Based on the HMAC (Hash-based Message Authentication Code) construction. 
    
3. **CTR_DRBG**: Based on block ciphers (e.g., AES) in counter mode. 
    

A critical requirement for a DRBG is **unpredictability**: even if an attacker knows the algorithm and observes some of the output, they cannot predict previous or future bits without knowing the secret seed. DRBGs are fundamental components in secure systems, including operating system random number generators like `/dev/urandom`.