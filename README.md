# NovaChat

NovaChat is a full-stack chat and video-calling application built with React, Vite, Express, MongoDB, Stream Chat, and Stream Video.

## Live Demo

Try the deployed application: [NovaChat](https://novachat-video-calls-app.onrender.com/login)

## Features

- User registration and login
- JWT-based authentication with HTTP-only cookies
- User onboarding and profile management
- Friend requests and friend lists
- Real-time chat
- One-to-one video calls
- Theme selection
- Production serving of the built frontend from the backend

## Tech Stack

- **Frontend:** React, Vite, React Router, Tailwind CSS, DaisyUI, Zustand
- **Backend:** Node.js, Express, MongoDB, Mongoose, JWT
- **Communication:** Stream Chat and Stream Video

## Requirements

- Node.js 18 or newer
- npm
- A MongoDB database
- A Stream account with chat and video credentials

## Setup

1. Clone the repository and enter the project directory.

2. Install dependencies for both applications:

   ```bash
   npm run build
   ```

3. Create `backend/.env` with the values required by the server:

   ```env
   PORT=5001
   NODE_ENV=development
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET_KEY=your_jwt_secret
   STEAM_API_KEY=your_stream_api_key
   STEAM_API_SECRET=your_stream_api_secret
   ```

   The backend currently reads the Stream credentials using the `STEAM_*` names shown above.

4. Create `frontend/.env`:

   ```env
   VITE_STREAM_API_KEY=your_stream_api_key
   ```

## Development

Run the backend and frontend in separate terminals.

### Backend

```bash
cd backend
npm run dev
```

The API runs at `http://localhost:5001` by default.

### Frontend

```bash
cd frontend
npm run dev
```

The frontend runs at `http://localhost:5173`.

## Production

Build the frontend and install the application dependencies from the project root:

```bash
npm run build
```

Start the backend in production mode:

```bash
npm start
```

Set `NODE_ENV=production` so the backend serves the frontend build from `frontend/dist`.

## Useful Commands

| Command                             | Description                                                  |
| ----------------------------------- | ------------------------------------------------------------ |
| `npm run build`                     | Install backend/frontend dependencies and build the frontend |
| `npm start`                         | Start the backend server                                     |
| `npm run dev --prefix backend`      | Start the backend with Nodemon                               |
| `npm run dev --prefix frontend`     | Start the Vite development server                            |
| `npm run lint --prefix frontend`    | Run frontend ESLint checks                                   |
| `npm run preview --prefix frontend` | Preview the production frontend build                        |

## Project Structure

```text
NovaChat-video-calls-app/
├── backend/
│   └── src/
│       ├── controllers/   # Authentication, chat, and user logic
│       ├── lib/           # Database and Stream integrations
│       ├── middleware/    # Authentication middleware
│       ├── models/        # MongoDB models
│       ├── routes/        # API routes
│       └── server.js      # Express entry point
├── frontend/
│   └── src/
│       ├── components/    # Shared UI components
│       ├── hooks/         # Authentication and data hooks
│       ├── lib/           # API and utility helpers
│       ├── pages/         # Application pages
│       └── store/         # Zustand stores
└── package.json           # Root scripts
```

## Security

Do not commit `.env` files or expose MongoDB, JWT, or Stream secrets. Use separate credentials for development and production environments.
