Learning from start. 

Revising Python

### Ascii

chr() - convert an ASCII ordinal number to a character
ord() - convert a character to an ASCII ordinal number

### Hex

bytes.fromhex() - convert hex to bytes
.hex() - (called on byte strings) gets hex representations

### Base64

we need to first import base64 module

import base64

base64.b64endcode() 


### Bytes and Big Integers

PyCryptodome library's bytes_to_long() and long_to_bytes() helps to take the ordinal bytes of the message, convert them into hexadecimal and concatenate.

### XOR Starter

pwntools library has a xor() function

### XOR Properties

Commutative: A ^ B = B ^ A
Associative: A ^ ( B ^ C ) = ( A ^ B ) ^ C
Identity: A ^ 0 = A
Self-Inverse: A ^ A = 0