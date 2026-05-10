**Nonmalleability** in cryptography means that an adversary cannot modify a ciphertext in a meaningful way to produce another ciphertext that decrypts to a related plaintext. 

Formally, given a ciphertext c encrypting a message m, it should be infeasible for an attacker to generate a _different_ ciphertext c′=c such that its decryption m′ is meaningfully related to m (e.g., m′=m+1, m′=2m, etc.). 

### Key Points

- **Security Against Tampering**: Ensures encrypted data cannot be subtly altered without detection. 
    
- **Stronger Than IND-CPA**: Provides integrity-like guarantees in public-key encryption where full authenticity isn't possible without signatures. 
    
- **Equivalent to IND-CCA2 Security**: A scheme is nonmalleable if and only if it is secure under adaptive chosen-ciphertext attacks. 
    
- **Examples**:
    
    - **Malleable**: Textbook RSA, ElGamal — allow transformations like E(m)→E(mt).
        
    - **Nonmalleable**: RSA-OAEP, Cramer-Shoup — resist such manipulations. 
        

Nonmalleability is essential for secure communication in adversarial environments, preventing attacks like ciphertext injection or message alteration.