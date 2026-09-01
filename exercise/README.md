<h1>
  <span class="headline">Intro to Mongoose Lab</span>
  <span class="subhead">Exercise</span>
</h1>


## 1. Model Definition (in `models/Recipe.js`)

1. Create a Schema and model for the Recipe. Use the following for your Schema creation:


Create a model folder and create a Recipe.js file inside. create the model with the following fields:
| Field        | Type      |  Validation |
|--------------|-----------|-------------|
| name         | String    | required, minLength: 2, maxLength: 100 |
| instructions | [String]  | |
| prepTime     | Number    | min: 5, max 500, required |
| difficulty   | String    | enum: ['Easy', 'Medium', 'Hard'] |


2. Now export the model using `module.exports = Recipe`

---

## 2. Functionality (in `practiceDatabaseMethods` file)

Build the following **functions** that interact with the database in your practiceDatabaseMethods

### 3. `createRecipe(newRecipe)`

- Create an `async` function that takes a parameter
- It should create a new recipe in the database
- If it is saved successfully then, `console.log()` the created recipe (**HINT** Use try catch).
- If unsuccessful, `console.log("Failed to create recipe.")`.
- Test your function with the following object:
   ```javascript
   const newRecipe = {
    name: "Um Ali",
    instructions: "bake at 180C",
    prepTime: 120,
    difficulty: "Medium"
   }
   ```


### 4. `getAllRecipes()`

- Write a function that should console.log() all the recipes we have in the database
- Use the .find() method
- BONUS: `console.log()` the recipes in the following format: `{name} is an {difficulty} recipe and takes {prepTime} minutes to prepare`


### 5. `getRecipeById(id)`

- Write function that takes an id as a parameter
- If found, `console.log` the recipe.
- If not found, `console.log("No recipe with this ID exists.")` (NOTE: If a id doesn't exist in the Database the method will return `null`).


### 6. `updateRecipe(recipeId, newRecipeData)`

- Write a function that Takes in a recipe ID and an object of updated data.
- Updates the recipe in the DB.
- Use `{ new: true }` to return the updated document.
- Log the updated recipe if successful.

### 7. `deleteRecipe(recipeId)`

- Deletes the recipe with the given ID.
- If successful, `console.log("Recipe successfully deleted.")`.


---

## Bonuses

### BONUS: Refactor for Reusability

1. Move all the function declerations into a separate file called `recipeUtils.js`.
2. Export the functions using module.exports in an object from `recipeUtils.js`.
3. Import and use them in `practiceDatabaseMethods`.


### BONUS 2: try catch
1. For any code that awaits using `async await` put the code in a `try catch` block

### BONUS 3: create db.js file
1. Create a file called `db.js`
2. Move the `connectToDB` function decleration to the `db.js` file
3. export the `connectToDB` function using `module.exports`
4. Import it in the `practiceDatabaseMethods` file.
5. NOTE: This should not change the functionality but just make it so your file structure is cleaner


### BONUS 4: .env
1. Instead of putting our connection string to the database in plain text in the `mongoose.connect()` method lets store it in the .env file
2. install the package `dotenv`
3. Create a `.env` file and add your connection string there
4. In your `practiceDatabaseMethods` file add the following code: `require('dotenv').config()`
5. Add `.env` to your `.gitignore` file so it doesn't get pushed to github




### BONUS 5: timestamps: true
1. Add `{timestamps: true}` to your Schema so it logs the created time and updated time


