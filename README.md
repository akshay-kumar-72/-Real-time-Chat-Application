# -Real-time-Chat-Application
📡 Real-time Chat Application
A real-time chat application that enables scalable messaging with features like group chats, message persistence, and instant delivery using Socket.IO and MongoDB.

🔧 Tech Stack
Backend Framework: Express.js

Runtime: Node.js

Database: MongoDB

Real-time Communication: Socket.IO

📁 Project Structure
pgsql
Copy
Edit
realtime-chat-app/
├── server.js
├── .env
├── models/
│   └── Message.js
├── routes/
│   └── messageRoutes.js
├── package.json
└── README.md
⚙️ Setup Instructions
1. Clone the repository
bash
Copy
Edit
git clone https://github.com/your-username/realtime-chat-app.git
cd realtime-chat-app
2. Install dependencies
bash
Copy
Edit
npm install
3. Create .env file
Create a .env file in the root directory and add your MongoDB URI and port:

env
Copy
Edit
PORT=5000
MONGO_URI=mongodb://localhost:27017/chatapp
You can use MongoDB Atlas for cloud database hosting.

4. Run the server
bash
Copy
Edit
npm start
The server will start on http://localhost:5000.

🔌 Socket.IO Events
joinRoom: Join a specific chat room

sendMessage: Send a new message

receiveMessage: Listen for new incoming messages in real time

🛠 API Endpoints
Method	Endpoint	Description
GET	/api/messages/:room	Fetch messages for a room

🧠 Message Schema
js
Copy
Edit
{
  sender: String,
  content: String,
  room: String,
  timestamp: Date (default: now)
}
💬 Frontend Integration Example
Include Socket.IO in your frontend and use:

html
Copy
Edit
<script src="https://cdn.socket.io/4.0.0/socket.io.min.js"></script>
<script>
  const socket = io("http://localhost:5000");

  socket.emit("joinRoom", "room1");

  socket.on("receiveMessage", (message) => {
    console.log("Received:", message);
  });

  function sendMessage() {
    socket.emit("sendMessage", {
      sender: "Alice",
      content: "Hello!",
      room: "room1"
    });
  }
</script>
🧪 Future Improvements
User authentication (JWT)

Group creation and management

File/image sharing

Online/offline indicators

Deployment with Docker

📃 License
This project is licensed under the MIT License.
