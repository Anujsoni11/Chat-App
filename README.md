# 💬 Real-Time Chat Application

A real-time **room-based chat application** built using **Node.js, Express.js, Socket.io, MongoDB, Mongoose, and EJS**.

Users can join a chat room, send messages in real time, see when another user is typing, and access previous messages even after refreshing the page.

## 🚀 Features

* 💬 Real-time messaging using **Socket.io**
* 🚪 Room-based chat system
* 👤 Username-based messaging
* ⌨️ Real-time typing indicator
* 💾 Messages stored in **MongoDB**
* 🔄 Previous messages loaded after page refresh
* 🎯 Messages are broadcast only to users in the same room
* 🖥️ Server-side rendering using **EJS**

## 🛠️ Tech Stack

**Backend**

* Node.js
* Express.js

**Real-Time Communication**

* Socket.io

**Database**

* MongoDB
* Mongoose

**Frontend**

* HTML
* EJS
* JavaScript

## 📁 Project Structure

```text
chat-app/
│
├── config/
│   └── database-config.js
│
├── models/
│   └── chat.js
│
├── public/
│   ├── index.html
│   └── script.js
│
├── views/
│   └── index.ejs
│
├── .gitignore
├── index.js
└── package.json
```

## ⚙️ Installation

Clone the repository:

```bash
git clone <your-repository-url>
cd <your-project-folder>
```

Install dependencies:

```bash
npm install
```

Make sure **MongoDB** is running locally.

The application currently connects to:

```text
mongodb://localhost/chatapp
```

Start the server:

```bash
npm start
```

The application will run on:

```text
http://localhost:3000
```

## 💬 How It Works

Users join a room using a unique **Room ID**.

For example:

```text
http://localhost:3000/chat/room1
```

Anyone opening the same room URL can communicate with other users in that room.

When a user sends a message:

```text
Client
   ↓
msg_send
   ↓
Socket.io Server
   ↓
Save Message → MongoDB
   ↓
msg_rcvd
   ↓
Users in Same Room
```

## 🔌 Socket Events

### `join_room`

Joins the user to a specific chat room.

### `msg_send`

Sends the user's message, username, and room ID to the server.

### `msg_rcvd`

Broadcasts the new message to users connected to the same room.

### `typing`

Notifies the server that a user is typing.

### `someone_typing`

Notifies other users in the room that someone is currently typing.

## 🗄️ Message Schema

Each chat message is stored with:

```javascript
{
  content: String,
  user: String,
  roomId: String
}
```

This allows messages to be retrieved according to their chat room.

## 🔮 Future Improvements

* Authentication and user accounts
* Better chat UI
* Private messaging
* Online/offline user status
* Message timestamps
* Delete/edit messages
* Multiple chat-room dashboard
* Deployment with a cloud MongoDB database

## 👨‍💻 Author

**Anuj Soni**

B.Tech Student at IIIT Ranchi
Backend & Full-Stack Developer