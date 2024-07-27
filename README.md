# 🚀 auth-mongo-setup: Your MongoDB Authentication Wingman! 🦸‍♂️

## Welcome to the world of MongoDB auth made easy! 🎉

Tired of setting up authentication like it's a Rubik's cube? 🧩
Say hello to auth-mongo-setup, your new best friend in the world of user management!

## What's this magic potion? 🧪

auth-mongo-setup is like having a tiny authentication wizard living in your code. It's got all the MongoDB and Express.js authentication spells you need, pre-packaged and ready to cast!

## Features that'll make you dance the authentication tango 💃🕺

- 🎭 User Registration: Because "Guest12345" is so last season.
- 🔐 Login: Keep the baddies out and your users cozy.
- 🧠 Forgot Password: For when your users' memory fails them (happens to the best of us).
- 🛡️ JWT Authentication: Like a forcefield, but for your API.
- 📧 Email Verification: Make sure your users are real humans, not clever cats with keyboards.

## Installation (Easier than installing a new habit) 🔧

```bash
npm install auth-mongo-setup
```

## Configuration (Customize your magic wand) 🪄

### Create a .env file in your project root. Fill it with your arcane secrets:

```bash
CopyMONGO_URI=mongodb://localhost:27017/hogwarts-db
JWT_SECRET=mischief-managed
SMTP_HOST=owl.postoffice.com
SMTP_USER=hedwig@owlmail.com
SMTP_PASS=treat$ForOwls
```

## Usage (No stack overflow required!) 🤓

#### First, sprinkle some magic dust in your main file:

```bash
javascriptCopyrequire('dotenv').config();
const express = require('express');
const authMongoSetup = require('auth-mongo-setup');

const app = express();

// Use the authentication routes
app.use('/api/auth', authMongoSetup.routes);

// Start your engines!
const PORT = process.env.PORT || 3000;
app.listen(PORT, () => console.log(`Server vrooming on port ${PORT}`));
```

### Now, let's break down the spells... err, functions:

## 🧙‍♂️ Registration Spell

```bash
javascriptCopy// In your client-side code
fetch('http://localhost:3000/api/auth/register', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ email: 'merlin@camelot.com', password: 'excalibur123' })
})
.then(res => res.json())
.then(data => console.log('New wizard registered!', data));
```

## 🔓 Login Incantation

```bash
javascriptCopyfetch('http://localhost:3000/api/auth/login', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ email: 'merlin@camelot.com', password: 'excalibur123' })
})
.then(res => res.json())
.then(data => {
  console.log('Wizard authenticated!', data);
  localStorage.setItem('authToken', data.token);
});
```

## 🧠 Forgot Password Potion

```bash
javascriptCopyfetch('http://localhost:3000/api/auth/forgot-password', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ email: 'merlin@camelot.com' })
})
.then(res => res.json())
.then(data => console.log('Password reset potion sent!', data));
```

## 🛡️ Protected Route Shield

```bash
javascriptCopyconst { auth } = require('auth-mongo-setup');

app.get('/api/secret-spell', auth, (req, res) => {
  res.json({ msg: 'The secret spell is Avada Kedavra... oops, wrong franchise!' });
});
```

### Remember, a good wizard never reveals their secrets! 🤫

## Contributing (Join our coven) 🧙‍♀️🧙‍♂️

### Found a bug? Want to add a new spell? Just want to share your favorite potion recipe? We're all ears! 👂

### Open an issue or submit a PR. Our code of conduct: Be excellent to each other! 🎸

### Remember, with auth-mongo-setup, you're never auth-alone. Now go forth and authenticate with confidence! 🚀✨
