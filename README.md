Food Delivery Website with Real‑time Map Tracking (MERN Stack)

A full‑stack food delivery web application built using the MERN stack (MongoDB, Express.js, React.js, Node.js), integrating Google authentication and Razorpay payments, and featuring live tracking of delivery via a map view.

🚀 Table of Contents

Features

Tech Stack

Getting Started

Prerequisites

Installation

Running Locally

Project Structure

Usage

Environment Variables

Payment & Authentication

Live Tracking

Deployment

Contributing

License

Features

User registration / login via Google OAuth

Browse restaurants, menus, add items to cart

Place orders and pay via Razorpay integration

Real‑time map tracking of delivery (courier location updates)

Order history, user profile

Admin / merchant panel (optional) for managing restaurants/orders

Responsive UI (desktop + mobile)

Tech Stack

Frontend: React.js (hooks + context or Redux)

Backend: Node.js + Express.js

Database: MongoDB (Atlas or local)

Auth: Google OAuth 2.0

Payments: Razorpay API

Real‑Time: WebSockets / Socket.io for live updates

Maps/Tracking: Google Maps API (or Mapbox)

Deployment: Vercel (frontend) + Heroku / DigitalOcean / AWS (backend)

Getting Started
Prerequisites

Node.js (v14 + recommended)

MongoDB database (local or cloud via MongoDB Atlas)

Google Cloud project with OAuth credentials + Maps API key

Razorpay account and API key/secret

Installation
# Clone repository
git clone https://github.com/your‑username/food‑delivery‑mern.git
cd food‑delivery‑mern

# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install

Running Locally
# In backend directory
cd backend
npm run dev     # or `node index.js`

# In frontend directory (in separate terminal)
cd frontend
npm start       # runs React app at http://localhost:3000


Ensure environment variables are set (see below).

Project Structure
/backend
  ├── controllers/
  ├── models/
  ├── routes/
  ├── services/          # e.g., payment, auth, tracking
  ├── sockets/           # WebSocket / Socket.io code for live tracking
  ├── index.js
/frontend
  ├── src/
        ├── components/
        ├── pages/
        ├── context/     # or redux/
        ├── hooks/
        ├── services/    # API call functions
        ├── assets/
        ├── App.js
        └── index.js
.env                     # environment variables (never commit!)

Usage

Register or login with Google account.

Browse restaurants and menus, add items to cart.

Place an order and pay via Razorpay.

Once order is confirmed and courier assigned, track the courier on map in real‑time.

View order history and profile.

Environment Variables

Create a .env file in both backend and frontend (if needed) with keys such as:

Backend (.env):

MONGO_URI=yourmongodburi
JWT_SECRET=yourjwtsecret
GOOGLE_CLIENT_ID=yourgoogleclientid
GOOGLE_CLIENT_SECRET=yourgoogleclientsecret
RZP_KEY_ID=yourrazpaykeyid
RZP_KEY_SECRET=yourrazpaysecret
GOOGLE_MAPS_API_KEY=yourmapsapikey
PORT=5000


Frontend (.env):

REACT_APP_BACKEND_URL=http://localhost:5000
REACT_APP_GOOGLE_MAPS_API_KEY=yourmapsapikey


⚠ Make sure to never commit your .env with secrets to version control.

Payment & Authentication

The Google OAuth flow allows users to sign in with their Google account.

Payment processing is done via Razorpay: orders are created in backend, payment captured, status updated.

You may need to handle webhooks or payment success/failure redirect flows.

Live Tracking

The backend uses WebSockets (e.g., via Socket.io) to push courier location updates to the front end.

The frontend maps service (Google Maps) displays the courier’s current position and route in real time.

Couriers can update their location via a mobile‑friendly view or manually in the admin panel.

Frontend listens on a socket event like locationUpdate and re‑renders the map marker.

Deployment

Deploy frontend to Vercel (or Netlify)

Deploy backend to Heroku, AWS EC2, or DigitalOcean; ensure environment variables are set and CORS is configured.

Set webhook/redirect URLs in Razorpay and Google OAuth to production domain.

Use HTTPS and secure cookies/jwt for production.

Contributing

Contributions are welcome!

Fork the repository

Create a new branch (git checkout -b feature‑foo)

Make your changes, add tests if applicable

Submit a pull request with a clear description of changes

License

This project is open‑source under the MIT License. See the LICENSE
 file for details.

Thanks for checking out the project!

Happy coding 🎉
If you run into issues or want to suggest enhancements, feel free to open an issue or discussion.
>>>>>>> 03154e3 (Commiting the completed project)
