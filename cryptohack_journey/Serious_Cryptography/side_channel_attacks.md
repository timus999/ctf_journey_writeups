A **side-channel attack** exploits unintended physical or behavioral information leaked during a system's operation such as **timing**, **power consumption**, **electromagnetic emissions**, or **sound** to extract sensitive data like cryptographic keys.  Instead of breaking the algorithm directly, it targets weaknesses in the implementation. 

For example:

- A **timing attack** measures how long operations take to infer secret values. 
    
- A **power analysis attack** studies power usage patterns to recover keys. 
    
- **Cache attacks** monitor memory access patterns, as seen in vulnerabilities like **Spectre** and **Meltdown**. 
    

These attacks are dangerous because they work on otherwise secure systems and can be non-invasive and hard to detect.