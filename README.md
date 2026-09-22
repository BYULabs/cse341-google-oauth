# StoryBooks

A simple Node.js and Express web app that allows users to sign in with their Google account and access a basic dashboard. The project uses Passport.js for OAuth authentication, MongoDB for user storage, Express Handlebars for the views, and Materialize CSS with Font Awesome for the UI.

## Features

- Google OAuth authentication with Passport.js
- Session-based login flow
- MongoDB user persistence
- Dashboard view for authenticated users
- Responsive styling using Materialize CSS
- Icons using Font Awesome

## Tech Stack

- Node.js
- Express
- Express Handlebars
- MongoDB + Mongoose
- Passport.js
- Passport Google OAuth 20 strategy
- Materialize CSS
- Font Awesome

## Project Structure

```bash
.
├── app.js
├── package.json
├── config/
│   ├── config.env
│   ├── db.js
│   └── passport.js
├── models/
│   └── User.js
├── public/
│   └── css/
│       └── style.css
├── routes/
│   ├── auth.js
│   └── index.js
├── views/
│   ├── dashboard.hbs
│   ├── login.hbs
│   └── layouts/
│       ├── login.hbs
│       └── main.hbs
└── README.md
```

## Prerequisites

Before running the app, make sure you have:

- Node.js installed
- MongoDB running or a MongoDB Atlas connection string
- A Google Cloud OAuth client configured

## Installation

1. Clone the repository:

```bash
git clone <your-repository-url>
cd cse341-google-oauth
```

2. Install dependencies:

```bash
npm install
```

3. Configure environment variables:

Create or update `config/config.env` with your app settings:

```env
PORT=3000
MONGO_URI=your_mongodb_connection_string
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
```

## Google OAuth Setup

1. Go to the Google Cloud Console.
2. Create a new project or select an existing one.
3. Enable the Google OAuth API.
4. Create OAuth 2.0 Client ID credentials.
5. Add your app's redirect URI:

```text
http://localhost:3000/auth/google/callback
```

6. Copy the Client ID and Client Secret into `config/config.env`.

This app uses the Passport Google OAuth strategy documented here:

- https://www.passportjs.org/packages/passport-google-oauth20/

## Frontend Libraries

This app uses the following frontend resources:

- Materialize CSS: https://materializecss.com/getting-started.html
- Font Awesome CDN: https://cdnjs.com/libraries/font-awesome

## Run the App

Development mode:

```bash
npm run dev
```

Production mode:

```bash
npm start
```

Then open:

```text
http://localhost:3000
```

## Notes

- The app stores user information from Google authentication in MongoDB.
- The login page is rendered with `login.hbs` and uses Materialize-styled buttons.
- The dashboard is a simple authenticated landing page.

## License

This project is licensed under the MIT License.
