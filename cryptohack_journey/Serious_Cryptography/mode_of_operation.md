A **mode of operation** is a method that defines how a block cipher encrypts data larger than a single block.  Since block ciphers like AES or DES only encrypt fixed-size blocks (e.g., 128 or 64 bits), modes of operation allow secure encryption of messages of arbitrary length by applying the cipher repeatedly. 

### Common Modes

- **ECB (Electronic Codebook)**: Each block is encrypted independently. Weak because identical plaintext blocks produce identical ciphertext. 
    
- **CBC (Cipher Block Chaining)**: Each plaintext block is XORed with the previous ciphertext block before encryption. Requires an **initialization vector (IV)**. 
    
- **CTR (Counter)**: Turns the block cipher into a stream cipher by encrypting a counter value and XORing it with plaintext. Allows parallel encryption. 
    
- **GCM (Galois/Counter Mode)**: Combines CTR mode with authentication, providing both **confidentiality and integrity** (AEAD). 
    
- **CFB/OFB**: Stream cipher modes that use feedback mechanisms to generate keystreams. 
    

### Significance

- Ensures **security** and **diffusion** across multiple blocks. 
    
- Prevents patterns in plaintext from leaking into ciphertext.
    
- Some modes (like GCM) provide **authenticated encryption**, protecting against tampering. 
    

Modes are standardized by organizations like NIST and are essential for real-world cryptographic protocols like TLS, disk encryption, and secure messaging.