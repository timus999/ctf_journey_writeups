**Semantic security (IND-CPA)** means that an encryption scheme is secure against a chosen-plaintext attacker who cannot learn any partial information about the plaintext from the ciphertext. 

Formally, it is defined through an experiment where:

- An adversary chooses two plaintexts m0​ and m1​.
    
- The challenger encrypts one of them (based on a random bit b ) and returns the ciphertext.
    
- The adversary must guess which plaintext was encrypted. 
    

The scheme is **IND-CPA secure** if the adversary’s success probability is only negligibly better than random guessing (i.e., 21​ ). 

This notion, introduced by Shafi Goldwasser and Silvio Micali, ensures that even if an attacker can encrypt arbitrary messages, they gain no meaningful information from observing ciphertexts. 

IND-CPA is equivalent to **semantic security** and requires **randomized encryption** (e.g., using an IV or nonce), ruling out deterministic schemes like textbook RSA.