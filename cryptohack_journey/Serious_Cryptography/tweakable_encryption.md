**Tweakable encryption** is a form of block cipher encryption that includes an additional input called a **tweak**, which modifies how the data is encrypted without changing the secret key. 

The tweak is typically **non-secret** and can be public, like a counter, sector number, or timestamp.  Using the same key but a different tweak produces a different ciphertext, even for identical plaintexts. 

### Why It’s Useful

- **Avoids Interoperability**: Ensures encrypted session tokens can't be used as password reset tokens, even with the same key. 
    
- **Disk Encryption**: Each disk block uses its block index as the tweak—same content encrypts differently, yet blocks remain same size and independently accessible. 
    
- **Efficiency**: Changing the tweak is faster than rekeying, which often involves expensive key setup (e.g., in AES). 
    
- **Security**: Prevents pattern leakage when encrypting repeated data.
    

### Example

In **XTS mode** (used for full-disk encryption), the block index serves as the tweak.  This allows secure, random-access encryption of storage devices.

Unlike initialization vectors (IVs), tweaks don’t need to be stored separately in many cases, and they enable deterministic, format-preserving encryption.