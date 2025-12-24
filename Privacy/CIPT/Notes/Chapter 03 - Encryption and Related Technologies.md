#CIPT #IAPP #Encryption

## Table of Contents
---
Chapter 3 - Encryption and Related Technologies  
	*Simson L. Garfinkel, CIPP/US*
	[[#3.1 Encryption the Mathematics of Privacy Protection]]
		[[#3.1.1 Vocabulary]]
		[[#3.1.2 Encryption Algorithms and Keys]]
		[[#3.1.5 Encryption Today]]
		[[#3.1.6 Encryption Tomorrow]]
	[[#3.2 Secret Key (Symmetric) Encryption]]
		[[#3.2.1 Algorithms and Key Sizes]]
		[[#3.2.3 Symmetric Cryptography Modes of Operation]]
		[[#3.2.5 Applications of Symmetric Cryptography]]
	[[#3.3 Cryptographic Hash Functions]]
	[[#3.4 Public Key (Asymmetric) Encryption]]
	[[#3.5 Public Key Infrastructure]]
	[[#3.6 Cryptographic Systems Putting It All Together]]
	[[#3.7 Other Cryptographic Applications and Concepts]]


## 3.1 Encryption: the Mathematics of Privacy Protection
---
**Primary Function: Confidentiality**
- **Definition:** The process of scrambling large quantities of data so it cannot be deciphered by unauthorized entities.
- **Data in Transit:** Protects information sent over the internet (e.g., stopping interception).
- **Data at Rest:** Protects information stored on devices (laptops, mobile phones) in case of loss or theft.

**Additional Cryptographic Functions** Beyond confidentiality, encryption serves three vital roles in information security:
- **Digital Signatures (Integrity):** Allows a third party to verify the identity of the sender and confirm the document has not been modified since signing.
- **Identification:** Establishes a link to a legal identity (person or corporation).
- **Authentication & Pseudonymization:** Can prove that multiple documents were authored by the same entity without revealing the specific legal identity. This provides authenticity while maintaining privacy (unlike static identifiers like Social Security Numbers which are prone to theft).

**Emerging Technologies: Blockchain** Modern cryptography enables cryptocurrencies and distributed ledger technologies.
- **Components:** Uses digital signatures and cryptographic hash functions.
- **Structure:** An append-only database known as a "ledger."
- **Use Cases:** Transfer of value/ownership (Bitcoin, Ethereum), NFTs, and Smart Contracts (transfers dependent on external events).

**Key Cryptographic Concepts**
- **Algorithm Types:**
    - **Symmetric:** Also known as Secret Key algorithms.
    - **Asymmetric:** Also known as Public Key algorithms.
- **Public Key Infrastructure (PKI):** A system designed to solve the "key distribution problem" inherent in asymmetric encryption.

**Security Determinants** The strength of an encryption system relies on more than just the math. Key factors include:
- **Algorithm Strength:** The robustness of the logic used.
- **Key Length:** Quantitative measure; generally, longer keys offer higher security.
- **Implementation:** The code and architecture used to deploy the encryption.
- **Key Management:** How keys are stored and exchanged.
- **Critical Note:** Poor implementation or weak key management can render even the strongest algorithms worthless.

**Data Protection: In Transit & At Rest**
- **The "Postcard" Analogy:** Sending unencrypted data over the internet is like sending a postcard; anyone along the path can read it. Encryption ensures that even if the "postcard" is intercepted, the content is indecipherable.
- **Physical Device Security:** Encryption protects privacy when physical hardware (laptops, phones) is lost or stolen.
- **Regulatory Impact (Key Exam Concept):** Most breach-notification laws contain an exception for encrypted data. If a device is stolen but the data is encrypted, the organization usually does not have to notify the affected individuals or authorities.

**Access Control & Integrity**
- **Field-Level Encryption:** Advanced techniques (used in systems like MongoDB) allow individual data fields to be encrypted with specific keys. This limits what a database user or application can modify, offering granular control.
- **Integrity Verification:** Cryptographic digital signatures verify that a document has not been modified since it was created.
###### 3.1.1 Vocabulary
**Plaintext:** The original, unencrypted data.
**Ciphertext:** The encrypted message.
**Cryptographers:** People who study the science of encryption.
**Cryptanalyst (Code Breaker):** Professionals who decrypt, or "crack," coded messages.

• **Work Factor:** The measure of effort an adversary needs to expend to decrypt a message.

• **Adversary:** The constant presence in security engineering assumed to be trying to gain unauthorized access or make unauthorized changes.

Encryption was historically developed to secure messages sent between locations, particularly diplomatic and military messages, which were vulnerable during transit

###### 3.1.2 Encryption Algorithms and Keys
Encryption rapidly scrambles large quantities of data (encrypts) so that unauthorized entities cannot decipher or understand the information. This protects confidentiality when data is sent over the internet or stored on a laptop.

The scrambling and unscrambling processes rely on two core components:

**1. Encryption Algorithms:**
• These are the mathematical procedures used to encrypt and decrypt data.
• There are fundamentally two kinds of encryption used today:
    ◦ **Secret Key (Symmetric) Encryption:** The **same key** is used for both encryption and decryption.
    ◦ **Public Key (Asymmetric) Encryption:** One key encrypts, and a **second key** decrypts
**2. Keys (The Secret Ingredient):**
• Encryption systems use keys that are very large numbers.
• For example, the widely used symmetric algorithm, Advanced Encryption Standard (AES), is typically used with keys that are 128 bits or 256 bits in size. A 128-bit key has approximately 3×1040 possible keys.
• The security of an encrypted document depends on both the strength of the algorithm and the encryption key itself

##### 3.1.5 Encryption Today
**TLS Limitations**
While TLS secures the _content_ of communication (**confidentiality**), it fails to protect metadata, making it vulnerable to **traffic analysis**.

|Information TLS Does Not Protect|Implication (Traffic Analysis)|
|---|---|
|**Data Exchange Amount**|The size/length of the messages being sent.|
|**Location of Endpoints**|The IP addresses of the sender and receiver.|
|**Fact of Exchange**|The very fact that communication is occurring.|
**Data-at-Rest Encryption Methods**
Encryption used to protect information stored over an extended period on a computer system is called **data-at-rest** encryption. Two common approaches are used to implement this:
	**1. Application-Level Encryption**
	This approach encrypts data based on the structure of the data itself (file or record).
	- **Synonyms:** File-level or document-based encryption.
	- **Mechanism:** The technology is typically **built into the application program**.
	- **Examples:** Saving a document with a "password to open" feature in programs like **Microsoft Word** or **Adobe Acrobat**. Encryption can also be applied post-creation using add-on file encryption programs.
	**2. Device-Level Encryption**
	This approach encrypts the entire storage volume at a very low level, regardless of the individual file structure.
	- **Mechanism:** The encryption is performed on a **block-by-block basis** by the computer's storage subsystem.
	- **Implementation:** Typically handled by the operating system (OS), a special device driver, or hardware built into the storage device itself.
	- **Advanced Example (Apple Devices):**
	    - Uses a **special chip** that automatically encrypts and decrypts data sent between the microprocessor and flash memory.
	    - The **encryption key** is derived from the **user's password** combined with a **random key stored inside the chip**.
	    - **Security Features:** The chip is configured to automatically **wipe itself** (rendering data unrecoverable) if too many incorrect password attempts are made. Since the key cannot be physically extracted from the chip, the encrypted data cannot be moved elsewhere for brute-force cracking.

###### 3.1.6 Encryption Tomorrow
**Working with Encrypted Data: Advanced Approaches**
To work with data while it remains encrypted, avoiding the need for cleartext processing, three advanced approaches are currently utilized:
	**1. Secure Enclaves**
	These methods rely on **microprocessor modifications** to create a secure, isolated environment for computation. They offer the **highest performance** for working with confidential data.
	- **Mechanism 1 (Isolation):** Relies on special hardware (e.g., **Arm TrustZone**) that **prevents the main microprocessor from accessing the memory** where the secure application is running.
	- **Mechanism 2 (Hardware Encryption):** Uses specialized hardware within the microprocessor (e.g., **Intel Software Guard Extensions - SGX**) to automatically **encrypt memory as it's written and decrypt it as it's read**. The cryptographic key is only accessible to programs with specific privileges.
	- **Vulnerability Note:** Despite high performance, the security of these systems has been repeatedly compromised by various **implementation flaws** discovered by security researchers.
	**2. Homomorphic Encryption (HE)**
	This is a collection of mathematical techniques that allow for computations to be performed directly on encrypted data without ever decrypting it.
	- **Development**: Generalized techniques were first developed in 2009 and are now deployable for certain classes of computation.
	- **Benefit**: Enables outsourced processing (e.g., in the cloud) while maintaining data confidentiality.
	**3. Multiparty Computation (MPC)**
	This class of algorithms allows programs running on **different computers** to collectively compute a result without compromising each party’s individual private data.
	- **Performance:** MPC algorithms are currently **faster** than Homomorphic Encryption algorithms.
	- **Setup:** MPC is typically **harder to set up** due to the need for coordinated computations among all parties.
	- **Security Model:** Many MPC systems assume participants are **honest but curious**:
	    - **Honest:** They faithfully execute the specified MPC protocol.
	    - **Curious:** They may try to infer confidential information from the data they receive, but the protocol is designed to prevent this inference.
	- **Vulnerability Note:** Most multiparty systems allow parties to **reveal private information if they conspire together**.


## 3.2 Secret Key (Symmetric) Encryption
---
Symmetric encryption uses a **single secret key** for both encryption and decryption. Its primary advantage is its computational speed and efficiency, making it the choice for large-volume data handling.

|**Factor**|**Description**|
|---|---|
|**Key**|One shared secret key.|
|**Speed**|**Extremely fast** (up to 1,000 times faster than asymmetric).|
|**Best For**|Encrypting large amounts of data (Bulk Data).|

**Key Use Cases**
- **Data at Rest Encryption:** Securing data stored locally on devices and servers.
    - Full-disk encryption (e.g., BitLocker, FileVault).
    - Database encryption (encrypting large volumes of records).
    - Securing backups and cloud storage (e.g., AES-256).
- **Bulk Data in Transit:** Protecting large streams of data efficiently.
    - Encrypting data inside a **Virtual Private Network (VPN) tunnel** _after_ the initial connection is established.
    - Real-time video or audio streaming.
- **Hybrid Encryption:** Encrypting the actual communication data _after_ the session key has been securely exchanged via asymmetric encryption (e.g., the second half of an HTTPS session).
###### 3.2.1 Algorithms and Key Sizes
Secret key algorithms, where the same key encrypts and decrypts data, fall into two main types:
1. **Stream ciphers:** Encryption algorithms that process one byte of data at a time.
	    ◦ Historically, stream ciphers only used substitution, which made them somewhat slower and less secure than block ciphers.
	    ◦ The **RC4 algorithm** was widely used in the 1990s with Netscape's SSL protocol, but attacks against it were demonstrated in 2015, meaning RC4 should no longer be used.
	    ◦ **ChaCha20** is a high-performance stream cipher, and its authenticated encryption variant, **TLS_CHACHA20_POLY1305_SHA256**, is one of the five ciphers in the TLS 1.3 specification.
2. **Block ciphers:** Encryption algorithms that transform a small block of data at one time, usually 16, 32, or 64 bytes.
	    ◦ Both the **Data Encryption Standard (DES)** and **Advanced Encryption Standard (AES)** are block ciphers.
	    ◦ Block ciphers traditionally used both **substitution** and **transposition** (scrambling bits within bytes), making them more secure.

###### 3.2.2 Symmetric Cryptography Attacks and Threats
**Cryptanalysis**: The process of trying to decipher an encrypted message


| **Attack Name**                       | **Attacker's Known Information**                                                                                            | **Attacker's Goal/Outcome**                                                                               |
| ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **Known Ciphertext Attack**           | Only the **Ciphertext (C)** (the encrypted message).                                                                        | To determine the corresponding **Plaintext (P)**.                                                         |
| **Known Plaintext Attack**            | A pair of **Plaintext (P)** and its corresponding **Ciphertext (C)**.                                                       | To determine the **Encryption Key (K)**used to encrypt $P$ into $C$.                                      |
| **Chosen Plaintext Attack**           | The attacker gets to **choose the Plaintext (P)** and receives the resulting **Ciphertext (C)**.                            | To determine the **Encryption Key (K)**. (This is a more powerful variant than a Known Plaintext attack). |
| **Differential Cryptanalysis Attack** | A collection of **similar Plaintexts ($P_1$ through $P_N$)** and their corresponding **Ciphertexts ($C_1$ through $C_N$)**. | To determine the **Encryption Key (K)** by analyzing the differences/patterns in the messages.            |
| **Related Key Attack**                | A set of **Ciphertexts** that were encrypted using a number of **related keys**.                                            | To learn **some or all of the related keys**and subsequently decrypt the Ciphertexts.                     |
![[Pasted image 20251129120759.png]]

###### 3.2.3 Symmetric Cryptography Modes of Operation
**Symmetric Cryptography Modes of Operation** describe the precise mechanisms for combining repeated invocations of these block algorithms to encrypt larger amounts of data.

Understanding these modes is crucial because the choice impacts the security and flexibility of the system.

**Key Modes of Operation**

| Mode                              | Key Functionality                                                                               | Advantages                                                                                                                                                                         |
| --------------------------------- | ----------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Counter Mode (CTR)**            | Replaces the Initialization Vector (IV) with a counter.                                         | Allows decryption to start at any point in the data, making it popular for disk encryption. Encryption and decryption can be parallelized, and ciphertext errors do not propagate. |
| **Authenticated Encryption (AE)** | A family of modes that injects additional information into the ciphertext.                      | Allows the decrypting program to verify two things: that the correct key was used and that the plaintext was not modified after it was encrypted.                                  |
| **Galois/Counter Mode (GCM)**     | The most popular AE mode. Provides high-performance parallelized encryption and authentication. | Increasingly the mode of choice for high-speed communications or applications requiring large amounts of data encryption due to its performance.                                   |

###### 3.2.5 Applications of Symmetric Cryptography
Common uses of **Secret Key (Symmetric) Encryption**:
1. **Documents with Passwords**
    ◦ Programs like Microsoft Office and Adobe Acrobat use symmetric encryption to password-protect documents.
    ◦ Typically, the document is encrypted with a randomly generated key, and that key is then encrypted using a hash of the user's passphrase.
    ◦ These systems can be set up to allow multiple passphrases to unlock the document, sometimes implementing a "master password".

2. **Block-Level Disk Encryption**
    ◦ This approach encrypts data at the driver layer, separately encrypting each disk sector.
    ◦ It transparently encrypts every file stored on the disk, including non-file data like hibernation data or virtual memory.
    ◦ These schemes typically use a variant of Counter Mode (CTR) or Galois/Counter Mode (GCM).

3. **Encrypted Databases**
    ◦ Symmetric encryption can be applied to databases in various ways, such as encrypting the entire file, individual rows, or columns. You can leave the index unencrypted for faster searching.
    ◦ Each strategy involves trade-offs regarding security, performance, and recoverability.

4. **Transport Layer Security (TLS)**
    ◦ After a cryptographic session is established using asymmetric cryptography, symmetric encryption is used for the bulk encryption of data sent over the World Wide Web.
    
5. **Cryptographic Erasure and Retention Rules**
    ◦ Complete data erasure of stored media can be achieved by simply erasing the key, which renders the encrypted contents indecipherable.
    ◦ This approach is useful for making document backups on tape or in the cloud inaccessible, and is much faster than overwriting the storage media.

6. **Persistent VPNs**
    ◦ Two networks connected for a long duration using a Virtual Private Network (VPN) may use a static encryption key, which the administrator programs into all necessary systems.

7. **Secret Sharing**
    ◦ A single key can be split into multiple mathematical shares, allowing the encrypted data to be recovered only if a predetermined number of shares are brought together (e.g., any three out of seven auditors).
    
8. **Wireless Networks
    ◦ The typical use of **WPA2 and WPA3** requires all units on the network to be programmed with the same passphrase or key.
 - This key or passphrase is then used to derive a specific symmetric encryption key that secures the data sent over the wireless network.
 - **WPA3** is the recommended choice, as it provides for **forward secrecy**.
 - Both WPA2 and WPA3 also support an enterprise mode, where users must be authenticated with a username and password or a Public Key Infrastructure (PKI) certificate.


## 3.3 Cryptographic Hash Functions
---
Hash algorithms are fast mathematical functions that take an input of any length and produce a small output, typically ranging from 16 to 128 characters, that appears random. Although the output seems random, it is entirely determined by the input.

**Key Properties and Purpose:**
• In a strong hash function, the output cannot be predicted without running the algorithm.
• A change to any single bit in the input will, on average, change half of the bits in the output. Hash functions that do not exhibit this property should not be used.
• Cryptographic hash functions are used to detect unauthorized changes to files, documents, database records, and other stored data.

###### 3.3.2 Applications of Hash Functions
**Generating Cryptographic Keys**
Hash functions solve the usability problem associated with complex, long encryption keys.
- **Key Format Issue:** Encryption keys (e.g., a 256-bit key) are typically displayed as **long hexadecimal strings** (e.g., `d0e4...36af`), making them impossible to remember or type accurately.
- **Solution (Passphrase Conversion):** Users are prompted to enter a memorable **passphrase** (e.g., "Hello World!"). A standard **hash function** (e.g., **SHA3-256**) is then used to securely and consistently convert that passphrase into the required hexadecimal cryptographic key.

**Document Identification and Integrity**
Hash functions create a unique, fixed-length value (the hash) that acts as a secure digital fingerprint for any document.
- **Unique Identification:** No two documents should have the same hash value for a given function.
- **Independence:** The hash value depends _only_ on the file's contents, not its filename or modification time.
- **Version Control:** The document's contents can be uniquely identified simply by its hash value, **assuming the hash function is unbroken**.

**Digital Signatures**
Hash functions are the first step in the process of creating a digital signature, which provides **authentication** and **non-repudiation**.
- **Process:**
    1. The document's contents are first run through a hash function to produce a concise hash value.
    2. This resulting hash value is then **cryptographically signed** using the person's **private signing key** (a public key algorithm is used).
    3. **Verification:** Anyone can verify the signature by rehashing the document and comparing the result with the signature using the person's **public key**. If they match, the document's authenticity and integrity are confirmed.

## 3.4 Public Key (Asymmetric) Encryption
---
Asymmetric encryption, often called "public key cryptography," uses two distinct keys. One key encrypts the data, and a second, different key decrypts it.
	• The plaintext is encrypted using _public information_, and decryption requires _private information_.
	• The system can be metaphorically understood as a locked box with a slot on top; anyone can drop a message into the box, but the combination is needed to retrieve it.
	• The terms "encrypting key" and "decrypting key" are used for encryption, while "signing key" and "verifying key" are used for digital signatures, to avoid confusion.

| **Factor**   | **Description**                              |
| ------------ | -------------------------------------------- |
| **Key**      | A pair of keys (Public and Private).         |
| **Speed**    | **Slower** and more resource-intensive.      |
| **Best For** | Key exchange, authentication, and integrity. |
 **Key Use Cases**
- **Secure Key Exchange:** The most common use. It securely transfers the symmetric "session key" over an unsecure public network.
    - **TLS/SSL Handshake (HTTPS):** The server's public key encrypts a randomly generated symmetric session key, which only the server can decrypt with its private key.
- **Digital Signatures (Non-repudiation & Integrity):** Using the **private key** to encrypt a document's hash value, proving the sender's identity and that the document has not been tampered with.
- **Authentication and Identity:** Verifying that a communicating party is who they claim to be.
    - Used in **digital certificates** to authenticate servers and clients.
    - Protecting access to accounts (e.g., SSH login keys).
- **Cryptocurrency/Blockchain:** Users use their **private key** to authorize transactions, proving ownership of a public key address.

###### 3.4.1 Algorithms and Key Sizes
Asymmetric algorithms are generally much slower than their symmetric counterparts. Their security often relies on hard mathematical problems, frequently involving the manipulation of prime numbers.
	• **RSA:** Named after Rivest, Shamir, and Adleman, RSA is one of the most common asymmetric algorithms. RSA keys are interchangeable, meaning they can be used for both message secrecy (encryption/decryption) and digital signatures.
	• **Elliptic Curve Cryptography (ECC):** ECC systems provide similar security to RSA using significantly shorter keys because the underlying mathematical problem is harder to solve for the same key size.
	• **Quantum Threat:** Current asymmetric algorithms like RSA and ECC are vulnerable to attack by large-scale, fully realized quantum computers, meaning they will eventually be replaced by new standards selected by NIST.

###### 3.4.2 Digital Signatures
Digital signatures combine cryptographic hash functions with public key cryptography. They serve as a mark affixed to a digital document to identify the signer and can be used for authentication.

**The Process:**
1. The document's cryptographic **hash value** is computed.
2. This hash value is then encrypted using the asymmetric **signing key**.

**Verification (by the Relying Party, RP):**
1. The signature is decrypted using the widely distributed **verification key**.
2. The original document is re-hashed.
3. If the decrypted hash matches the re-hashed document, the RP knows the document has not been modified since it was signed, and it was signed by the matching key.

If a person’s private signing key is stolen, a thief can sign documents in the victim’s name without detection.


## 3.5 Public Key Infrastructure
---
**Certificates**
• An entity called a **Certificate Authority (CA)** asserts that a specific public key belongs to a particular entity.
• These assertions are stored in small electronic documents called certificates.
• Browser vendors, such as Microsoft, Apple, and Google, evaluate CAs and agree to place a copy of the trustworthy CA’s public key into their browsers.
• To verify a certificate's digital signature, a browser computes the cryptographic hash of the certificate information (H1), decrypts the signature using the CA's public key (H2), and checks if H1 equals H2.

**Client-Side PKI**
• In addition to verifying the identity of websites, PKI can verify the identity of users. This process is similar to website validation, but the certificate is issued to an individual.

**Certificate Revocation**
• Workable PKI systems include **certificate revocation**, a feature that allows the certificate’s owner or issuer to indicate that a certificate should no longer be used or trusted, typically if the private key is stolen or lost.

• Revocation approaches include:
    ◦ A "revocation certificate" obtained by the owner and published if the private key is compromised.
    ◦ A **Certificate Revocation List (CRL)** maintained by CAs.
    ◦ An online revocation service, typically based on the **Online Certificate Status Protocol (OCSP)** standard.
• Note that while individual certificates can be revoked, it is not possible to revoke a CA itself.

**Time **
• Computers using PKI must securely know the current time because certificates have validity periods. If a computer's time is wrong, it can be convinced that an expired certificate is still valid.

**Limitations**
• While PKI works well, it is "far from perfect" and is considered increasingly frayed as its use exposes more problems.




## 3.6 Cryptographic Systems: Putting It All Together
---
This process outlines the steps a web browser takes to establish a secure, encrypted **TLS (Transport Layer Security)**connection when a user accesses a website via HTTPS. This process ensures data **confidentiality** and **authentication**.

###### 3.6.1 Steps for Establishing an HTTPS Connection
1. **Domain Name Resolution (DNS):**
    - The web browser first issues a **DNS request** to translate the human-readable domain name (e.g., `www.company.com`) into its numerical **IP address**.
2. **TLS Connection Initiation:**
    - The browser uses the obtained IP address to open a **TLS connection** to the web server.
3. **Key Exchange (Session Key Agreement):**
    - The browser and server perform a cryptographic key exchange algorithm to securely agree upon a shared, symmetric encryption key, known as the **session key**.
    - Common algorithms used for this key exchange include:
        - **Diffie-Hellman Key Exchange (DHE)**
        - **Elliptic Curve Diffie-Hellman Key Exchange (ECDHE)**
    - This session key will be used to encrypt all the subsequent high-volume communication (the actual application data).
4. **Optional Client Authentication:**
    - The server can optionally send a **CertificateRequest** message to the client, asking the client to prove its identity using a **client-side certificate**.
5. **Client Verification:**
    - If client authentication is requested, the client sends a **CertificateVerify** message back to the server.
    - This message is **signed with the client’s private key**, using **PKI (Public Key Infrastructure)** principles to prove the client's authenticity (i.e., proving they possess the private key corresponding to the public key in the certificate).
6. **Application Data Exchange:**
    - Once the secure session key is established and authentication is complete (if required), the server and client are free to exchange application data (e.g., loading the web page content) which is secured by the **session key**.

 **TLS Decrypting Proxy Attack (Man-in-the-Middle)**
A TLS Decrypting Proxy is a sophisticated form of **Man-in-the-Middle (MITM)** attack that allows an intermediary (the proxy) to read traffic intended to be fully encrypted end-to-end. This attack compromises the **confidentiality** of data by relying on the client's trust store.

Here are the steps involved, presented as a clear study list:
1. Connection Redirection
	- The web browser issues a **DNS request** for the legitimate server (`www.company.com`).
	- The attacker intervenes, and the browser receives the **IP address of the attacker's TLS proxy server** instead of the correct server IP. The client is now mistakenly connecting to the MITM.
2. Dual Session Establishment
	The proxy immediately sets up **two independent, encrypted TLS sessions** to act as a bridge:
	- **Session A:** Browser-to-Proxy (encrypted).
	- **Session B:** Proxy-to-Legitimate Server (encrypted).
3. Server Impersonation
	- The legitimate server successfully authenticates itself to the proxy (Session B).
	- The proxy then generates and sends the client a **fake certificate** claiming to be `www.company.com`, which is signed with the proxy's **fraudulent Certificate Authority (CA) key**. The client is deceived into trusting the proxy.
4. Optional Client Impersonation
	- If the legitimate server requests client authentication, the proxy sends a message to the server, signed with a **fake client certificate**, falsely claiming to be the client.
5. Eavesdropping and Data Flow
	- The core of the attack: The proxy receives data from the server, **decrypts it** (allowing inspection in cleartext), **re-encrypts it** using the key from Session A, and sends it to the client.
	- This reverse process is applied to all traffic from the client to the server, allowing the proxy to view **all application data** transmitted.

###### 3.6.2 Email Encryption
**S/MIME** and **PGP (Pretty Good Privacy)** are the two dominant standards used for securing email communications. Both use **public key cryptography** to provide three core security functions: **confidentiality**, **integrity**, and **authentication**(non-repudiation).

| Feature         | S/MIME (Secure/Multipurpose Internet Mail Extensions)                                                               | PGP (Pretty Good Privacy)                                                                                            |
| --------------- | ------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Foundation**  | Based on **X.509 Certificates** and **PKI (Public Key Infrastructure)**.                                            | Based on the **Web of Trust** model.                                                                                 |
| **Trust Model** | **Hierarchical.** Trust is established by relying on a central, third-party **Certificate Authority (CA)**.         | **Decentralized.** Trust is established through direct, verified relationships between users.                        |
| **Key Storage** | Keys are usually stored and managed by the operating system or browser, and linked to a formal digital certificate. | Keys are stored locally, often in key files or keyring databases managed by the application.                         |
| **Adoption**    | Supported natively by most major commercial email clients (e.g., Outlook, Apple Mail) and enterprise environments.  | Requires third-party software or browser plugins (e.g., GPG for Linux/Windows/Mac). Popular among privacy advocates. |
| **Format**      | Uses **ASN.1** (Abstract Syntax Notation One) and MIME encoding.                                                    | Uses proprietary format (though the standard is open-source/IETF).                                                   |
Both standards secure email by using a **hybrid approach**, which combines the speed of symmetric encryption with the key-management benefits of asymmetric encryption:

1. **Confidentiality (Encryption):**
    
    - The sender's email client generates a random **symmetric session key** for the message.
        
    - The client uses the **recipient's public key** (obtained via PKI or Web of Trust) to encrypt this session key.
        
    - The client uses the symmetric session key to encrypt the large body of the message (the ciphertext).
        
    - The recipient decrypts the session key using their **private key**, and then uses the session key to decrypt the message.
        
2. **Authentication and Integrity (Digital Signing):**
    
    - The sender computes a **hash** (digital fingerprint) of the message content.
        
    - The sender encrypts this hash using their own **private key**. This encrypted hash is the **digital signature**.
        
    - The recipient uses the sender's **public key** to decrypt the signature and reveal the original hash.
        
    - The recipient computes a new hash of the received message. If the two hash values match, the message is confirmed to be **authentic** (signed by the sender) and **unmodified** (integrity).


## 3.7 Other Cryptographic Applications and Concepts
---
###### 3.7.1 USB Security Tokens
These are typically small devices that implement the **Fast Identity Online (FIDO) 2.0 standard**.
- They are significantly different from PKI-based smart cards.
- Designed to be second, after a username/password combination, that helps establish that a person accessing a website today is the same person who previously accessed the website.

###### 3.7.12 Digital Rights Management
◦ DRM systems distribute digital media in an encrypted form.
    ◦ They use public key technology to identify authorized computers, which are then provided with a decryption key.
    ◦ Some DRM systems use **cryptographic erasure** to automatically wipe the decryption key, thus blocking access to a document after a time period has expired.
    ◦ While some systems decrypt content in hardware to prevent capture, the "analog hole" (recording the screen) is still usually possible

###### 3.7.1 Database Encryption
Encryption can be used on individual rows or cells of data in a database, adding a layer of security and limiting opportunities for unauthorized access.

**Encryption Strategies**
There are many strategies for database encryption:
	• Encrypting the entire database file with a single key.
	• Encrypting individual rows or columns.
	• Encrypting rows, columns, or cells with keys stored in other locations.
	• Encrypting the main database but leaving the index unencrypted to allow for rapid searching.

1. Format Preserving Encryption (FPE): An approach that encrypts data in such a way that the resulting encrypted values maintain the **same format** as the plaintext values.
	• This feature makes it possible to add encryption to **legacy systems**.
	• Legacy systems often restrict the types of data that can be stored in specific database fields (e.g., a credit card number must fit in a 16-character numerical field).
	• For example, if a 16-digit credit card number is encrypted using FPE, the resulting ciphertext will also be 16-decimal characters.
		• Traditional encryption, in contrast, might turn a 16-character number into a 16-byte binary object, which could violate the legacy system's field constraints

2. **Order Preserving Encryption (OPE):** This approach encrypts data such that the sort order is preserved. However, OPE inherently leaks information about the encrypted data, although this may be considered acceptable in certain circumstances.

3. **Oblivious Random-Access Memory (ORAM):** ORAM systems are designed to prevent the monitoring of read-and-write operations between the user and the database from revealing **side channel information**.
	    ◦ ORAM encrypts the data written with a key that only the user can access.
	    ◦ To prevent observers from learning access patterns, ORAM typically performs additional read-and-write operations to different parts of memory whenever information is accessed.
	    ◦ Since achieving perfect security (reading and writing every bit of remote memory for every operation) is highly inefficient, systems usually trade increased efficiency for less-than-perfect security.

4. **Private Information Retrieval (PIR):** PIR describes a range of protocols allowing data retrieval from a database without revealing the retrieved information to the database operator or an observer.
	    ◦ PIR systems are a subset of ORAM that provide data access but not necessarily data modification.
	    ◦ Some PIR systems enable sophisticated database operations, such as searching for documents matching a keyword or retrieving encrypted documents in sorted order, all without knowing the underlying data being operated upon.

5. **Homomorphic Encryption**: Set of cryptographic techniques that enable computers to perform calculations or operations directly on **encrypted data (ciphertext)** without ever needing to decrypt the contents. The resulting output remains encrypted until the recipient decrypts it.
	- **Core Principle:** It allows computation on data while maintaining **confidentiality** for all parties involved, including the computing service provider.
	- **Current State of the Art (Example):** An auditor can send a complex, encrypted query (e.g., a statistical model to detect money laundering) to a bank's computer. The bank runs the query and returns the encrypted results. The bank never sees the query, the results, or the conclusion of the model.
	- **Future Potential (2030+ Projection):** HE is advancing rapidly toward scenarios where cloud services could perform complex functions like sharpening photos, running **AI algorithms** (e.g., facial recognition), and data analysis on user-encrypted content without the cloud owner ever accessing the data in **plaintext**.

Each strategy presents different trade-offs related to security, performance, and recoverability. If the database index is encrypted, the system may not be able to respond to certain search queries. Some modern database systems, such as Apple’s iOS operating system database engine, integrate with hardware encryption to implement record-level encryption.