# Elia-gardmanager (Backend) 

## 📋 Project Overview
Welcome to the Backend API for managing shifts and schedules!
This backend handles user authentication, CRUD operations on users, schedules, statuses, and switches, and validates the user shifts based on specific date ranges.

## 📱 Features
User Authentication: Login/logout via sessions.
CRUD operations:
Users (User)
Schedules (Schedule)
Statuses (Status)
Switches (Switch)
Switch Validation: Modify assigned users for a schedule within a date range.
Session Management: Uses express-session for storing sessions server-side.

## 📸 Project Preview

## 📂 Project Structure
```php
├── backend
│   ├── config
│   │   └── connection.js        # MongoDB connection
│   ├── controllers              # Controllers for CRUD operations
│   │   ├── schedule.controller.js
│   │   ├── status.controller.js
│   │   ├── switch.controller.js
│   │   └── user.controller.js
│   ├── models                   # Mongoose models
│   │   ├── schedule.js
│   │   ├── status.js
│   │   ├── switch.js
│   │   └── user.js
│   ├── routes                   # API routes
│   │   ├── schedule.routes.js
│   │   ├── status.routes.js
│   │   ├── switch.routes.js
│   │   └── user.routes.js
│   └── ...
├── .env                         # Environment configuration file (to be created)
├── package.json
└── server.js                    # Express entry point
```

## 🚀 Technologies Used
- Node.js for the server runtime.
- Express.js for API routing.
- MongoDB for data storage.
- Mongoose for MongoDB object modeling.
- express-session for managing user sessions.

## 🔧 Prerequisites and Installation

**Prerequisites**
- Node.js (version 14 or higher recommended)
- npm or yarn (for dependency management)

**Installation Steps**

Clone the repository
```bash
git clone https://github.com/<your-account>/Elia-gardManager.git
cd Elia-gardManager
```
Install dependencies
```bash
npm install
```

## ⚙️ Environment Configuration
Create a .env file at the root of the project (same level as package.json and server.js) and add the following:

```env
MONGO_URI=mongodb://<your-mongo-uri>
SESSION_SECRET=<your-session-secret>
```
MONGO_URI: The URL to your MongoDB database.
SESSION_SECRET: A secret key for encrypting sessions (used by express-session).
Note: Do not commit the .env file to a public repository. Ensure it's added to your .gitignore.

▶️ Launching the Application
After configuring your .env file, you can start the server with:

```bash
npm start
```
Or for development mode (if you have a dev script, e.g., via nodemon):

```bash
npm run dev
```
By default, the server runs on port 8000 (configurable in server.js).
You should see the following output in the console:

```bash
🐍 Server is running on port 8000
✅ Successfully connected to MongoDB!
```

## 🛠️ Usage and Endpoints
Once the server is running, you can test the routes using an API client like Postman, Insomnia, or a simple HTTP client. Below are the available endpoints:

**1. Users (/user)**

- POST /user: Create a new user
- POST /user/login: Log in a user
- GET /user/logout: Log out a user (removes session)
- GET /user/me: Get the currently logged-in user (via session)
- GET /user: Get a list of all users
- PUT /user/:id: Update a user (by ID)
- DELETE /user/:id: Delete a user (by ID)
**2. Schedules (/schedule)**
  
- POST /schedule: Create a new schedule
- GET /schedule: Get all schedules
- PUT /schedule/:id: Update a schedule (by ID)
- PUT /schedule: Validate a switch and update affected schedules (route validateSwitch)
- DELETE /schedule/:id: Delete a schedule (by ID)
**3. Statuses (/status)**
  
- POST /status: Create a new status
- GET /status: Get a list of all statuses
- PUT /status/:id: Update a status (by ID)
**4. Switches (/switch)**
  
- POST /switch: Create a new switch
- GET /switch: Get a list of all switches
- GET /switch/:id: Get the “balance” of days for a user
- PUT /switch/:id: Update a switch state (by ID)
- DELETE /switch/:id: Delete a switch (by ID)
  
## ✅ Tests and Verification
**To test the routes:**

- Install Postman (or another API client like Insomnia).
- Check the URL of your server (e.g., http://localhost:8000).
- Test each endpoint using the appropriate methods (POST, GET, PUT, DELETE).
- Pass the required data in req.body or req.params as per the documentation above.
  
**Example for creating a user via Postman:**

- Method: POST
URL: http://localhost:8000/user
- Headers:
- Content-Type: application/json
Body (raw, JSON):

```json
{
  "passWord": "myPassword",
  "fullName": "John Doe",
  "email": "john@example.com"
}
```

## 🔗 Frontend
This project works with the Elia-gardManager-backend.
Ensure that the frontend is running before launching the frontend.

## 🔗 Frontend Repo: 
[Elia GardManager Backend](https://github.com/Fauve-mce/elia-gardmanager-frontend)

## 🎥 Video Demo
Check out the video demo here: 
[Linkedin Post](https://www.linkedin.com/feed/update/urn:li:activity:7301037570862338049/)
