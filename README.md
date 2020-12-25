# LAB - Class 06

## Project: bearer-auth

### Author: Jeremy Penning

### Links and Resources

- [CI/CD](https://github.com/jeremyp-401-advanced-javascript/bearer-auth/actions) (GitHub Actions)
- [Back-end Application](https://jeremyp-bearer-auth.herokuapp.com/)
- API Endpoints - Relative to Back-end Application URL above.

---

### API Endpoints - Users

#### **POST /signup** - (Create a User)

**Required Parameters:**

>Request Body (JSON or form-data):
>- username - _String_
>- password - _String_ 

#### **POST /signin** - (Authenticate a User)

**Required Parameters:**

>Headers:
>- Authorization: Basic `<hashed username:password>`

---

### Setup

#### `.env` requirements

- `PORT` - Port Number
- `MONGODB_URI` - Mongo DB Connection String
- `SECRET` - JWT encryption secret (string)

#### How to initialize/run the application

To run application:

`npm start`

### Testing (All tests provided with lab)

To run tests:

`npm test`

#### Basic Auth Middleware Tests

The user authentication middleware:
- fails a login for a user (admin) with the incorrect basic credentials
- logs in an admin user with the right credentials

#### Bearer Auth Middleware Tests
The user authentication middleware:
- fails a login for a user (admin) with an incorrect token
- logs in a user with a proper token

#### Authentication Router Tests

The /signup route:
- successfully creates a new user: 'admin'
- successfully creates a new user: 'editor'
- successfully creates a new user: 'user'

The /signin route:
- correctly signs in 'admin' using basic authentication
- correctly signs in 'editor' using basic authentication
- correctly signs in 'user' using basic authentication
- correctly signs in 'admin' using bearer authentication
- correctly signs in 'editor' using bearer authentication
- correctly signs in 'user' using bearer authentication

Failure on /signin route:
- basic fails with known user and wrong password
- basic fails with unknown user
- bearer fails with an invalid token
