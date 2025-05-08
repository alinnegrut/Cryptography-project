# 🔐 OpenSSL RSA Encryption Project

## 📄 Description

This project demonstrates how to use **OpenSSL** to perform basic RSA cryptographic operations: generating key pairs, encrypting messages with a public key, and decrypting them with the corresponding private key. It serves as an introductory exercise in understanding public-key cryptography via the command line.

## 🧰 Languages and Utilities Used

- **OpenSSL** – for key generation, encryption, and decryption  
- **Terminal / Command Line Interface** – for running commands  
- **Text Editor** – for creating and editing text files (plaintext messages)

## 💻 Environments Used

- macOS (via Homebrew)  
- Linux / Windows (use appropriate OpenSSL distribution or package manager)

## 🚶‍♂️ Project Walk-through

### 1. 🔧 Installing OpenSSL

Install OpenSSL via your system’s package manager. Example for macOS:

```bash
brew install openssl
```

### 2. 📁 Open Terminal or Command Prompt

All subsequent steps are performed via terminal or command prompt.

### 3. 🔑 Generate RSA Private Key

```bash
openssl genrsa -out private_key.pem 2048
```

Generates a 2048-bit RSA private key and saves it to `private_key.pem`.

### 4. 🔍 Verify the Private Key

```bash
openssl rsa -in private_key.pem -text -noout
```

Displays the private key in human-readable format to verify its contents.

### 5. 🔓 Generate RSA Public Key

```bash
openssl rsa -in private_key.pem -outform PEM -pubout -out public_key.pem
```

Extracts the public key and saves it to `public_key.pem`.

### 6. 📨 Encrypt a Message

Create a `plaintext.txt` file containing your message. Then run:

```bash
openssl rsautl -encrypt -inkey public_key.pem -pubin -in plaintext.txt -out encrypted.txt
```

Encrypts the plaintext using the public key.

### 7. 📬 Decrypt the Message

```bash
openssl rsautl -decrypt -inkey private_key.pem -in encrypted.txt -out decrypted.txt
```

Decrypts the message using the private key and saves the result in `decrypted.txt`.

### 8. ✅ Verify

Compare `decrypted.txt` with `plaintext.txt` to ensure the message was accurately decrypted.

## 📸 Screenshots

Screenshots demonstrating each step will be added here.

## 📌 Conclusion

This project illustrates how asymmetric encryption works using OpenSSL and RSA. The steps show how to:
- Generate RSA key pairs
- Encrypt data using the public key
- Decrypt data using the private key
- Validate the process through file comparison
