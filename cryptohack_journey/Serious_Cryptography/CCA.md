A **chosen-ciphertext attacker** is an adversary who can select arbitrary ciphertexts and obtain their corresponding plaintexts by querying a **decryption oracle** typically a system or device that performs decryption without revealing the key.  The goal is to use these plaintext-ciphertext pairs to recover the secret key or decrypt other ciphertexts of interest. 

### Key Features

- **Active Attack**: Unlike passive eavesdropping, the attacker actively submits crafted ciphertexts. 
    
- **Adaptive vs. Non-Adaptive**:
    
    - **CCA1 (Lunchtime attack)**: The attacker can query the oracle only before receiving a challenge ciphertext.
        
    - **CCA2 (Adaptive CCA)**: The attacker can make queries both before and after seeing the challenge ciphertext (except querying the challenge itself), making it a stronger model. 
        
- **Security Notion**: A scheme secure under CCA2 satisfies **IND-CCA2** (indistinguishability under adaptive chosen-ciphertext attack), the gold standard for encryption security. 
    

### Real-World Relevance

- Public-key systems like RSA are especially vulnerable if not properly padded (e.g., the **Bleichenbacher attack** on PKCS#1). 
    
- Secure protocols (e.g., TLS) use CCA-secure schemes such as **RSA-OAEP** or **authenticated encryption** (e.g., GCM mode). 
    

Modern cryptography requires resistance to chosen-ciphertext attacks to ensure security in realistic, adversarial environments.