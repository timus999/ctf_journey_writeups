A **one-time pad (OTP)** is an encryption method that is mathematically proven to be unbreakable when used correctly.  It works by combining a plaintext message with a **random secret key** (the "pad") that is:

- **At least as long as the message**
    
- **Truly random**
    
- **Used only once**
    
- **Kept completely secret**
    

Each bit or character of the plaintext is encrypted using modular addition or XOR with the corresponding bit or character from the key. 

### Why It’s Unbreakable

If the key meets all conditions, the resulting ciphertext provides **perfect secrecy**—an attacker gains no information about the plaintext, even with infinite computing power.  Any plaintext of the same length could produce the same ciphertext with a different key, making decryption impossible without the exact key. 

### Uses and Limitations

- **Historical Use**: Widely used in espionage and diplomatic communications (e.g., Cold War-era KGB). 
    
- **Modern Relevance**: Impractical for most digital applications due to key distribution and generation challenges. 
    
- **Legacy**: Inspires secure communication principles and quantum key distribution (QKD).
    

Despite its theoretical perfection, the difficulty of securely generating, sharing, and destroying keys limits its use today.