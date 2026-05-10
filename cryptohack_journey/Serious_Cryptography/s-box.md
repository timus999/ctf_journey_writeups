An **S-box (substitution box)** is a fundamental nonlinear component in symmetric-key block ciphers that performs substitution to introduce **confusion**, a principle defined by Claude Shannon.  It maps a fixed number of input bits to output bits using a lookup table, obscuring the relationship between the **plaintext**, **ciphertext**, and **key**. 

### Properties

- S-box can have different number of inputs and outputs.

- Basic components of symmetric key algorithms which performs substitution.

- It can be keyed or keyless, but modern block ciphers normally use keyless.

- It is used as an intermediate stage of encryption and decryption.

### How S-Boxes Work

- An **m×n S-box** takes _m_ input bits and produces _n_ output bits (often m=n for bijectivity). 
    
- Implemented as a **lookup table** with 2m entries of _n_ bits each. 
    
- Example: In DES, a 6-to-4-bit S-box uses outer bits to select a row and inner bits to select a column in a 4×16 table. 
    

### How S-Boxes Are Determined/Designed

S-boxes are carefully designed to meet cryptographic criteria:

1. **Nonlinearity**: Prevents linear cryptanalysis by minimizing correlation between input and output bits (measured via **Linear Approximation Table - LAT**). 
    
2. **Low Differential Uniformity**: Resists differential cryptanalysis by minimizing predictable input-output differences (measured via **Difference Distribution Table - DDT**). 
    
3. **Strict Avalanche Criterion (SAC)**: Flipping one input bit changes ~50% of output bits on average. 
    
4. **Bijectivity**: Ensures one-to-one mapping for invertibility (required for decryption). 
    
5. **Balancedness**: Output bits have equal probability of being 0 or 1. 
    

Design methods include:

- **Algebraic constructions**: e.g., AES S-box uses multiplicative inverse in GF(28) + affine transformation. 
    
- **Chaotic systems**: e.g., logistic maps generate dynamic S-boxes. 
    
- **Key-dependent generation**: e.g., Blowfish creates S-boxes from the encryption key. 
    

### Uses of S-Boxes

- **Block Ciphers**: Core of substitution layers in AES, DES, Twofish. 
    
- **Stream Ciphers**: RC4 uses a dynamic 256-byte S-box for keystream generation. 
    
- **Hash Functions**: SHA variants use S-boxes to enhance diffusion and avalanche effect. 
    
- **Lightweight Cryptography**: Compact 4-bit S-boxes used in IoT ciphers like PRESENT.