A **substitution-permutation network (SPN)** is a structure used in symmetric key block ciphers to achieve **confusion** and **diffusion**, as defined by Claude Shannon.  It processes data through multiple rounds of alternating substitution and permutation layers. 

### How SPNs Work

1. **S-boxes (Substitution Boxes)**:
    
    - Provide **confusion** by non-linearly transforming small blocks of input bits.
        
    - A good S-box ensures that changing one input bit flips approximately half the output bits (avalanche effect).
        
    - Example: AES uses a fixed 8-bit S-box. 
        
2. **P-boxes (Permutation Boxes)**:
    
    - Provide **diffusion** by rearranging or spreading bits across the block.
        
    - Output bits from one S-box are distributed to multiple S-boxes in the next round. 
        
3. **Round Keys**:
    
    - The key is expanded into multiple **round keys**, combined with the data (usually via XOR) at each round. 
        
4. **Multiple Rounds**:
    
    - The process repeats for several rounds to strengthen security.
        
    - Decryption reverses the process using inverse S-boxes, P-boxes, and round keys in reverse order. 
        

### Examples and Applications

- **AES (Rijndael)** is the most well-known SPN-based cipher.
    
- Other SPN ciphers include **PRESENT**, **Kuznyechik**, and **SHARK**. 
    

### Advantages

- High **parallelizability** due to independent S-box operations. 
    
- Simpler design and analysis compared to Feistel networks.
    
- Efficient in both **hardware** and **software**.