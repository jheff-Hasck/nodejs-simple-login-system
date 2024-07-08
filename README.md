# Node.js Simple Login System

This is a simple login system built with Node.js. It uses `express` for the server, `ejs` as the view engine, and various authentication-related dependencies to handle user login and sessions.
> **NOTE:** Database isn't setup. Login Credentials are stored in local storage

## Dependencies

- `express`
- `ejs`
- `bcrypt`
- `passport`
- `passport-local`
- `express-session`
- `express-flash`
- `dotenv`

## Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/nodejs-simple-login-system.git
    ```

2. **Navigate to the project directory:**
    ```bash
    cd nodejs-simple-login-system
    ```

3. **Install the dependencies:**
    ```bash
    npm install
    ```

4. **Create a `.env` file in the root of the project and add your session secret:**
    ```plaintext
    SESSION_SECRET=any_secret_key
    ```

5. **Start the server:**
    ```bash
    npm start
    ```

6. **Open your browser and navigate to:**
    ```
    http://localhost:3000
    ```

## How It Works

### Express
`express` is a minimal and flexible Node.js web application framework. It provides a robust set of features to develop web and mobile applications.

- **Usage in your code:**
    ```javascript
    const express = require('express');
    const app = express();
    app.use(express.urlencoded({ extended: false }));
    ```

### EJS
`ejs` (Embedded JavaScript templates) is a simple templating language that lets you generate HTML markup with plain JavaScript.

- **Usage in your code:**
    ```javascript
    app.set('view engine', 'ejs');
    ```

### Bcrypt
`bcrypt` is a library to help you hash passwords. It uses the bcrypt hashing function to securely hash user passwords before storing them in the database.

- **Usage in your code:**
    ```javascript
    const bcrypt = require('bcrypt');
    const hashedPassword = await bcrypt.hash(password, 10);
    ```

### Passport and Passport-Local
`passport` is authentication middleware for Node.js, while `passport-local` is a Passport strategy for authenticating with a username and password.

- **Usage in your code:**
    ```javascript
    const passport = require('passport');
    const LocalStrategy = require('passport-local').Strategy;

    passport.use(new LocalStrategy(
        function(username, password, done) {
            // Authentication logic here
        }
    ));
    ```

### Express-Session
`express-session` is a middleware to handle sessions in your application. It stores session data on the server and gives the client a session ID to identify their session.

- **Usage in your code:**
    ```javascript
    const session = require('express-session');
    app.use(session({
        secret: process.env.SESSION_SECRET,
        resave: false,
        saveUninitialized: false
    }));
    ```

### Express-Flash
`express-flash` is a flash message middleware for Express. It provides a way to display messages to the user after a redirect.

- **Usage in your code:**
    ```javascript
    const flash = require('express-flash');
    app.use(flash());
    ```

### Dotenv
`dotenv` is a module that loads environment variables from a `.env` file into `process.env`.

- **Usage in your code:**
    ```javascript
    require('dotenv').config();
    ```

## Conclusion

This simple login system provides the basic structure for handling user authentication in a Node.js application. By leveraging the above-mentioned dependencies, you can easily extend and customize it to fit your specific needs.

## Contribution

Feel free to fork this project, make improvements, and send a pull request. Any contributions are welcome!

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
