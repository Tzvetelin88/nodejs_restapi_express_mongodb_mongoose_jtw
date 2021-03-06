# nodejs_restapi_with_mongodb_mongoose_jtw
- Backend achieved by Nodejs
- Frontend achieved by Reactjs. (p.s. React Application will be used to access backend. https://github.com/Tzvetelin88/reactjs_hooks_saga_redux)

Nodejs RestAPI application. Using Express, Mongoose, JWT auth. 

## Inside:

 - Crеate free account with MongoDB Atlas (https://account.mongodb.com/)
 - HTTPS access via SSL/TLS (get OpenSSL for Windows: https://wiki.openssl.org/index.php/Binaries)
 - dotenv to set environment variables (dev/prod/test/stage) (In real env use DevOps stack - PipeLines, Releases etc.)
 - User Mongoose as syntax sugar.
 - Create Routes, Models and Controllers.
 - Validate requests with epxress validator.
 - Add authentication and validate with JWT.
 - Use Multer to send image + uuid string generator
 - helmet to secure Express app by setting HTTP headers.
 - Logging HTTP requests via morgan to access.log file (or DB) (more on logging: https://blog.risingstack.com/node-js-logging-tutorial/)

## Using middleware: 

 -  dotenv			  - https://www.npmjs.com/package/dotenv
 -  HTTPS			  - https://nodejs.org/api/https.html
 -  express           - https://expressjs.com/en/api.html
 -  mongoose          - https://mongoosejs.com/docs/documents.html
 -  MongoDB Cloud     - https://account.mongodb.com/
 -  express-validator - https://express-validator.github.io/docs/   
 -  jsonwebtoken      - https://github.com/auth0/node-jsonwebtoken#readme
 -  bcryptjs		  - https://github.com/kelektiv/node.bcrypt.js#readme
 -  helmet		  	  - https://helmetjs.github.io/
 -  multer		  	  - https://github.com/expressjs/multer#readme
 -  morgan		      - http://expressjs.com/en/resources/middleware/morgan.html

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


## How to use:
 - Go to https://account.mongodb.com/ and crеate free account with MongoDB Atlas
 - Clone the repo
 - run "npm install" to install all packages from package.json
 - Set your environment variables in .env file - PORT and MONGODB_URL
 - Generate your own Self Signed Certificate with: "openssl req -nodes -new -x509 -keyout server.key -out server.cert" or use the one attached for testing (SSL is Self 	Signed Certificate generated by OpenSSL https://wiki.openssl.org/index.php/Binaries).
 	 Do NOT use Self Signed Certificate for Production! Request certificate for you FQDN by legit authorities like Hosting Provider (AWS, Azire, GCP, Heroku(Digital Ocean), etc.)!
 - Visit Application URL: https://localhost:<PORT>/  
 - Write API request with Postman (example: [Express.postman_collection.json](https://github.com/Tzvetelin88/nodejs_restapi_express_mongodb_mongoose_jtw/blob/main/Express.postman_collection.json)) or [React Application](https://github.com/Tzvetelin88/reactjs_hooks_saga_redux).
   Import "Express.postman_collection.json" to your Postman for testing.


## P.S.
#### In next release we will re-write all .then() promises with async/await for more readable and structured code!
#### Still you can use the new ECMA syntax to import/export, but be aware that many are still Experimental, depends of the version of Nodejs:
 - v.15 https://nodejs.org/api/esm.html
 - v.14 https://nodejs.org/docs/latest-v14.x/api/esm.html

#### Will rewrite to TypeScript
