# Basics
Symmetric cryptographic schemes are also referred to as _symmetric-key_, _secret-key_,  and _single-key_ schemes or algorithms. 

Symmetric cryptography is best introduced with an easy to understand problem: There are two users, Alice and Bob, who want to communicate over an insecure _channel_

The term: _channel_ can refer to any sort of a communication link. This can be the internet, a stretch of air in case of mobile phones or wireless LAN and so on. The problem starts with Oscar, whi has access to the channel, for instance, by hacking into an internet router or by listening to radio signals of a Wi-Fi communication. (This type of unauthorized listening is called _eavesdropping_).

![Better Figure 1.4](assets/alice-bob-oscar-basic.png)

In this situation, cryptography offers a powerful solution: Alice encrypts her message ` x ` using a symmetric algorithm, yielding the ciphertext ` y `. Bob receives the ciphertext and decrypts the message. _Decryption is, thus, the inverse process of encryption_.

![Figure 1.5](alice-bob-oscar-sym-key.png)

There are a few important values in this figure:
- ` x ` is called _plaintext_  or _cleartext_.
- ` y ` is called _ciphertext_
- ` k ` is called the _key_
- The set of all possible keys is called the _key space_.

==The system needs a secure channel for distribution of the key== between Alice and Bob. The secure channel shown in Figure 1.5 can, for instance, be a human who is transporting the key in a wallet between Alice and Bob. In any case, the key has only to be transmitted once between Alice and Bob and can then be used for securing many subsequent communications. 

One important and also counterintuitive fact in this situation is that both the encryption and the decryption algorithms are publicly known. 
