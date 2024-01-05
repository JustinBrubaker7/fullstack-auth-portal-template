# FullStack Auth Portal Template

This template provides a full-stack application with authentication functionality. It uses a React frontend with Vite for a fast and efficient development experience, and an Express.js backend for handling API requests.

## Frontend

The frontend is located in the `client` directory. It uses React for UI and Vite for bundling and development server. The main entry point of the application is `client/src/main.jsx`, which renders the `App` component from `client/src/App.jsx`.

The `App` component sets up the routing for the application using `react-router-dom`. It includes routes for login, sign up, and home pages. The home page is protected by a `PrivateRoute` component, which checks if the user is logged in before rendering the page.

The application state related to authentication is managed using a React context, defined in `client/src/context/auth-context.jsx`. This context provides functions for logging in, logging out, signing up, and getting the current user.

The login and sign up pages are located in `client/src/pages/Login.jsx` and `client/src/pages/SignUp.jsx` respectively. They both use forms to collect user input, and call the appropriate functions from the auth context when the form is submitted.

## Backend

The backend is located in the `server` directory. It uses Express.js for handling API requests, and JWT for authentication.

The main entry point of the server is `server/app.js`, which sets up middleware, routes, and starts the server listening on a port.

The routes for authentication are defined in `server/routes/auth.js`, which includes routes for registering and logging in. These routes use the `register` and `login` functions from `server/controllers/authController.js`.

The `register` function checks if a user with the given email already exists, hashes the password, and creates a new user. The `login` function checks if the user exists and if the password is correct, and then creates a JWT token for the user.

## Running the Project

To run the project, you need to start both the frontend and the backend servers. You can do this by running the following commands in separate terminal windows:

```sh
# Start the frontend server
cd client
npm install
npm run dev

# Start the backend server
cd server
npm install
npm start