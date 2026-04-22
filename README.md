# 📡 Real-Time Chat Application using Spring Boot WebSocket & React (Vite)

## 📌 Experiment Title
**Implementation of Real-Time Chat System using WebSockets (STOMP Protocol) with Spring Boot and React**

---

## 📖 Description
This experiment demonstrates the development of a **real-time chat application** using Spring Boot WebSocket on the backend and React (Vite) on the frontend.

The system enables multiple clients to communicate instantly without refreshing the page by establishing a persistent **WebSocket connection**. Communication follows the **STOMP (Simple Text Oriented Messaging Protocol)** over WebSocket.

Messages sent by one user are broadcast to all connected users via a message broker.

---

## 🎯 Objectives
- Understand WebSocket communication  
- Implement STOMP protocol in Spring Boot  
- Enable real-time messaging between multiple clients  
- Integrate frontend (React) with backend WebSocket server  

---

## 🏗️ System Architecture

### 🔹 Backend (Spring Boot)

**WebSocketConfig.java**
- Enables WebSocket message broker  
- Defines:
  - `/app` → client sends messages  
  - `/topic` → server broadcasts messages  
- Endpoint: `/ws`  

**ChatController.java**
- Handles incoming messages (`/app/chat`)  
- Broadcasts to `/topic/messages`  

**Message.java**
- Model class with:
  - `sender`
  - `content`

**DemoWebSocketApplication.java**
- Main Spring Boot application  

---

### 🔹 Frontend (React + Vite)

- Uses WebSocket/STOMP client  

**Components:**
- `Chat.jsx` → Main chat UI  
- `MessageInput.jsx` → Input field  
- `MessageList.jsx` → Display messages  

**Polyfills used:**
```js
window.global = window;
window.Buffer = Buffer;
window.process = process;
```
🔄 Working Flow

Client connects to WebSocket endpoint:

http://localhost:8080/ws

Client sends message to:

/app/chat

Spring Boot processes message via:

@MessageMapping("/chat")

Message is broadcast to:

/topic/messages
All subscribed clients receive the message instantly
⚙️ Technologies Used
🔹 Backend
Java
Spring Boot
WebSocket
STOMP Protocol
🔹 Frontend
React (Vite)
JavaScript
SockJS
STOMP.js
▶️ How to Run the Project
🔹 Backend
mvn spring-boot:run

Server starts at:
http://localhost:8080

🔹 Frontend
cd websocket
npm install
npm run dev

Open:
http://localhost:5173

📊 Output
Users can send messages in real-time
Messages are instantly visible to all connected clients
No page refresh required
📸 Screenshots

The following screenshots demonstrate real-time communication between multiple clients along with server-side message handling.

🔹 Chat Interface (User 1)

User "Sakshi" sending messages
Real-time chat functionality

🔹 Chat Interface (User 2)

User "Manya" receiving messages
Demonstrates multi-user communication
🔹 Backend Console Output

Displays messages received on the server
Confirms WebSocket communication is working
📁 Project Structure
Demo_WebSocket/
├── screenshots/
│   ├── chat-interface-user1.png
│   ├── chat-interface-user2.png
│   └── backend-console-output.png
├── README.md
├── backend (Spring Boot)
└── frontend (React - Vite)
📌 Key Concepts Learned
WebSocket vs HTTP
STOMP messaging protocol
Publish-Subscribe model
Real-time frontend-backend integration
🚀 Conclusion

This experiment successfully demonstrates how to build a low-latency, real-time communication system using WebSockets. It highlights the efficiency of persistent connections over traditional request-response models and showcases modern full-stack integration using Spring Boot and React.
window.global = window;
window.Buffer = Buffer;
window.process = process;
