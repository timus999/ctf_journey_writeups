**n-bit security** means a cryptographic system requires approximately $2^n$ operations for an attacker to break it, typically through brute force.  It measures the system's strength, allowing comparison across different algorithms. 

For symmetric ciphers like AES, the security level usually equals the key size (e.g., AES-128 offers 128-bit security). For hash functions, collision resistance is $n/2$ bits due to the birthday attack (e.g., SHA-256 has 128-bit collision resistance). In asymmetric cryptography, key sizes are much larger for equivalent security (e.g., a 3072-bit RSA key ≈ 128-bit security). 

This logarithmic scale means each additional bit doubles the attacker's effort.