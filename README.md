# xcha 


Xcha provides a straightforward and effective way to manage file encryption and decryption using robust cryptographic primitives available in Rust. Its modular structure—with clear separation between key generation, encryption, and decryption modes—makes it both easy to understand and extend. 

The key file is always key.key in the same directory as the executable. You can use the app to generate key.key from a password (which will give you a deterministic key) or you can make your own 256 bit (32 byte) key and name the file key.key and place it in the same directory as the executable. 

XChaCha20Poly1305 is used. Why? Because it is way less error prone than AES to implement in a home made app like this, and it is just as secure. 
