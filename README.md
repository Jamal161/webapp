# Web Application murmur(=tweet)

## Running with Docker

```sh
docker-compose up
```

## Running without Docker

You must have mongoDB, node.js and npm installed on your computer.
Then, first, after the `cd backend` command, then the `npm i` or `npm install` command, if you are going to develop, you can restore the backend with the `npm watch` command. If you have seen

```
started listening on http://localhost:3000/ in your terminal we are connected to mongoDB!!!
```

if there is this command, it means its backend is working fine.

Then for the frontend, you can install the packages by saying `yarn` in the `frontend` folder, then you can raise the frontend with `yarn serve`. If there is no problem, you can completely restore the project at `http://localhost:8080/`.

## Running backend

```sh
cd backend
npm i
npm start
npm watch #run with nodemon for development
```

## Running frontend

```sh
cd frontend
yarn
yarn serve
```

Run `npm install` on the root folder and it will set up a pre-commit hook to lint the staged files. You will also have two lint commands, `npm run lint` and `npm run lint-staged` that you can run on the root folder.

These commands run the individual `lint` and `lint-staged` scripts in both the `frontend` and the `backend` folders, and they will respect individual configurations of these folders.

]

### Request end-points

```javascript
GET  http://localhost:3000/users HTTP/1.1

###

POST  

{"name": "John Doe", "handle": "@johnDoe", "email": "john_doe@twitter.com"}

###

DELETE  http://localhost:3000/users/611390360384a2befbbc7466 HTTP/1.1

###

GET http://localhost:3000/users/6113b3d9e2c6234211727249

###

POST    http://localhost:3000/users/617e978514928da134c12366/tweets HTTP/1.1
content-type: application/json

{"body": "This is a test tweet."}

###

PATCH   http://localhost:3000/users/6113a464e332bd183bf840d2 HTTP/1.1
content-type: application/json

{"name": "Cihat"}

###

PATCH   http://localhost:3000/users/611546eebd96a6a5e85c821d/following HTTP/1.1
content-type: application/json

{"userToFollowId": "6113dc26306ad96bcd30b251"}

###

PATCH   http://localhost:3000/users/612cea71e2e1167e4e1547ce/like HTTP/1.1
content-type: application/json

{"likeTweetId": "612cea85e2e1167e4e1547d1"}

###

PATCH   http://localhost:3000/users/6113dc26306ad96bcd30b251/retweet HTTP/1.1
content-type: application/json

{"retweetId": "6113de87306ad96bcd30b50b"}

###
```

------------------------------------
