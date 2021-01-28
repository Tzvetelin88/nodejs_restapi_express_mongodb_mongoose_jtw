# nodejs_restapi_with_mongodb_mongoose_jtw
- Backend achieved by Nodejs
- Frontend achieved by Reactjs. (p.s. React Application will be used to access backend. https://github.com/Tzvetelin88/reactjs_hooks_saga_redux)

Nodejs RestAPI application. Using Express, Mongoose, JWT auth. 

## Inside:

 - Crеate free account with MongoDB Atlas (https://account.mongodb.com/)
 - User Mongoose as syntax sugar.
 - Create Routes, Models and Controllers.
 - Validate requests with epxress validator.
 - Add authentication and validate with JWT.

## Using: 

 -  express           - https://expressjs.com/en/api.html
 -  mongoose          - https://mongoosejs.com/docs/documents.html
 -  MongoDB Cloud     - https://account.mongodb.com/
 -  express-validator - https://express-validator.github.io/docs/   
 -  jsonwebtoken      - https://github.com/auth0/node-jsonwebtoken#readme
 -  bcryptjs		  - https://github.com/kelektiv/node.bcrypt.js#readme
 
 - Testing 
	- chain 		  - http://chaijs.com/
	- sinon 		  - https://sinonjs.org

## Four Routes: 
``` 
   /feed
   /auth 
```

## API Endpoints:
```
/auth
	router GET:
		'/status'

	router PUT:
		'/signup'

	router POST:
		'/login'

	router PATCH:
		'/status'

/feed
	router GET: 
		'/posts'
		'/post/:postId'
		
	router POST: 
		'/post'
		
	router PUT:
		'/post/:postId'

	router DELETE:
		'/post/:postId'
```


# P.S.
## In next release we will re-write all .then() promises with async/await for more readable and structured code!
## Still you can use the new ECMA syntax to import/export, but be aware that many are still Experimental, depends of the version of Nodejs:
 - v.15 https://nodejs.org/api/esm.html
 - v.14 https://nodejs.org/docs/latest-v14.x/api/esm.html

Some examples in our project:
```
// New syntac to import.
// Add "type: module" in package.json

import path, { dirname } from 'path'
import { fileURLToPath } from 'url'
import express from 'express'
import bodyParser from 'body-parser'
import mongoose from 'mongoose'
import multer from 'multer'

import { default as feedRoutes } from './routes/feed.js'
import { default as authRoutes } from './routes/auth.js'

// Because of the new syntax of Ecma, __filename or __dirname not supported as global variables.
// Read more: https://nodejs.org/docs/latest-v15.x/api/esm.html
// !!!! Some features are still experimental  !!!!

// We need to construct it in more long way....
const __filename = fileURLToPath(import.meta.url);
const __dirname = dirname(__filename);

// Old way to import
// const path = require('path');
// const express = require('express');
// const bodyParser = require('body-parser');
// const mongoose = require('mongoose');
// const multer = require('multer');

// const feedRoutes = require('./routes/feed');
// const authRoutes = require('./routes/auth');
```
