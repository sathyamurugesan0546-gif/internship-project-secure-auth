# Face Recognition File Encryptor  
### Secure File Encryption & Decryption using Face Authentication

## Internship Project (September 2024)

This project implements a secure file encryption and decryption system using **face recognition–based biometric authentication**. Files are encrypted for a specific user, and only the authenticated user whose face matches the registered biometric data can decrypt them.

The system combines **machine-learning-based face recognition** with **strong cryptographic encryption**, providing practical protection against unauthorized file access.

---

## Problem Statement

Traditional file security mechanisms rely on passwords or hardware tokens, which are vulnerable to being stolen, shared, forgotten, or compromised. When files are stored or transmitted through shared or cloud environments, the risk of third-party access increases.

This project addresses these issues by:
- Replacing password-based authentication with **biometric face recognition**
- Encrypting files so that **only the intended user can decrypt them**
- Preventing unauthorized access even if encrypted files are exposed

---

## Technologies Used

### Programming Language
- Python 3.11

### Machine Learning & Computer Vision
- `face_recognition` – deep-learning-based face embeddings
- `opencv-python` – webcam access and face capture
- `numpy`

### Cryptography
- `cryptography` library  
- **Fernet symmetric encryption** (AES-based)

### GUI & Utilities
- `tkinter` – graphical user interface
- `Pillow` – image handling
- `pickle` – storage of face encodings

---

## System Overview

1. User registers with a **username and facial data**
2. Facial features are converted into **face embeddings**
3. Face encodings are stored locally
4. Files are encrypted using **user-specific symmetric keys**
5. During decryption:
   - User is authenticated via live face recognition
   - Only the matching user can access the decryption key
   - File is decrypted securely

This ensures **authentication, verification, and validation** before file access.

---

## Methodology

### 1. Face Registration
- User’s face is captured via webcam
- Face is detected and encoded using the `face_recognition` library
- Encodings are stored along with the username using `pickle`

### 2. File Encryption
- User selects a recipient username and a file
- A unique **Fernet symmetric key** is generated
- File is encrypted and saved as:
username_filename.enc
- The encryption key is stored securely in a user-specific directory

### 3. Authentication & Decryption
- User authenticates by showing their face to the webcam
- Face embedding is compared with stored encodings
- If a match is found:
- The corresponding encryption key is loaded
- The file is decrypted successfully

### 4. Graphical User Interface
- Built using Tkinter
- Provides options for:
- User registration
- File encryption
- User authentication
- File decryption

---

## Project Structure

├── secure_file_auth.ipynb # Main implementation

├── users_face.pkl # Stores usernames and face encodings

├── keys_face/ # Stores user-specific encryption keys

│ └── username.key

├── encrypted_files/

│ └── username_filename.enc

---

## Features

- Biometric authentication using face recognition
- Strong symmetric file encryption (Fernet / AES)
- Multi-user support
- User-specific access control
- Simple and intuitive GUI
- Protection against unauthorized file access

---

## Results

- Multiple users can register and be recognized accurately
- Files can only be decrypted by the intended user
- Encrypted files remain secure even if accessed by third parties
- Demonstrates a practical and efficient biometric security system

---

## Conclusion

This project demonstrates a practical approach to secure file protection by integrating **face recognition-based authentication** with **cryptographic encryption**. By eliminating password dependency and enforcing biometric validation, the system improves data security while maintaining usability.

---

## Future Enhancements

- Anti-spoofing and liveness detection
- Secure remote key management
- Cloud deployment
- Improved GUI and scalability
- Multi-factor authentication support
