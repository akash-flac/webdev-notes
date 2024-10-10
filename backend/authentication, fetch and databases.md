# fetch API
- used to fetch data from an API
```js
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Document</title>

</head>

<body>

    <script>

        // function getData(){

        //     fetch("https://fakerapi.it/api/v1/persons")

        //     .then(function(response){

        //         response.json()

        //         .then(function(finalData){

        //             console.log(finalData);

        //         })

        //     })

        // }

  

        //the following code does the same thing as above

        async function getData() {

            const response = await fetch("https://fakerapi.it/api/v1/persons");

            const finalData = await response.json()

            console.log(finalData);

        }

    </script>

  

    <button onclick="getData()">Get Data</button>

</body>

</html>
```

# authentication
## hashing 
- passwords are hashed before they are stored in a database
- string -> (hash function) -> hashed string
- one way(cant de-hash)
- given the output, cant find the input
## encryption
- df
- two way(a password is used using which the same string can be encrypted or decrypted)

## JSON Web Tokens
- Takes JSON as input and gives out a string(token)
- the string is just a different representation of the json data, nothing is changed as such, and no hashing or encryption is done
- It is used to verify(or authenticate) a user.
- Here, we pass JSON through a function called `jwt.encode`, and the output is then again passed through another function `jwt.verify` along with the original password, which gives the original object, verifying the user.
- JWT is stored in the local application storage of the user.
- ![](attachments/Pasted%20image%2020240911191220.png)
- ![](attachments/Pasted%20image%2020240911191519.png)

## databases
![](attachments/Pasted%20image%2020240911192001.png)

- There are various types of databses:
	- Graph : specific use cases
	- Vector : ML stuff
	- SQL : used in most full-stack apps
	- NoSQL : MongoDB

### MongoDB
- lets you create a database
- in each DB, lets you create tables(collections)
- in each table, lets you dump JSON data
- is schemaless
- scales well and is a decent choice for most use cases

### How does the backend connect to the database?
**Using libraries**
- Express lets you create an HTTP server
- jsonwebtokens library lets you create jwt
- mongoose lets you connect to your database
