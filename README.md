# xcha 


Xcha provides a straightforward and effective command-line tool for managing file encryption and decryption using robust cryptographic primitives available in Rust. Its modular design clearly separates key generation, encryption, and decryption operations, making the code easy to understand, maintain, and extend.

The key file is always named key.key and is expected to reside in the same directory as the executable. You have two options for key management: either generate key.key from a password (which produces a deterministic key using SHA3-256) or supply your own 256-bit (32-byte) key by creating a file named key.key in the executable’s directory. This approach ensures consistency and simplifies key handling across all operations.

The app utilizes XChaCha20Poly1305 for encryption. This choice was made because XChaCha20Poly1305 is less error-prone to implement in a custom application than AES, while still offering a comparable level of security. Numerous comparisons between ChaCha20 and AES highlight that both ciphers are excellent; however, XChaCha20Poly1305 is often simpler and more reliable for “homemade” projects. Additionally, it does not require specialized hardware to achieve optimal performance, unlike AES. For more in-depth analysis, please refer to the /docs directory in this repo. I put the docs in html form, just view the file from a browser.

While Xcha is ideal for personal and small-scale projects, it is important to recognize that professional, production-grade encryption applications are generally superior in terms of auditing, testing, and handling edge cases. Nonetheless, Xcha offers a practical, secure, and user-friendly solution for everyday encryption needs. This entire app is cargo.toml and main.rs- other encryption apps are over 100 files. The commands to use this app are simple. There are only 3 commands. Key maker (optional), encrypt or decrypt. Very simple and easy to use. 

# Make an optional deterministic key
./xcha -k adelia  

will make key.key - the key will be the same every time you use the password "adelia". You can use any password to make a specific key. Or you can make a key.key file with your own key. This is very versatile. 

# Encrypt a file 
./xcha -e plain.txt encrypted.dat  

encrypts plain.txt to a file called encrypted.dat 

# Decrypt a file 
./xcha -d encrypted.dat decrypted.txt  

decrypts encrypted.dat to a file called decrypted.txt 

# User Friendly

This app is made with 2 files. It has only 3 command functions. It is incredibly easy to feed the code to ai and have it change anything you want. 

