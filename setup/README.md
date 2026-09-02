<h1>
  <span class="headline">Intro to Mongoose Lab</span>
  <span class="subhead">Setup</span>
</h1>


## 1. Project Setup

1. Initialize the project as a node project by running the following command:

   ```bash
   npm init -y
   ```
2. Install mongoose as a dependancy:

   ```bash
   npm install mongoose
   ```

3. create a `.gitignore` and add node_modules inside

## 2. Database Connection
* Create a file called `practiceDatabaseMethods.js`

.
* Use `mongoose.connect()` and log:

  * `"Connected to database!"` on success.
  * `"Connection failed."` on error.

```js


async function connectToDB(){ //connection to the database
    try{
        await mongoose.connect() // <----- PUT YOUR DATABASE CONNECTION STRING HERE
        console.log("Connected to Database")
    }
    catch(error){
        console.log("Error Occured",error)
    }
}


connectToDB() // connect to database


```
