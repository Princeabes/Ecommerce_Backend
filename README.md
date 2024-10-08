🚀 E-Commerce Backend API

Welcome to the E-Commerce Backend API, a robust and scalable backend server designed for modern e-commerce platforms. This server supports user authentication, product management, and order processing—everything you need to get your e-commerce app up and running!

🛠️ Technologies Used

Node.js: Fast and lightweight JavaScript runtime.
Express.js: Web framework to manage API routing and HTTP requests.
MongoDB: NoSQL database for seamless data storage.
Mongoose: Elegant MongoDB object modeling for Node.js.
dotenv: For environment configuration management.
CORS: Cross-Origin Resource Sharing for frontend-backend integration.
cookie-parser: Easy cookie handling for session and auth management.

⚙️ Getting Started

Prerequisites
Before you get started, make sure you have the following tools installed:

Node.js
MongoDB (either locally or cloud-based)
npm

Installation Steps
1. Clone the repository:
   git clone https://github.com/Princeabes/Ecommerce_Backend.git
cd your-repo-name

2. Install Dependencies:
  npm install


3. Configure Environment Variables: Create a .env file inside the config/ directory and fill in your values: 
      PORT=9000
    MONGODB_URI=your-mongodb-uri
    JWT_SECRET=your-jwt-secret


4. Set Up MongoDB: Ensure MongoDB is up and running and then configure the connection in the connect.js file:
   const mongoose = require("mongoose");

  mongoose.connect(process.env.MONGODB_URI, {
    useNewUrlParser: true,
    useUnifiedTopology: true,
    })
      .then(() => console.log("MongoDB connected successfully"))
      .catch((error) => console.log(`MongoDB connection error: ${error.message}`));

  Start the Application 🚀
    node index.js
    node server.js
  The backend server will be live at http://localhost:9000.
  📚 API Endpoints

User Management (/api/users)

  POST /register – Register a new user.
  POST /login – Log in an existing user.
  Product Management (/api/products)
  GET / – Fetch all products.
  POST / – Add a new product.
  Order Management (/api/orders)
  POST /create – Create a new order.
  GET / – Get all orders for the current user.
Share


You said:
const express = require("express");
const cors = require("cors");
const cookieParser = require("cookie-parser");
const user = require("./routes/userRoutes");
const product = require("./routes/productRoutes.js")
const order = require("./routes/orderRoutes.js")
require("./connect.js");

const app = express();
app.use(
  cors({
    origin: "http://localhost:3000",
    credentials: true,
  })
);

// Handling Uncaught Exception
process.on("uncaughtException", (err) => {
  console.log(Error: ${err.message});
  console.log(Shutting down the server due to Uncaught Exception);
  process.exit(1);
});

// Config

  require("dotenv").config({ path: "./config/.env" });


app.use(express.json());
app.use(express.urlencoded({ extended: true })); // Replaced bodyParser with express.urlencoded
app.use(cookieParser());

app.use("/api", user);
app.use("/api",product);
app.use("/api",order);

PORT = process.env.PORT || 9000
app.listen(PORT, ()=> console.log(Server Started on port no. ${PORT}));
write readme.md file for this 
ChatGPT said:

ChatGPT
Here’s a sample README.md for your project:

E-Commerce Backend API

This project is a backend server for an e-commerce platform built using Node.js and Express. It handles user authentication, product management, and order processing. The server also supports Cross-Origin Resource Sharing (CORS) and uses cookies for session management.

Technologies Used

Node.js: JavaScript runtime for building the backend server.
Express.js: Web framework for Node.js.
MongoDB: NoSQL database used for data storage.
Mongoose: ODM (Object Data Modeling) library for MongoDB.
dotenv: Loads environment variables from a .env file.
CORS: Middleware to allow Cross-Origin Resource Sharing.
cookie-parser: Parses cookies in HTTP requests.
Setup Instructions

Prerequisites
Node.js installed on your system.
MongoDB instance running locally or on the cloud.
npm (Node package manager).
Installation
Clone the repository:
bash
Copy code
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
Install the required dependencies:
bash
Copy code
npm install
Create a .env file in the config directory with the following variables:
bash
Copy code
PORT=9000
MONGODB_URI=your-mongodb-connection-string
JWT_SECRET=your-secret-key
Set up MongoDB connection in connect.js file:
javascript
Copy code
const mongoose = require("mongoose");

mongoose.connect(process.env.MONGODB_URI, {
  useNewUrlParser: true,
  useUnifiedTopology: true,
})
.then(() => console.log("MongoDB connected"))
.catch((error) => console.log(`MongoDB connection error: ${error.message}`));
Running the Application
To start the server, run:
bash
Copy code
npm start
or

bash
Copy code
node server.js
The server should be running at http://localhost:9000.
API Endpoints

User Routes (/api/users)
POST /register: Register a new user.
POST /login: Log in a user.
Product Routes (/api/products)
GET /: Get all products.
POST /: Add a new product.
Order Routes (/api/orders)
POST /create: Create a new order.
GET /: Get all orders for the logged-in user.
Error Handling

The app has an error handler for uncaught exceptions:
javascript
Copy code
process.on("uncaughtException", (err) => {
  console.log(`Error: ${err.message}`);
  console.log("Shutting down the server due to Uncaught Exception");
  process.exit(1);
});
License

This project is licensed under the MIT License.

Feel free to modify it based on your exact requirements or folder structure!






You said:
write In such a way it is attracti
ChatGPT said:

ChatGPT
Here’s an enhanced version of your README.md to make it more attractive, engaging, and easier to read:

🚀 E-Commerce Backend API

Welcome to the E-Commerce Backend API, a robust and scalable backend server designed for modern e-commerce platforms. This server supports user authentication, product management, and order processing—everything you need to get your e-commerce app up and running!

🛠️ Technologies Used

Node.js: Fast and lightweight JavaScript runtime.
Express.js: Web framework to manage API routing and HTTP requests.
MongoDB: NoSQL database for seamless data storage.
Mongoose: Elegant MongoDB object modeling for Node.js.
dotenv: For environment configuration management.
CORS: Cross-Origin Resource Sharing for frontend-backend integration.
cookie-parser: Easy cookie handling for session and auth management.
⚙️ Getting Started

Prerequisites
Before you get started, make sure you have the following tools installed:

Node.js
MongoDB (either locally or cloud-based)
npm
Installation Steps
Clone the repository:
bash
Copy code
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
Install Dependencies:
bash
Copy code
npm install
Configure Environment Variables: Create a .env file inside the config/ directory and fill in your values:
bash
Copy code
PORT=9000
MONGODB_URI=your-mongodb-uri
JWT_SECRET=your-jwt-secret
Set Up MongoDB: Ensure MongoDB is up and running and then configure the connection in the connect.js file:
javascript
Copy code
const mongoose = require("mongoose");

mongoose.connect(process.env.MONGODB_URI, {
  useNewUrlParser: true,
  useUnifiedTopology: true,
})
.then(() => console.log("MongoDB connected successfully"))
.catch((error) => console.log(`MongoDB connection error: ${error.message}`));
Start the Application 🚀
Run the following command to start the server:
bash
Copy code
npm start
or

bash
Copy code
node server.js
The backend server will be live at http://localhost:9000.
📚 API Endpoints

User Management (/api/users)
POST /register – Register a new user.
POST /login – Log in an existing user.
Product Management (/api/products)
GET / – Fetch all products.
POST / – Add a new product.
Order Management (/api/orders)
POST /create – Create a new order.
GET / – Get all orders for the current user.
🛑 Error Handling

In case of any uncaught exceptions, the server will gracefully shut down:

javascript
Copy code
process.on("uncaughtException", (err) => {
  console.error(`Error: ${err.message}`);
  console.error("Shutting down the server due to an Uncaught Exception");
  process.exit(1);
});
🌍 Cross-Origin Resource Sharing (CORS)

The backend API is set up to allow requests from the frontend (typically React or similar apps):

javascript
Copy code
app.use(
  cors({
    origin: "http://localhost:3000", // Your frontend URL
    credentials: true,
  })
);
🔐 Cookie Management

Session handling and authentication are simplified with cookie-parser. This ensures smooth handling of user authentication using cookies in HTTP requests.
