# Digital Envelope - RSA-based Encryption

## Abstract

In today's technological world, the need to handle enormous amounts of data comes with the responsibility to protect it. The concept of a digital envelope addresses this need by electronically encrypting messages and placing them in sealed containers to ensure privacy and security, preventing tampering by unauthorized parties. This project employs RSA (Rivest-Shamir-Adleman) cryptography, utilizing both secret key and public key techniques to implement the digital envelope. The public key conveys the secret key to the recipient, and the secret key is used for encryption and decryption, ensuring secure communication.

## Introduction to Digital Envelope

A digital envelope is a secure electronic data container used to encrypt and authenticate data, protecting messages from unauthorized access. It utilizes both secret (symmetric) key and public key encryption, providing a robust two-layer security approach. Secret key encryption is used for encoding and decoding messages, while public key encryption facilitates the secure transmission of the secret key. Plain text communication is unnecessary with this strategy.

The digital envelope can be implemented using the following techniques:

- For message encryption, algorithms like Rijndael or Two fish using secret keys can be employed.
- RSA's public key encryption algorithm is used to encrypt the recipient's secret key using the recipient's public key.

An example of a well-known cryptographic program that utilizes the digital envelope concept is Pretty Good Privacy (PGP), offering cryptographic privacy and data transmission authentication.

## Encryption using Symmetric Key

In a digital envelope, the sender first chooses a symmetric algorithm session key randomly. This session key is then encrypted with the recipient's public key using an asymmetric algorithm. The original (unencrypted) symmetric session key is used by the sender to encrypt the message body (plaintext). Both the encrypted session key and the encrypted message body (ciphertext) are transmitted to the receiver.

To access the authentic message body, the recipients must first decrypt the session key using their private key and then decrypt the remainder of the message using the decrypted session key (plaintext). Only the owner of the recipient's private key can recover the session key and the original message.

## RSA Algorithm

The RSA algorithm is an asymmetric cryptography algorithm that operates with two different keys: the public key and the private key. The public key is given to everyone, while the private key is kept private.

Key Pair Generation in RSA:

Any individual or party participating in encrypted communication must generate a public key and a private key. The steps to generate the keys are as follows:

1. Create the RSA modulus, n:
   - Select two large prime numbers, p and q.
   - Calculate n = p * q, where n is a big integer, typically at least 512 bits for effective uncrackable encryption.

2. Find the Derived Number, e:
   - The value of e should be greater than 1 and less than (p-1)(q-1).
   - e and (p-1)(q-1) must have no common factors except for 1 (i.e., they are coprime).

3. Create the public key:
   - The RSA public key consists of two numbers: (n, e).
   - Note that while n is part of the public key, the difficulty of factorizing a huge prime number ensures that an attacker cannot obtain the two primes (p & q) required to calculate n within a feasible timeframe. This is the main strength of RSA.

4. Produce a private key:
   - Secure keys P, Q, and e are used to calculate d, which is a distinct number for the given n and e.
   - d is the number less than (p-1)(q-1) such that (d * e) % (p-1)(q-1) equals 1.
   - The mathematical formula for this relationship is: ed ≡ 1 mod (p-1)(q-1).

## Requirements

- Python 3
- RSA (Rivest-Shamir-Adleman) Library

## Getting Started

1. Install Python 3 on your system.
2. Install the RSA library using pip: `pip install rsa`.
3. Follow the documentation to integrate the Digital Envelope into your application.

## Usage and Contribution

To use this Digital Envelope implementation, follow the instructions in the project documentation. Contributions and feedback from the community are highly appreciated. Please report any issues or suggest improvements through the project's GitHub repository.





