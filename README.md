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

🔐 Cookie Management

Session handling and authentication are simplified with cookie-parser. This ensures smooth handling of user authentication using cookies in HTTP requests
