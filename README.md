# Real Estate API

A RESTful backend API for real-estate marketing platforms, built with **Node.js, Express.js, and MongoDB**.

The project provides the backend foundation for managing real-estate projects, buildings, floors, units, users, roles, orders, and related resources through a structured REST API.

## ✨ Features

* 🏠 Real-estate project management
* 🏢 Building and floor management
* 🏘️ Unit management
* 👤 User management
* 🔐 JWT-based authentication
* 🛡️ Role-based authorization
* 🔑 Password hashing with bcrypt
* 🗄️ MongoDB integration with Mongoose
* 🌐 CORS support
* 📦 Environment-based configuration
* 🧾 Invoice generation
* 📮 Postman collection for API testing
* 🧩 Modular controllers, models, routes, and middleware

## 🛠️ Tech Stack

| Technology  | Purpose                       |
| ----------- | ----------------------------- |
| Node.js     | JavaScript runtime            |
| Express.js  | REST API framework            |
| MongoDB     | Database                      |
| Mongoose    | MongoDB ODM                   |
| JWT         | Authentication                |
| bcryptjs    | Password hashing              |
| dotenv      | Environment configuration     |
| CORS        | Cross-origin resource sharing |
| EasyInvoice | Invoice generation            |
| Validator   | Data validation               |
| Nodemon     | Development server            |

## 📁 Project Structure

```text
real-state-api/
│
├── controllers/
│   ├── projectControllers/
│   │   ├── build.js
│   │   ├── floor.js
│   │   ├── project.js
│   │   └── unit.js
│   ├── index.js
│   ├── order.js
│   ├── roles.js
│   ├── urls.js
│   └── users.js
│
├── middlewares/
│
├── models/
│   ├── projectModels/
│   │   ├── build.js
│   │   ├── floor.js
│   │   ├── projects.js
│   │   └── unit.js
│   ├── connect.js
│   ├── order.js
│   ├── role.js
│   ├── urls.js
│   └── user.js
│
├── routes/
│   ├── projectRoutes/
│   │   ├── build.js
│   │   ├── floor.js
│   │   ├── project.js
│   │   └── unit.js
│   └── index.js
│
├── public/
├── .gitignore
├── index.js
├── package.json
├── package-lock.json
└── real.postman_collection.json
```

The repository currently follows a controller/model/route separation, with dedicated modules for real-estate projects and their related building, floor, and unit resources.

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

* [Node.js](https://nodejs.org/)
* MongoDB
* npm

### 1. Clone the repository

```bash
git clone https://github.com/khaledhelmyg/real-state-api.git

cd real-state-api
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env` file in the project root:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
```

> Use the variable names expected by the application's database and authentication configuration.

### 4. Start the development server

```bash
npm start
```

The project uses Nodemon during development and starts the application through `index.js`.

The API will be available at:

```text
http://localhost:5000
```

## 🔐 Authentication

The API uses **JSON Web Tokens (JWT)** for authentication.

Typical authentication flow:

```text
Client
   │
   │ Login
   ▼
API
   │
   │ Validate credentials
   ▼
MongoDB
   │
   │ Generate JWT
   ▼
Client
   │
   │ Authorization: Bearer <token>
   ▼
Protected API
```

Passwords are hashed using `bcryptjs` rather than being stored as plain text.

## 👥 Authorization

The application includes role-related controllers and models, allowing authorization rules to be separated from the authentication layer.

This structure makes it possible to define different permissions for different user roles.

```text
User
 │
 ├── Authentication
 │
 ├── JWT
 │
 └── Role
      │
      └── Authorization
```

## 🏗️ Real Estate Domain

The project organizes real-estate resources hierarchically.

```text
Project
   │
   ├── Building
   │      │
   │      └── Floor
   │             │
   │             └── Unit
   │
   └── Other project information
```

Dedicated controllers, models, and routes exist for projects, buildings, floors, and units.

## 🗄️ Database

The API uses **MongoDB** through **Mongoose**.

Database connection logic is located under:

```text
models/connect.js
```

Domain models are separated into individual modules, making the database layer easier to maintain and extend.

## 📮 API Testing

A Postman collection is included in the repository:

```text
real.postman_collection.json
```

You can import this file into Postman to test the available API requests.

## ⚙️ Available Scripts

### Development

```bash
npm start
```

Runs the application using Nodemon.

## 🔒 Environment & Security

Never commit sensitive configuration to the repository.

Keep secrets such as:

```env
MONGO_URI=...
JWT_SECRET=...
```

inside `.env` and make sure `.env` is excluded through `.gitignore`.

For production environments, use a proper secrets-management solution instead of committing credentials to source control.

## 🚀 Production Considerations

Before deploying this API to production, consider adding:

* Request validation at the API boundary
* Centralized error handling
* Structured logging
* Rate limiting
* Security headers
* API versioning
* Request/response documentation
* Automated tests
* Health/readiness endpoints
* Database indexes
* MongoDB connection monitoring
* Graceful shutdown handling
* Production process management
* CI/CD pipeline
* Dependency and vulnerability scanning

## 🧪 Testing Strategy

A production-ready implementation should cover at least:

```text
Authentication
├── Login
├── Invalid credentials
└── Unauthorized requests

Users
├── Create
├── Read
├── Update
└── Authorization

Projects
├── Create
├── Read
├── Update
└── Delete

Buildings
├── Create
├── Read
└── Update

Floors
├── Create
├── Read
└── Update

Units
├── Create
├── Read
├── Update
└── Availability
```

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a feature branch.

```bash
git checkout -b feature/your-feature
```

3. Make your changes.
4. Commit your changes.

```bash
git commit -m "feat: add your feature"
```

5. Push the branch.

```bash
git push origin feature/your-feature
```

6. Open a Pull Request.

## 📄 License

This project is currently published under the **ISC License** as specified in `package.json`.

## 👨‍💻 Author

**Khaled Helmy**

GitHub:
https://github.com/khaledhelmyg

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

Repository:

https://github.com/khaledhelmyg/real-state-api
