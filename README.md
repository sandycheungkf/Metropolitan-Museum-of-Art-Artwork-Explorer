### Vercel App (Deployed) Link : https://web-as06-kfc.vercel.app/

## Overview
The website involves creating a User API using Node/Express, securing it with JWT authentication, and integrating it with a Next.js application to manage user registration, authentication, and data persistence.

---

## User API (Node/Express)

### Setup Instructions

1. **Database Setup on MongoDB Atlas**

2. **Create a `.env` file in the root directory of the User API project.**

3. **Run `npm install` to install all required dependencies**

4. **Starting the Server**

5. **Endpoints and Authentication**
   - Implement JWT authentication using Passport with `passport-jwt` strategy.
   - Secure routes for user favorites and history using `passport.authenticate()` middleware.

---

## Next.js Application

### Setup Instructions

1. **Create a `.env.local` file in the root directory of your Next.js application**

2. **Libraries Setup**
   - Implement authentication and data handling libraries (`authenticate.js` and `userData.js`).
   - Use `jsonwebtoken` for handling JWT in client-side authentication.

3. **Pages and Components**
   - Implement `login.js` and `register.js` for user authentication.
   - Integrate API calls for user registration, login, and CRUD operations for favorites and history.

