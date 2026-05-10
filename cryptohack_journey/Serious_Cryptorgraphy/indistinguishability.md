**Indistinguishability** in cryptography means that an adversary cannot distinguish between two ciphertexts or cryptographic objects, even when given access to encryption or decryption oracles.  It ensures that encrypted data reveals no information about the underlying plaintext. 

Formally, a scheme has **indistinguishability under chosen-plaintext attack (IND-CPA)** if, given two plaintexts and a ciphertext of one of them, an adversary cannot guess which plaintext was encrypted with probability significantly better than random (i.e., 1/2). 

Stronger variants include:

- **IND-CCA1** (under non-adaptive chosen-ciphertext attack)
    
- **IND-CCA2** (under adaptive chosen-ciphertext attack), the strongest form. 
    

Indistinguishability is equivalent to **semantic security** and is a standard requirement for secure encryption schemes like AES in secure modes (e.g., GCM).