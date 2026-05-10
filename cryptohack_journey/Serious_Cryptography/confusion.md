
- **Purpose**: Obscure the relationship between the **ciphertext** and the **key**. 
    
- **Mechanism**: Achieved primarily through **substitution** (e.g., S-boxes in AES or DES). 
    
- **Effect**: If a single bit of the key changes, most or all bits of the ciphertext should change unpredictably. 
    
- **Used in**: Both **block ciphers** and **stream ciphers**.
    

> Example: In AES, non-linear S-boxes introduce confusion by making ciphertext bits depend on multiple key bits in a complex way.

### Key Differences between Confusion and Diffusion

| Aspect               | Confusion                             | Diffusion                                   |
| -------------------- | ------------------------------------- | ------------------------------------------- |
| **Goal**             | Hide key-ciphertext relationship      | Hide plaintext-ciphertext relationship      |
| **Method**           | Substitution (S-boxes)                | Permutation (P-boxes, MixColumns)           |
| **Ciphers**          | Block & stream                        | Mainly block                                |
| **Effect of change** | Key bit → many ciphertext bits change | Plaintext bit → many ciphertext bits change |
