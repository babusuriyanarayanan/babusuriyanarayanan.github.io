
Nowadays, many of us have used Facebook connect or Google OAuth for logging into any other websites conveniently with out going through the annoying registration process. Mostly, all sites allow token based authentication such as JWT. 


From the front end perspective, the authentication service validates user login credentials and provides you the token with expires time set on it. Using the token, you can get the data on every subsequent request until the token is expired. what happens when a token expires ? will you ask the user to log in again? Obviously not correct right, so what's the remedy for this? The token based authentication system provides a special kind of token called refresh tokens. After the previous token expires, a new token can be obtained by using this refresh token and allows the user authenticated into the application forever. 


Tokens are not advisable to store in the browser directly due to security reasons. It must be stored safely somewhere. The best option to keep the token in any of persistent NoSQL key value cache data store like Redis. So authentication can be done from this data store.Amazon ElasticCache provides a platform to run Redis cluster in their cloud. 


When the user logs in, the authentication service returns the access token, refresh token, token type, expires in information along with a unique id. In Redis store, all sensitive data like tokens will be stored for the corresponding unique id and the server will return only the unique id to the browser. This unique id alone is meaningless to the browser.


The browser will send the unique id in the HTTP Header to make Authorized Requests. In the server, based on the unique id, the user token will be retrieved from the Redis and will communicate with the restful API. 
