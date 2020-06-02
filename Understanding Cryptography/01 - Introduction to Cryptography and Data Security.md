[[]]
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

### Substitution Cipher

- Method for encrypting text
- Each letter gets replaced with one other letter
- Assumption is that the substitution table is chosen randomly
	- The **substitution table is the key** of this cryptosystem

#### Ways of Breaking the Cipher

- **Brute-Force / Exhaustive Key Search**
	- Attacker has the ciphertext from eavesdropping and a short piece of plaintext (from the headers, for example)
	- Attacker decrypts the first piece of ciphertext with *all possible* keys
	- If resulting plaintext matches the known piece of plaintext, correct key has been found
		- $(x, y)$ denote pair of plaintext and ciphertext 
		- $K={k_{1},...,k_{K}}$ is the keyspace of all possible keys $k_{i}$
		- Brute-force attack checks for every $k_{i}\in K$ if:
			- $d_{k_{i}}(y)\stackrel{?}{=}x$
		- If this equality holds, a possible correct key is found; if not, proceed with the next key 
	- Brute-force can be more complicated in practice because incorrect keys can give false positives
	- Brute-force is **always possible in principle against symmetric ciphers**
		- Feasability depends on the key space
		- If testing all keys on a modern computer takes too much time (several decades+), the cipher is *computationally secure*
		- Key space for substitution cipher where we randomly choose which letter gets replaced with which:
			- $26! \approx 2^{88}$
			- This would take many decades with powerful computers, so we can say that this is computationally secure
- **Letter Frequency Analysis**
	- Main weakness of the substitution cipher is that each plaintext symbol always maps to the same ciphertext symbol
		- This means that the statistical properties of the plaintext are preserved in the resulting ciphertext
	- For practical attacks, the following properties of language can be exploited:
		1. Determine the frequency of each ciphertext letter. The frequency distribution (often even for relatively short pieces of text) will be close to that of the given language in general
		2. The above method can be generalized by looking at pairs, triples, quadruples, etc of ciphertext symbols.
			- e.g. `q` is almost always followed by a `u`
		3. Assuming word separators have been found (spaces)(only sometimes true), we can often detect short words (`the`, `and`, etc). Once those words have been identified, we immediately know those letters for the entire text
- **Take-away:**
	- Good ciphers should hide the statistical properties of the plaintext, the ciphertext should appear random
	- A large key space alone is not enough for a strong encryption algorithm

## Cryptanalysis

### General Thoughts on Breaking Cryptosystems

#### Classical Cryptanalysis
- As just discussed:[[01 - Introduction to Cryptography and Data Security#Ways of Breaking the Cipher]]
	- Analytical attacks
	- Brute-force attacks

#### Implementation Attacks
- "Side-channel analysis" can be used to obtain a secret key
	- For example, by measuring electrical power consumption of a processor that operates on the secret key:
		- The power trace can be used to recover the key by applying signal processing techniques
	- Electromagnetic radiation
	- Runtime behavior of algorithm
	- These attacks are mostly relevant against systems that attackers can physically access
		- Implementation attacks against remote systems usually not a concern

#### Social Engineering Attacks
- Bribes, blackmail, espionage can be used to obtain a secret key
- Violently or otherwise
	- Many attacks are successful by tricking people into giving out their password or other personal details over a phone call by impersonating IT or tax collectors

#### Major Takeaway
- **An attacker always looks for the weakest link in a cryptosystem. We must choose strong algorithms *and* make sure that social engineering and implementation attacks are not practical**
- Solid cryptosystems should adhere to **Kerckhoff's Principle**

### Kerckhoff's Principle
- *A cryptosystem should be secure even if the attacker knows all details about the system, with the exception of the secret key. In particular, the system should be secure when the attacker knows the encryption and decryption algorithms*
- This is counter-intuitive. It is tempting to assume that a system is secure with *security by obscurity*
	- Historically theses systems are often broken easily as soon as the 'secret design' has been reverse-engineered or leaked
	- See [Content Scrable System](https://en.wikipedia.org/wiki/Content_Scramble_System) on DVDs
		- It was only secure for ~3 years until it was reverse-engineered

### How Many Key Bits Are Enough?

Two important points ("crucial aspects") to remember:
1. Discussion of key lengths for symmetric crypto algorithms only relevent is a brute-force attack is the best known attack
2. Key lengths for symmetric and asymmetric algorithms are dramatically different
	- e.g. an 80-bit symmetric key provides roughly the same security as a 1024-bit RSA asymmetric key

| Key  length | Security estimation |
| ----------- | ----------- |
| 56-64 bits | short term: a few hours or days |
| 112-128 bits | long term: several decades in the absence of quantum computers | 
| 256 bits | long term: several decades, even with quantum computers that run the currently known quantum computing algorithms | 

### Modular Arithmetic and More Historical Ciphers
















































