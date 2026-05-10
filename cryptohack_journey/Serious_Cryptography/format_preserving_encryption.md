**Format-preserving encryption (FPE)** is a cryptographic method that encrypts data while maintaining the same format (e.g., length, character set) as the original plaintext.  For example, encrypting a 16-digit credit card number results in another 16-digit number, and an email address remains in a valid email format after encryption. 

### Key Features

- **Format Retention**: Output matches input format—ideal for structured data like SSNs, phone numbers, or dates. 
    
- **Field-Level Security**: Enables encryption of specific database fields without altering schema or breaking applications. 
    
- **Deterministic Encryption**: Same input always produces the same ciphertext, supporting referential integrity and indexing. 
    
- **Standards-Based**: Uses NIST-approved modes like **FF1** and **FF3** (from SP 800-38G) based on AES. 
    

### Uses

- **Legacy System Integration**: Apply encryption without modifying applications that expect fixed formats. 
    
- **Compliance**: Helps meet **PCI DSS**, **HIPAA**, and **GDPR** requirements by securing PII/PHI while preserving usability. 
    
- **Secure Testing**: Generate realistic but protected data for development and analytics. 
    
- **Tokenization Alternative**: Replaces sensitive values with encrypted tokens that retain format (e.g., vaultless tokenization). 
    

FPE enables strong security with minimal system disruption, making it ideal for financial, healthcare, and enterprise environments