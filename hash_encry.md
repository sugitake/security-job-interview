# Difference between Hash, Encryption

## Hash
Hashing is the process mapping any arbitrary size data into a fixed-length value using a hash function. Hashing has following features:
1. A given known input must always produce one known output
2. Once hashing has been done, it should be impossible to go from the output to the input
3. Defferent multiple inputs should given a different output
4. Modifying an input should mean a change in the hash.

### Protocols
1. MD4
   MD4 has a length of 128bit. The security of this algorithm has been criticized.
2. SHA-1
   This stands for Secure Hash Algorithm. This has a length of 160 bit. This algorithm is also criticized and recommended not to use.
3. SHA-2
   SHA-2 has a length of 256bit.

## Usase
There are some use case of hashing algorithms.
- Ensure data integrity
- Secure against unauthorized modifications
- Protect stored passwords
- Operate at different speeds to suit different purpose

## Encryption
Data encryption is the process that translates the data from its original form to another form. The main purpose of encryption data is to protect data confidentiality thile it is stored on computer systems or transmitted to other computers over the network.

## Defference between hashing and encryption
Hash is used to validate the integrity of the content by detecting all modifications and thereafter changes to a hash output.Encryption encodes data for the primary purpose of maintaining data confidentiality and security. It requires a private key to reversible function encrypted text to plain text.


# References
1. https://www.ssl2buy.com/wiki/difference-between-hashing-and-encryption
2. https://www.baeldung.com/cs/hashing-vs-encryption