Cryptography seems cosely linked ot modern electronic communication. However, cryptography is a rather old business, with early examples dating to about 2000 B.C. We'll be dealing with modern cryptography, however it's good to know such things of the past. 

Contrary to popular belief, cryptography is a _sub-branch_ of a wider field of study called **Cryptology**.

![Cyrptography as a part of cryptology](cryptology-tree.png)

Cryptology splits into 2 main branches:
- **Cryptography** is the science of secret writing with the goal of hiding the meaning of a message.
- **Cryptanalysis** is the science and sometimes _art_ of breaking cryptosystems.

Cryptanalysis is of central importance for modern cryptosystems: without people who 
try to break our crypto methods, we will never know whether they are really secure or not. It is important to remember: _"An idea may sound very good in theory, but it may not be practical"_

Because cryptanalysis is the only way to assure that a cryptosystem is secure, it is an integral part of cryptology.

Cryptography itself splits itself into 3 main branches:

- **[[Symmetric Cryptography|Symmetric Algorithms]]** are what most people assume cryptography is like/about: _two parties have an encryption and decryption method for which they share a secret key_. This was the prevalant method in use until 1976 (See [[Bibliography#^0f83df|this reference]] for more detail on it all).
- **Asymmetric (or Public-key) Algorithms**: In 1976 an entirely new and different type of cipher was invented by Whitfield Diffie, Martin Hellman and Ralph Merkle. _In public-key_ cryptography, a user possesses a secret key as in symmetric cryptography but also a public key. Asymmetric algorithms can be used for applications such as digital signatures and key establishment, and also for classical data encryption.
- **Cryptographic Protocols**: Symmetric and asymmetric algorithms can be viewed as building blocks with which applications such as secure Internet communication can be realized. The Transport Layer Security (TLS) scheme, which is used in every Web browser, is an example of a cryptographic protocol.

***NOTE:***  Strictly speaking, hash functions, which will be introduced in Chap. 11, form a third class of algorithms but at the same time they share some properties with symmetric ciphers.

In the majority of cryptographic applications in practical systems, symmetric and  asymmetric algorithms (and often also hash functions) are all used together. This is  sometimes referred to as hybrid schemes.



