# xcha 


Xcha provides a straightforward and effective command-line tool for managing file encryption and decryption using robust cryptographic primitives available in Rust. Its modular design clearly separates key generation, encryption, and decryption operations, making the code easy to understand, maintain, and extend.

The key file is always named key.key and is expected to reside in the same directory as the executable. You have two options for key management: either generate key.key from a password (which produces a deterministic key using SHA3-256) or supply your own 256-bit (32-byte) key by creating a file named key.key in the executable’s directory. This approach ensures consistency and simplifies key handling across all operations.

The app utilizes XChaCha20Poly1305 for encryption. This choice was made because XChaCha20Poly1305 is less error-prone to implement in a custom application than AES, while still offering a comparable level of security. Numerous comparisons between ChaCha20 and AES highlight that both ciphers are excellent; however, XChaCha20Poly1305 is often simpler and more reliable for “homemade” projects. Additionally, it does not require specialized hardware to achieve optimal performance, unlike AES. For more in-depth analysis, please refer to the aes-vs-chacha20.html file in the /html repository.

While Xcha is ideal for personal and small-scale projects, it is important to recognize that professional, production-grade encryption applications are generally superior in terms of auditing, testing, and handling edge cases. Nonetheless, Xcha offers a practical, secure, and user-friendly solution for everyday encryption needs.
