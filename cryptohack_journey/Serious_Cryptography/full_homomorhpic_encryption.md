**Fully homomorphic encryption (FHE)** is a cryptographic system that allows arbitrary computations to be performed on encrypted data without decrypting it.  The result of the computation remains encrypted and, when decrypted, matches the result of the same operations performed on the plaintext. 

FHE supports both **addition** and **multiplication** operations on ciphertexts, enabling the evaluation of complex functions (e.g., machine learning models or database queries) while preserving data confidentiality. 

### Key Features

- **End-to-End Privacy**: Data stays encrypted during storage, transmission, and _processing_—ideal for cloud computing and AI.
    
- **Unbounded Computation**: Unlike partially or somewhat homomorphic schemes, FHE allows unlimited operations of any type. 
    
- **Quantum Resistance**: Most FHE schemes are based on **lattice cryptography**, making them candidates for post-quantum security. 
    

### How It Works

- Based on mathematical problems like **Learning With Errors (LWE)**. 
    
- Uses a **bootstrapping** technique to refresh ciphertexts and control noise growth during computations. 
    
- Enables secure outsourcing: a client encrypts data, sends it to a server, which computes on it and returns encrypted results. 
    

### Use Cases

- Secure medical data analysis
    
- Private AI inference
    
- Confidential financial computations
    
- Blockchain and smart contract privacy 
    

Despite high computational overhead, advances in algorithms and hardware are making FHE increasingly practical.