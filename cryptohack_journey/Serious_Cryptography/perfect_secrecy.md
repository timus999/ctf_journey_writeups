**Perfect secrecy** is a cryptographic property where a ciphertext reveals _no information_ about the plaintext, even to an attacker with unlimited computational power.  Formally, it means the probability distribution of the plaintext remains unchanged before and after observing the ciphertext:

P(M=m∣C=c)=P(M=m)

This concept was defined by Claude Shannon and ensures that an adversary gains zero knowledge about the message from the ciphertext alone. 

### Key Points

- **Unbreakable**: Even with infinite resources, an attacker cannot determine the original message. 
    
- **One-Time Pad (OTP)**: The only practical example, requiring a key that is:
    
    - As long as the message
        
    - Truly random
        
    - Used only once
        
    - Kept secret
        
- **Impractical for most uses**: Due to key size and secure distribution challenges. 
    

Perfect secrecy is the strongest form of security in cryptography, forming the foundation of information-theoretic security.