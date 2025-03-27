# Cryptography🔐
**Kerckhoffs’s principle: "A cryptosystem should be secure even if everything about the system, except the key, is public knowledge"**
---

**Cryptography** is the practice of securing information while transmitting it from one computer to another or storing data on a computer to prevent unauthorized access. Cryptography involves encryption and decryption.

**Encryption** is the process of converting plaintext (readable text/message) into ciphertext (non-readable text/message).

For example:

[ABC] plaintext → ⚙️**Encryption**⚙️ → [#3S4D] ciphertext

**Decryption** is the process of converting ciphertext (non-readable text/message) back into plaintext (readable text/message).

For example:

[#3S4D] ciphertext → ⚙️**Decryption**⚙️ → [ABC] plaintext

---

## TYPE

There are two primary types of encryption techniques

1. symmetric key encryption 
2. asymmetric key encryption

---

## Symmetric key encryption

**In symmetric-key encryption**, the message/information is encrypted and decrypted using the same key (secret key). Therefore, it is also known as secret key cryptography or private key cryptography. The strength of encryption depends on the key size being used. Examples: **Stream Cipher** and **Block Cipher**.

1. Common algorithms include AES, DES, Blowfish, 3DES, and RC4.
2. It uses one key for both encryption and decryption.
3. It is faster and more efficient for large amounts of data.

The mathematical representation is as follows:

**P = D(K, E(K, P))**

Where:

- **K** → Encryption and decryption key
- **P** → Plaintext
- **D** → Decryption
- **E(K, P)** → Encryption of plaintext using **K**

---

## **Asymmetric Key Encryption**

**Asymmetric-key cryptography** uses two different keys for encryption and decryption. The key used for encryption is the **public key** (publicly available), and the key used for decryption is the **private key** (only the owner knows the private key). This is also known as **public key cryptography**. Examples: **Digital signature**, **encrypted browsing sessions**, and **cryptocurrency transactions**.

1. It uses two keys: a public key for encryption and a private key for decryption.
2. It is more secure but slower than symmetric encryption.
3. Common algorithms include RSA, ECC, and Diffie-Hellman.

The mathematical representation is as follows:

**P = D(Kd, E(Ke, P))**

Where:

- **Ke** → Encryption key
- **Kd** → Decryption key
- **D** → Decryption
- **P** → Plaintext
- **E** → Encryption
- **E(Ke, P)** → Encryption of plaintext using **Ke** (encryption key).

---

## Public key

A **public key** is **a large numerical value used to encrypt data**. A public key is one half of a key pair used in public-key cryptography (also known as asymmetric cryptography) and is freely shared to encrypt messages or verify digital signatures. Only the corresponding private key can decrypt the message or sign the data.

### **Public-Key Cryptography:**

This system uses two mathematically linked keys: a **public key** and a **private key**.

- **Public Key:** This key can be shared with anyone and is used for encrypting messages or verifying digital signatures.
- **Private Key:** This key must be kept secret and is used to decrypt messages encrypted with the corresponding public key or to create digital signatures.
- **How it Works:** Anyone can use the public key to encrypt a message, but only the owner of the private key can decrypt it. Similarly, the owner of the private key can use it to create a digital signature, and anyone with the corresponding public key can verify the signature.
- **Applications:** Public-key cryptography is widely used for secure communication, digital signatures, and authentication, including in HTTPS for secure web browsing, email encryption, and digital signatures.
- **Examples of Public Key Cryptography Algorithms:** RSA, Elliptic Curve Cryptography (ECC), and Diffie-Hellman.

---

## TERMS

**In the context of cryptocurrency and blockchain:**

### **Public Key:**

- **Function:** The public key is like a bank account number, used to receive funds. Think of it as your wallet's address.
- **Security:** It can be shared publicly without compromising your funds.

### **Private Key:**

- **Function:** The private key is like a password, used to access and control your funds.
- **Security:** It must be kept secret and never shared with anyone.
- **Consequence of Loss/Compromise:** If someone gains access to your private key, they can spend your cryptocurrency.

### **Seed Phrase (Recovery Phrase):**

- **Function:** A sequence of words that acts as a backup for your private keys, allowing you to recover your wallet and access your funds if you lose your device or forget your private key.
- **Security:** It must be kept secret and stored securely.
- **Analogy:** Like a backup key to a safe.
- **Consequence of Loss/Compromise:** If someone gains access to your seed phrase, they can access your wallet and all its associated funds.

### **Secret Key:**

- **Function:** In some contexts, "secret key" can be used interchangeably with "private key."
- **Security:** It must be kept secret and never shared with anyone.
- **Analogy:** Like a password or PIN.
- **Consequence of Loss/Compromise:** If someone gains access to your secret key, they can spend your cryptocurrency.

---

## **asymmetric** and **symmetric** algorithms

| **Type** | **Algorithm** | **Cipher Name** | **Examples** |
| --- | --- | --- | --- |
| **Symmetric** | AES (Advanced Encryption Standard) | AES-128, AES-256 | Advanced Encryption Standard |
| **Symmetric** | DES (Data Encryption Standard) | DES, 3DES | Data Encryption Standard |
| **Symmetric** | RC4 (Rivest Cipher 4) | RC4 | Stream Cipher |
| **Symmetric** | Blowfish | Blowfish | Block Cipher |
| **Asymmetric** | RSA (Rivest–Shamir–Adleman) | RSA | Public-Key Cryptosystem |
| **Asymmetric** | ECC (Elliptic Curve Cryptography) | ECDSA, ECDH | Elliptic Curve Cryptography |
| **Asymmetric** | ElGamal | ElGamal | Public Key Cryptosystem |
| **Asymmetric** | DSA (Digital Signature Algorithm) | DSA | Digital Signature Algorithm |

---

## HASHING

**Hashing** is the process of scrambling a piece of information or data beyond recognition. It is irreversible. We pass the input through a hash function to calculate the hash value, digest, or hash of the file.

The **difference** between hashing and encryption is that **hashing** is irreversible, while **encryption** is a reversible process.

Websites use hashing to store usernames and passwords on the server.

- A **hash function** ensures that the same input always produces the same output.
- It is used to check file integrity.

### Hash Function:

- Mathematical operations are carried out on two blocks.
- Both blocks are created by dividing the initial input into equal parts.
- This can be carried out multiple times, but the final digest must be consistent for the same input.

| Hash Algorithm  | Digest Size |
| --- | --- |
| MD5 | 128 BITS |
| SHA256 | 256 BITS |

What if two person used same password? Since hash function is same for all user ————>  This type of problem is called Hash Collision. 

To prevent this, we use **salting & peppering method.** 

**Salting** is process of adding a random value (salt) to a password before hashing it, making each password hash unique.

Example: 

| Input | MD5 Hash Value |
| --- | --- |
| cryptography | d2fc0657c7712abbe7 |
| “cryptography”+(abc123) | c5649e531064a82c |

**Peppering** is process of adding a secret value (pepper) to the password before hashing, making it harder to crack.

Example: 

| Input | Hash |
| --- | --- |
| cryptography | d2fc0657c7712abbe7 |
| “cryptography” + pepper "secretkey" | 4ba285b09f39de233d |

Hash Function Names :  

- MD5
- SHA-1
- SHA-2 (SHA-224, SHA-256, SHA-384, SHA-512)
- SHA-3 (SHA3-224, SHA3-256, SHA3-384, SHA3-512)
- CRC32
- HMAC (Hash-based Message Authentication Code)

---

## **Deterministic & Randomized**

**Deterministic algorithms** always produce the same output for a given input.

**Example:** Sorting the numbers [3, 1, 2] will always result in [1, 2, 3].

They are predictable and ensure consistency every time they run.

**Randomized algorithms** use random values during execution, so their output can vary each time, even with the same input.

**Example:** Shuffling the list [3, 1, 2] might result in different orders, such as [2, 3, 1] or [1, 3, 2].

They are often used to solve problems more efficiently or in cases where unpredictability is beneficial.

**Perfect secrecy** is always desirable but comes at a heavy price.

- The key must be as long as the message.
- A fresh key is required for every instance of encryption.

In practice, perfectly secure encryption is simply not possible.

- The goal is to get “CLOSER” to perfect secrecy.
- It is impossible to eliminate practical limitations of perfect secrecy, such as shorter key lengths or key reusability

Various Attack Model

 ⇒ Ciphertext only attack (COA)

 ⇒ Known plaintext attack (KPA)

 ⇒ Chosen plaintext attack (CPA) Active attack

 ⇒ Chosen ciphertext attack (CCA)
