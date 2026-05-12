**Entropy**, in the context of cryptography and information theory, is a **measure of randomness or uncertainty** in data.  It quantifies how unpredictable a piece of information—such as a cryptographic key or password is to an attacker. The higher the entropy, the harder it is to guess or reproduce the data through brute force. 

Mathematically, entropy is defined using **Shannon's formula**:

H=−∑i​P(xi​)log2​P(xi​)

where $H$ is the entropy in **bits**, and $P(x_i)$ is the probability of a specific outcome $x_i$.  For example, a fair coin flip has 1 bit of entropy because there are two equally likely outcomes.

In cryptography:

- High entropy is essential for **secure key generation**.  A 128-bit key with full entropy has $2^{128}$ possible values, making brute-force attacks infeasible.
    
- Low entropy leads to **predictable keys**, as seen in vulnerabilities like the 2008 Debian OpenSSL flaw, where poor entropy resulted in weak SSH keys. 
    
- Entropy is gathered from **unpredictable physical or system events**, such as mouse movements, hardware noise, or quantum effects, and is often pooled in operating systems (e.g., `/dev/random` on Linux). 
    

Without sufficient entropy, even strong cryptographic algorithms become vulnerable, as the security of the system collapses at its weakest point—the key.