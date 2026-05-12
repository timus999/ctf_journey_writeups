An **entropy pool** is a reservoir of randomness maintained by an operating system to supply high-quality, unpredictable data for cryptographic operations.  It collects environmental noise from various hardware and system events such as keyboard timings, mouse movements, disk I/O, network activity, and hardware interrupts and uses this data to seed **cryptographically secure pseudorandom number generators (CSPRNGs)**. 

The collected entropy is mixed using cryptographic hash functions (like SHA-256) or stream ciphers (like ChaCha20) to eliminate bias and ensure uniform distribution. The system estimates the amount of available entropy in bits, which can be checked on Linux via:

```
cat /proc/sys/kernel/random/entropy_avail
```

A typical pool size is 4096 bits. Devices like `/dev/random` may block if entropy is low, waiting for more randomness, while `/dev/urandom` uses a CSPRNG to stretch existing entropy and never blocks, making it suitable for most cryptographic needs. 

Modern systems (e.g., Linux 5.6+) use hybrid designs that continuously reseed the generator, ensuring long-term security even if initial entropy is limited