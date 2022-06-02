It is important to note that, _a cipher should be secure even if an attacker somehow knows the details of the algorithm_.

In general, cryptanalysis splits into several subsections and branches:

![Cryptanalysis Overview](assets/cryptanalysis-overview.png)


#### Classical Cryptanalysis
This branch is understood as the _science of recovering the plaintext ` x ` from the ciphertext ` y `, or alternatively, recovering the key ` k ` from the ciphertext ` y `_.

This is further divided into mathematical analysis and brute force attacks.

#### Implementation Attacks
Side Channel analysis can be used to obtain a secret key, for instance, by measuring the electrical power consumption of a processor which operates on the secret key. This power trace can then be used to recover the secret key by applying signal processing techniques. In addition to power consumption, electromagnetic radiation or the runtime behavior of algorithms can give information about the secret key and are, thus useful side-channels.

