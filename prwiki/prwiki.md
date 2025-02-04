# PRWIKI

TABLE OF CONTENTS
- [Checksums](#checksums)




## CHECKSUMS

### 1. Simple Checksum Methods
These methods are fast but not very secure, mainly used for error detection rather than cryptographic verification.

#### a) Modular Sum
- Adds up all the bytes in a file or message and takes the modulus of the sum.
- Example: **8-bit checksum** → Sum of all bytes **modulo 256**.
- Used in basic error detection (e.g., network packets).

#### b) XOR Checksum
- Each byte is **XORed** sequentially to generate a single checksum byte.
- Detects simple transmission errors but **weak against intentional tampering**.

<br>
<br>

### 2. Cyclic Redundancy Check (CRC)
- Uses **polynomial division** to generate a checksum.
- Common versions:
  - **CRC-8, CRC-16, CRC-32, CRC-64** (higher bits improve error detection).
- Used in **Ethernet, ZIP files, and file integrity checks**.

<br>
<br>

### 3. Cryptographic Hash Functions
These methods are designed to be resistant to intentional tampering and used for **digital signatures, password hashing, and data integrity**.

#### a) MD5 (Message Digest Algorithm 5)
- **128-bit hash**.
- **Fast but weak** against collision attacks.
- Still used in legacy applications but **not recommended for security**.

#### b) SHA (Secure Hash Algorithm)
- **SHA-1**: **160-bit hash**, deprecated due to vulnerabilities.
- **SHA-256, SHA-512 (SHA-2 family)**: Stronger and widely used in security applications.
- **SHA-3**: More resistant to collision attacks, based on a sponge construction.

<br>
<br>

### 4. Fletcher's Checksum & Adler-32
- Used in **data transmission for error detection**.
- **Fletcher-16, Fletcher-32**: Faster than CRC, but **less reliable for burst errors**.
- **Adler-32**: Faster than CRC-32 but **less robust**.

<br>
<br>

### 5. HMAC (Hash-based Message Authentication Code)
- Combines cryptographic hash functions (like SHA-256) with a **secret key**.
- Used in **secure communications** (e.g., TLS, HMAC-SHA256 in authentication).

<br>
<br>

### 6. BLAKE2 & BLAKE3
- **Faster and more efficient** than SHA-2.
- Used in **modern security applications** (e.g., password hashing, data integrity).

<br>
<br>

### 7. Checksum in Redundant Data Storage
- **RAID systems** use **parity-based checksums** for error recovery.
- **ZFS & Btrfs** use checksums to detect **data corruption**.

<br>
<br>

### Choosing the Right Method
| **Use Case**                 | **Recommended Method**      |
|------------------------------|----------------------------|
| Simple error detection       | CRC-32, Fletcher, Adler-32 |
| Data integrity               | SHA-256, BLAKE2           |
| Security-sensitive apps      | HMAC-SHA256, SHA-3        |


