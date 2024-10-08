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
git clone https://github.com/Princeabes/Ecommerce_Backend.git
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
node index.js
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
