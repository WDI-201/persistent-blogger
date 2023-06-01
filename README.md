# Persistent Blogger

In this assignment, you will create a new blog application using Express.js, Mongoose, and the Model-View-Controller (MVC) architecture. The application will allow users to create, read, update, and delete authors and blog posts.

## Instructions

1. **Generate a new Express application:**

   - Create a new repository in Github called persistent-blogger
   - Open your terminal or command prompt.
   - Clone the repository.
   - Go into the repository directory:
     ```
     cd persistent-blogger
     ```
   - Run the following command to generate a new Express application:
     ```
     npx express-generator --no-view
     ```

2. **Install required dependencies:**

   - Run the following command to install the required dependencies:
     ```
     npm install
     ```

3. **Install dependencies**
   - Run the following command to install Nodemon as a development dependency:
     ```
     npm install --save-dev nodemon
     ```
     Run the following command to install dotenv and uuid as dependencies:
     ```
     npm install dotenv uuid
     ```
4. **Set up .env file**

   - Open Visual Studio Code by running the following command:
     ```
     code .
     ```
   - Add .env file in the project's root directory.
   - Add:
     ```
     ATLAS_URI = <Your MongoDB Atlas URI>
     ```

5. **Update package.json:**
   - Open the `package.json` file in the project's root directory.
   - Locate the `"scripts"` section and update it as follows:
     ```
     "scripts": {
       "start": "nodemon ./bin/www",
     },
     ```
   - Save the file.
   - Run the following command in the terminal to start the server:
     ```
     npm start
     ```
6. **Update app.js to include dotenv:**
   - Open `app.js`and add the following line below const logger:
     ```
     require("dotenv").config();
     ```
7. **Set up Mongoose:**

   - Create a new file called `db.js` in the root of your project.
   - Open `db.js` and create a function, use the ATLAS_URI with mongoose.connect to connect to MongoDB Atlas
   - Export out the function

8. **Run the function that connects our Application to MongoDB:**

   - Remember to go into `app.js` bring in the function from `db.js` below `require("dotenv").config();`
   - Invoke the function

9. **Create router files and bring them in app.js:**

   - Create a new file called `authors.js` in the routes directory.
   - Create a new file called `blogs.js` in the routes directory.
   - Add router boilerplate to each one of the file.
   - Remember to export router out
   - In `app.js` create a route for `/authors` and route for `/blogs`.
   - Remember location matters!

10. **Create a model and a controller directories**

    - In the projects directory add a model folder and a controller folder

11. **Create a Author.js file inside the model directory**

- Create a new file called `Author.js` in the model's directory.
- Open `models/Author.js` and define the schema, the Author model and export the Author model out.
- The Author schema should have the following fields:
  - `_id` (String): A unique identifier generated using UUID (Universally Unique Identifier) version 4.
  - `name` (String): The name of the author. A required field
  - `email` (String): The email of the author. A required field
  - `createdAt` (Date): The date and time when the author was created. It has a default value of the current time.

12. **Create a controller:**

- Create a new file called `authorController.js` in the controller's directory.
- Open `controllers/authorController.js` and add the following functions (You should create one function at a time with a route to test):
  - `getAllAuthors`
  - `createAuthor`
  - `getAuthorById`
  - `updateAuthorById`
  - `deleteAuthorById`
- Remember to export these functions out so they can be used!

13. **Create Routes:**

- Open `routes/authors.js` and add the following routes, connect the functions from controller. Remember to test each route with the corresponding functions:
  - `/all-authors`
  - `/new-author`
  - `/get-author-by-id`
  - `/update-author`
  - `/delete-author`
- Remember to add needed params or queries!

14. **Create a Blog.js file inside the model directory**

- Open `models/blog.js` and define the schema, the blog post model and export the Blog model out.
- The structure of the schema should have the following (You should create one function at a time with a route to test):
  - `_id` (String): A unique identifier generated using UUID (Universally Unique Identifier) version 4.
  - `title` (String): The title of the blog post. It is a required field.
  - `content` (String): The content of the blog post. It is a required field.
  - `author` (String): The author of the blog post refering to a user. It is a required field.
  - `lastModified` (Date): The date and time when the blog post was last modified. It has a default value of the current time.
  - `createdAt` (Date): The date and time when the blog post was created. It has a default value of the current time.

15. **Create a controller:**

- Create a new file called `blogController.js` in the controller's directory.
- Open `controllers/blogController.js` and add the following functions:
  - `getAllBlogs`
  - `createBlog`
  - `getBlogById`
  - `updateBlogById`
  - `deleteBlogById`
- Remember to export these functions out so they can be used!

16. **Create Routes:**

- Open `routes/blogs.js` and add the following routes, connect the functions from controller. Remember to test each route with the corresponding functions:
  - `/all-blogs`
  - `/new-blog`
  - `/get-blog-by-id`
  - `/update-blog`
  - `/delete-blog`
- Remember to add needed params or queries!

## Testing the Application

To test your application, follow these steps:

1. Make sure you are in the project's root directory in your terminal or command prompt.

2. Run the following command to start the application in development mode:
   ```
   npm start
   ```