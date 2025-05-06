# Prototype Implementation of a Public Key Distribution Authority

This project demonstrates a **Proof of Concept** for a **Public Key Distribution Authority (PKDA)** — a centralized service that facilitates secure distribution of public keys between users for encrypted communication in a network.

It is implemented in Python using socket programming to simulate communication between a PKDA server and two clients.

---

## 🔐 What is a Public Key Distribution Authority?

A Public Key Distribution Authority is a **trusted third-party entity** that:
- Maintains a database of registered users and their public keys
- Authenticates users upon request
- Distributes public keys of users securely to requesting clients

This mechanism helps avoid **Man-in-the-Middle (MITM)** attacks by ensuring that users receive authentic public keys from a trusted authority.

---

## 🧪 How It Works

1. **PKDA Server** starts and listens for client connections.
2. **Client A** or **Client B** connects and requests the public key of the other client.
3. PKDA:
   - Authenticates the request
   - Sends back the requested public key securely
4. Clients can now use the received key for secure encrypted communication.

---

## 🚀 How to Run

### 1. Clone the Repository

### 2. Install Python Requirements

This project uses the built-in `socket`, `os`, and `cryptography` libraries.

To install the required module:

```bash
pip install cryptography
```

### 3. Generate RSA Key Pairs (if not already present)

Use `cryptography` to generate keys or use the ones already available in the `keys/` folder.

---

### 4. Run PKDA Server

```bash
python pkda_server.py
```

This will start the Public Key Distribution Authority on a predefined port (e.g., `12345`).

### 5. Run Client A and Client B in separate terminals

```bash
python client_A.py
```

```bash
python client_B.py
```

Each client will:
- Connect to the PKDA server
- Request the public key of the other
- Receive and display the key securely

---

## 🔑 Sample Interaction

Client A output:

```
[INFO] Connected to PKDA
[INFO] Requested public key of B
[SUCCESS] Received public key of B:
-----BEGIN PUBLIC KEY-----
...
-----END PUBLIC KEY-----
```

---

## ✅ Features

- Simulates secure public key distribution
- Demonstrates RSA key generation and usage
- Uses file-based key storage
- Simple socket-based client-server architecture

---

## 📚 Educational Use

This project is intended for **educational purposes** to help understand:
- The concept of centralized key distribution
- Role of PKDA in secure communication
- Basic RSA public/private key handling

> ⚠️ This is a **proof of concept** only. It lacks encryption, mutual authentication, and advanced security checks that would be required in real-world PKI systems.

---
