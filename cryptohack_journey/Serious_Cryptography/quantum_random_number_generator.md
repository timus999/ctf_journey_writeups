A **Quantum Random Number Generator (QRNG)** is a hardware device that produces **true random numbers** by measuring unpredictable quantum phenomena.  Unlike classical pseudorandom generators, which rely on deterministic algorithms and can be predicted if the seed is known, QRNGs exploit the **inherent randomness** of quantum mechanics. 

The most common method involves sending individual **photons** (particles of light) at a **beam splitter**.  Quantum mechanics dictates that each photon exists in a **superposition** of states simultaneously passing through and reflecting until it is measured.  At the moment of measurement, the photon "collapses" randomly into one state or the other, with exactly 50% probability. Detectors record this outcome as a 0 or 1, generating a truly random bit. 

Other quantum processes used include:

- **Vacuum fluctuations**: Measuring random quantum noise in empty space. 
    
- **Photon polarization**: Observing the random orientation of light particles. 
    
- **Quantum entanglement**: Using correlated particles to generate randomness.
    

Because the outcome of a quantum measurement is fundamentally unpredictable—even with complete knowledge of the system QRNGs provide **information-theoretic security**.  This makes them ideal for high-security applications like **quantum key distribution (QKD)**, military communications, and next-generation cryptography, where the failure of randomness could compromise the entire system. 

While traditionally slower, modern photonic chips are making QRNGs faster and more accessible, with some already integrated into smartphones and cloud services.