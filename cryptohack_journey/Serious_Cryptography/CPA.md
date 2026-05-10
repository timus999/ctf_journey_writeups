A **chosen-plaintext attacker** is an adversary who can select arbitrary plaintexts and obtain their corresponding ciphertexts using the target encryption system.  The goal is to analyze these plaintext-ciphertext pairs to recover the secret key or gain information about the encryption scheme. 

### Key Characteristics

- **Encryption Oracle Access**: The attacker interacts with an encryption oracle (e.g., a device or service) that encrypts chosen messages without revealing the key. 
    
- **Two Variants**:
    
    - **Batch CPA**: All plaintexts are chosen before seeing any ciphertexts.
        
    - **Adaptive CPA**: The attacker chooses subsequent plaintexts based on previous ciphertexts, increasing attack power. 
        
- **Stronger Than Known-Plaintext Attack**: Since the attacker can strategically pick inputs (e.g., all zeros, repeated patterns), it's more effective than passively observing random plaintext-ciphertext pairs. 
    

### Relevance

- Critical in **public-key cryptography**, where the encryption key is public, allowing anyone to encrypt arbitrary messages. 
    
- Used to evaluate **security definitions** like **IND-CPA** (indistinguishability under chosen-plaintext attack), a standard for secure encryption schemes. 
    
- Real-world examples include WWII cryptanalysis of Enigma, where Allied forces planted known messages to observe encrypted outputs. 
    

Modern ciphers like AES in secure modes (e.g., GCM) are designed to be resistant to such attacks.