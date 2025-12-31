# Random Ideas

A full-stack web application for capturing, sharing, and managing random ideas. Built with Node.js, Express, MongoDB, and a modern JavaScript frontend using Webpack.

Deployed at https://randomideas-app-wouo.onrender.com/

<img src="./random-ideas.png" />

## Features

- **CRUD Operations**: Create, read, update, and delete ideas
- **User Authentication**: Username-based authorization for editing/deleting ideas
- **RESTful API**: Clean API endpoints for idea management
- **Responsive Frontend**: Modern web interface with modal forms and dynamic lists
- **MongoDB Integration**: Persistent data storage with Mongoose ORM

## Tech Stack

### Backend

- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **CORS** - Cross-origin resource sharing
- **dotenv** - Environment variable management

### Frontend

- **JavaScript (ES6+)** - Client-side logic
- **Webpack** - Module bundler and build tool
- **Babel** - JavaScript transpiler
- **Axios** - HTTP client for API calls
- **FontAwesome** - Icons and UI elements
- **CSS** - Styling and responsive design

## API Endpoints

| Method | Endpoint         | Description                              |
| ------ | ---------------- | ---------------------------------------- |
| GET    | `/api/ideas`     | Get all ideas                            |
| GET    | `/api/ideas/:id` | Get single idea by ID                    |
| POST   | `/api/ideas`     | Create new idea                          |
| PUT    | `/api/ideas/:id` | Update idea (requires matching username) |
| DELETE | `/api/ideas/:id` | Delete idea (requires matching username) |

### Request/Response Format

#### Idea Object

```json
{
  "_id": "string",
  "text": "string (required)",
  "tag": "string",
  "username": "string",
  "date": "ISO date string"
}
```

## Prerequisites

- Node.js
- MongoDB (local installation or cloud service like MongoDB Atlas)
- npm package manager

## Installation & Setup

1. **Clone the repository**

   ```bash
   git clone https://github.com/philipstubbs13/randomideas-app
   cd randomideas-app
   ```

2. **Install backend dependencies**

   ```bash
   npm install
   ```

3. **Set up environment variables**

   Create a `.env` file in the root directory:

   ```env
   PORT=5001
   MONGO_URI=mongodb://localhost:27017/randomideas
   # Or for MongoDB Atlas: mongodb+srv://username:password@cluster.mongodb.net/randomideas
   ```

4. **Start MongoDB**

   If running locally:

   ```bash
   mongod
   ```

5. **Install frontend dependencies**
   ```bash
   cd client
   npm install
   cd ..
   ```

## Running the Application

### Development Mode

1. **Start the backend server**

   ```bash
   npm run dev
   ```

   Server runs on http://localhost:5001

2. **Start the frontend development server**
   ```bash
   cd client
   npm run dev
   ```
   Frontend runs on http://localhost:3000

### Production Mode

1. **Build the frontend**

   ```bash
   cd client
   npm run build
   cd ..
   ```

2. **Start the server**
   ```bash
   npm start
   ```

## Project Structure

```
randomideas-api/
├── client/                 # Frontend application
│   ├── src/
│   │   ├── components/     # React-like components
│   │   ├── css/           # Stylesheets
│   │   └── index.js       # Entry point
│   ├── package.json
│   └── webpack.config.js
├── config/
│   └── db.js              # Database connection
├── models/
│   └── Idea.js           # Mongoose schema
├── public/                # Static files
├── routes/
│   └── ideas.js          # API routes
├── server.js              # Express server
├── package.json
├── .env                   # Environment variables (create this)
└── README.md
```

## Usage

1. Open your browser to the frontend URL (http://localhost:3000 in dev mode)
2. Add new ideas using the form modal
3. View all ideas in the list
4. Edit or delete your own ideas (username matching required)

## Development

### Available Scripts

#### Backend

- `npm start` - Start production server
- `npm run dev` - Start development server with nodemon

#### Frontend

- `npm run build` - Build for production
- `npm run dev` - Start development server

### Adding New Features

1. **Backend**: Add new routes in `routes/` and models in `models/`
2. **Frontend**: Create new components in `client/src/components/`
3. **Styling**: Add CSS in `client/src/css/`

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## Project Structure (Client-side)

- `client/src/index.js`: The main entry point for the client-side application.
- `client/src/components/`: Contains individual UI components (for example, `IdeaForm`, `IdeaList`, `Modal`).
- `client/src/css/style.css`: Global styles for the application.
- `client/src/utils/`: (Optional) For utility functions.
- `client/src/services/`: (Optional) For API interaction logic.

## Contributing

Feel free to fork this repository, make improvements, and submit pull requests.
