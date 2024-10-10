![](attachments/Pasted%20image%2020240910233539.png)
We create a server to provide abstraction to our code, wherein we can expose the functionality of our code to the world without having to expose the code. 
Using server, we won't need the code to use it's functionality. We can have a code at some server where we can request access to it's functionality from some other place. 

This is the most basic express example:
```js
const express = require("express");

const app = express();

app.get('/', function(req, res){

    res.send("hi, there");

})

app.listen(3000);
```

Here, on `localhost:3000`, we get a response `hi, there` by the server. 

> In the URL, whatever comes after the `/` is counted in the route, but when encountered `?`, whatever comes after `?` isn't counted in the route, and instead counted as parameters if written with the right syntax. Eg. `localhost:3000/asd?n=3&a=2`. Here, /asd is part of the route, but n=3 and a=2 are the parameters given to the server as part of the request to get the requisite response. These are called query parameters.

## Request Methods
### GET
Get data from the server
### POST
Add data into the server
### PUT
PUT is used to modify a resource. PUT updates the entire resource with data that is passed in the body payload. If there is no resource that matches the request, it will create a new resource.
### DELETE
Remove data entries. 

## Status Codes
- 200 : OK
- 404 : Not Found
- 500 : Something went wrong
- 411 : Input is incorrect 
- 403 : Not allowed

