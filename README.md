# JS401 - Project 3 - API Server
## Author: Cory Henderson
This project took our previously built API server and merged it with an authentication server.  API are now protected as follows:

- app.get(...) should should not require authentication
- app.post(...) should require the create capability
- app.put(...) should require the update capability
- app.patch(...) should require the update capability
- app.delete(...) should require the delete capability

## Links and Resources
- [Github Repo](https://github.com/401-advanced-javascript-1/project3-api-server/tree/submission)
- [Heroku](https://mysterious-savannah-83587.herokuapp.com/)

## Documentation
- Adding player models with the CLI: echo '{"name":"<string>","position":"<string>","throws":"<string>","bats":"<string>","team":"<string>"}' | http post :3000/api/v1/players/ -a username:password
- Teams can be updated with the above command replacing "post" with "put"
- Getting player/team models: http :3000/api/vi/players -a username:password
- .env requirements (these will be inputs in the heroku config vars): 
    - PORT=3000 (locally, not required for Heroku)
    - MONGODB_URI=mongodb://localhost:27017/project3 (locally, auto-updated in Heroku)
    - SECRET=asecretofyourchoice (for authentication)
- Supported routes:
    - /signup: enables user signup
    - /signin: authenticates user at signin
    - /api/v1/:model: user may get and create teams/players
    - /api/v1/:model/:id: user may get, update, or delete teams/players
- All data will come back in JSON format

# Modules
- index.js: this is the entry point which connects to the MongoDB
- app.js: this is the server file
- api: contains the router file for the api
    - v1.js
- api-models: conatins models and schemas for players and teams
    - players-model.js, teams-model.js, players-schema.js, teams-schema.js
- auth: contains the authorization router and middleware for authentication
    - middleware.js, router.js
- auth-models: contains models and schemas for users and roles which assigns user capabilities
    - roles-model.js, users-model.js

# Setup
- .env requirements
    - MONGODB_URI=mongodb://localhost:27017/teams (for MongoDB NoSQL)
    - PORT=3000 (for nodemon)
    - SECRET= secret for authentication

## Tests
- Testing for expected route endpoints is performed using jest.

## UML
