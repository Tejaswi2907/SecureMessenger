# SecureMessenger
SecureMessenger is a web-based secure messaging application inspired by Telegram's dual-chat system. It supports both Secret Chats (end-to-end encrypted) and Cloud Chats (server-assisted delivery with encryption in transit). The app is built with a focus on cryptographic integrity, secure key exchange, and forward secrecy.

## 🚀 Features
•	**Secret Chats**: True end-to-end encryption using Diffie-Hellman key exchange and AES-256-IGE. The server cannot read or decrypt any messages.

•	**Cloud Chats**: Encrypted transport layer, server can decrypt and store messages for delivery across devices.

•	**Forward Secrecy**: Implements automatic re-keying after 100 messages or 7 days for Secret Chats.

•	**Real-Time Communication**: Built using WebSockets for live messaging.

•	**In-Memory Message Queuing**: Messages are temporarily stored if the recipient is offline (no persistent storage).

## 🛠 Tech Stack
**Frontend:**
•	HTML, TailwindCSS

•	Vanilla JavaScript
**Backend:**
•	Node.js with TypeScript

•	ws (WebSocket library)

•	crypto (built-in Node.js module for cryptography)
**Cryptographic Components:**
•	Diffie-Hellman key exchange

•	AES-256 encryption (IGE simulation)

•	SHA-256-based Key Derivation Function (KDF)

## 🔐 Chat Modes Explained
**Secret Chat**
•	Diffie-Hellman public key exchange

•	Shared key derived on client

•	Messages encrypted with AES-IGE using derived key

•	Server is unaware of message content
**Cloud Chat**
•	Auth key established via Diffie Hellman during login

•	Each message is encrypted with a derived key using SHA-256 and AES

•	Server decrypts, stores temporarily, and re-encrypts for the recipient

## 📦 How to Run Locally
1. **Clone the repo** and **cd SecureMessenger**

2. **Install dependencies**
**npm install**

3. **Run the app**
**npm run dev**

4. **Open two browser tabs to simulate users**

## 📘 Notes
•	No database is used — all message storage is ephemeral and in-memory.

•	Keys and payloads are logged to console for debugging/demo purposes.

