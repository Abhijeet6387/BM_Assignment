# BM-Assignment <br/>
Aim of this repository is to contain the solution to the task to create a project in django rest framework and celery with following APIs exposed:
* User signup, login , logout APIs
* Token exchange API : An authenticated user can submit a plaid public token that he gets post link integration. a) This public token is exchanged for access token on the backend.b) This initiates an async job on the backend for fetching account and item metadata for the access token.
* Expose a webhook for handling plaid transaction updates and fetch the transactions on receival of a webhook.
* Expose an api endpoint to fetch all transactions and account data for each user.
* To handle plaid error appropriately.

## ***Models:-***
* ***User:*** To store user login information.
* ***TokenItem:*** To store Access_token and Item_id information.
* ***Log:*** To store every activity log.
* ***Transactions:*** To store transactions information from Plaid API.
* ***Items:*** To store information of each Items.
* ***Account:*** To store bank account information.

## ***REST APIs:-***
* ***auth/registration/:*** To register a user.
* ***auth/login:*** To login a user.
* ***auth/logout:*** To logout already logged-in user.
* ***api/linktoken:*** To get link_token for logged-in user.
* ***api/tokenexchange:*** Exchange public_token to get access_token.
* ***api/fetchtrasaction:*** Fetch transaction of loggedIn user.
* ***api/webhook:*** Exposed webhook api for handling plaid transactions.
* ***api/:***  Link account and go in to plaid auth flow.

## ***How to use:-***
***step 1)*** Create a config.py file in plaid_auth directory and create a Setting object having plaid credentials as its properties.<br/>
***step 2)*** Install all the required dependecies from requirements.txt.<br/>
***step 3)*** Run the program and goto signup/login api to create/login your account.<br/>
***step 4)*** Go to api/ url to start the plaid auth flow for getting access token for one item.<br/>
***step 5)*** Go to fetchtransaction/url to fetch all the transactions between a start time and time.<br/>
