# 🔐 OpenSSL RSA Encryption Project

## 📄 Description

In this project I demonstrated how to use **OpenSSL** to perform basic RSA cryptographic operations: generating key pairs, encrypting messages with a public key, and decrypting them with the corresponding private key using an an introductory exercise in understanding public-key cryptography via the command line.

## 🧰 Languages and Utilities Used

- **OpenSSL** – for key generation, encryption, and decryption  
- **Terminal / Command Line Interface** – for running commands  
- **Text Editor** – for creating and editing text files (plaintext messages)

## 💻 Environments Used
 
- [Oracle Virtual Box](https://www.virtualbox.org/)
- Kali Linux

## 🚶‍♂️ Project Walk-through

### 1. 🔧 Installing OpenSSL

Install OpenSSL via used system’s package manager. Example for Kali Linux is ussualy installed, but we can we use the following CLI commands:
- checking if OpenSSL is installed
```bash
openssl version
```
- Installing or updating OpenSSL
```bash
sudo apt update
sudo apt install openssl -y
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
openssl pkeyutl -encrypt -inkey public_key.pem -pubin -in plaintext.txt -out encrypted.txt
```

Encrypts the plaintext using the public key.

### 7. 📬 Decrypt the Message

```bash
openssl pkeyutl -decrypt -inkey private_key.pem -in encrypted.txt -out decrypted.txt
```

Decrypting the message using the private key and saves the result in `decrypted.txt`.

### 8. ✅ Verify

In this step I compared `decrypted.txt` with `plaintext.txt` to ensure the message was accurately decrypted.

## 📸 Screenshots

Screenshots demonstrating each step:

- Verifying OpenSSL version
  
![image](https://github.com/user-attachments/assets/1f16ee26-ee24-49db-b411-957442418316)

- Generating and verifying private key
  
![image](https://github.com/user-attachments/assets/d53cfdfb-00b7-4ab2-aaeb-5ed289e3a92f)

- Generating public key
  
![image](https://github.com/user-attachments/assets/e849f721-b2ba-445a-8303-0dbdbb6ca8e6)

- Writing a txt file containig a hidden message, encrypting the file, decrypting the file and checking the decrypted message
  
![image](https://github.com/user-attachments/assets/dd9adc93-cec8-437a-9f3e-941f1c3c1f3d)




## 📌 Conclusion

This project illustrates how asymmetric encryption works using OpenSSL and RSA. The steps show how to:
- Generate RSA key pairs
- Encrypt data using the public key
- Decrypt data using the private key
- Validate the process through file comparison
