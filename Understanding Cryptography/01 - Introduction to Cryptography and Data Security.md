## Overview of Cryptography
- Cryptography is very old
	- Early examples date back to 2000 B.C.
	- Non-standard "secret" hieroglyphics used in ancient Egypt
- It has been used in many, if not most, cultures that developed written language
	- *scytale* of Sparta
	- Caesar cipher in ancient Rome

- Most General Term Is **Cryptology**
- **Cryptology** splits into two main branches
	- **Cryptography**
		- The science of secret writing with the goal of hiding the meaning of a message
	- **Cryptanalysis**
		- The science of *breaking* cryptosystems
		- Most cryptanalysis is done by by researchers in academia
		- It is of central importance to the field, as without people trying to break crypto methods, we can't really know how secure they are

### 3 Main Branches of Cryptography
1. Symmetric Ciphers
	- Two parties have an encryption and decryption method for which they share a secret key
	- All cryptography until 1976 was exclusively based on symmetric methods
	- Still in widespread use, especially for data encryption and integrity check of messages
2. Asymmetric Ciphers
	- Introduced in 1976 by Whitfield Diffie, Martin Hellman, and Ralph Merkle
	- Users have a secret key (like in symmetric cryptography) *but also a public key*
	- Used for digital signatures, key establishment, and classical data encryption
3. Protocols
	- Roughly speaking, protocols deal with the application of crypto algorithms
	- Symmetric and Asymmetric algorithms are like building blocks for creating secure applications in the real world
	- TLS scheme (used in every browser) is an example of a crypto protocol
4. Strictly speaking, hash functions form another class of algorithms, but they also share some properties with symmetric ciphers

## Symmetric Cryptography
- Also referred to as *symmetric-key,* *secret-key,* and *single-key* algorithms
- Best introduced with a simple example
	- **Alice** wants to send a message to **Bob** over an *insecure channel*
		- "Insecure channel" can be any communication link that isn't 100% secure
	- **Oscar** has access to the channel and is *eavesdropping* on communications passing through
	- **Symmetric cryptography is a powerful solution here**
		- Alice encrypts her message *x* using a symmetric algorithm
			- Yielding ciphertext *y*
		- Bob receives ciphertext *y* and decrypts the message
		- Decryption is the **inverse process of encryption**
		- If the encryption algorithm is strong enough, the message passing through the insecure channel will look like random bits to Oscar, containing no useful information
		- The encryption and decryption *algorithm* are both publicly known
			- Secret algorithms === untested algorithms
			- *The only way to make sure an algorithm is strong, is to make the algorithm public and subject it to cryptanalysis* 
				- [[01 - Introduction to Cryptography and Data Security#Cryptanalysis]]
			- The only thing that **must** be kept secret in a sound crypto system is the key
		- **The system requires a secure channel for distributing the key between Alice and Bob**
			- Once the key has been securely distributed, it can be used to secure many subsequent communications

**Important Terms:**
1. "*plaintext*" or "*cleartext*" is the unencrypted message
2. "*ciphertext*" is the encrypted message, passing through the insecure communication channel
3. "*key*" is the encryption and decryption method which converts plaintext to ciphertext and vice versa
4. "*key space*" is the set of all possible keys

## Cryptanalysis



















































