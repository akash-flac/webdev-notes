- https://medium.com/@ksshravan667/14-days-of-express-day-2-middlewares-global-catches-bedac3007414
- Prechecks happen in the server before the request reaches the actual logic part of the code in the server where the response is given.
- Two prechecks that are done :
	- Authentication
	- Input Validation
- global catches : Express comes with a default error handler that takes care of any errors that might be encountered in the application. The default error handler is added as a middleware function at the end of the middleware function stack. This is also called global catching.

