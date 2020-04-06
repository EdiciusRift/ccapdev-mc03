# Mini Challenge 3 for CCAPDEV1920T2

## General Instructions
- **READ THE INSTRUCTIONS FIRST BEFORE PROCEEDING!**
- You are provided with a skeleton code for this Mini-Challenge. You are **NOT ALLOWED** to modify any part of the code unless specified. Editable parts of code are marked with `TODO` comments.
- For any clarifications, ask your instructor.
- This Mini Challenge is _no longer graded_ but will serve as additional practice for working with databases, AJAX and express (with handlebars). Submission is **highly encouraged**.

## Local Set Up
- Make sure MongoDB is installed and running.
- Run `npm install` after cloning the forked repository.
- To run the application, execute `node index.js`

## Submission Details
- Fork this repository and submit the URL of the forked repository to AnimoSpace.

## Content
- [controllers](controllers) - This folder contains files which defines callback functions for client requests.
- [models](models) - This folder contains files for database modeling and access.
- [public](public) - This folder contains static assets such as css, js, and image files.
- [routes](routes) - This folder contains files which describes the response of the server for each HTTP method request to a specific path in the server.
- [views](views) - This folder contains all hbs files to be rendered when requested from the server.
- [index.js](index.js) - The main entry point of the web application.

## Challenge Description
You are to create a web application which simulates an online phonebook.

When a client requests for the root path, i.e. `/`, the server should display [`views/home.hbs`](views/home.hbs). Your web browser should display the screen below:
![alt text](home.png "Index Page")

The web application accepts two inputs - a name and a number. When the user submits the form, the web application first checks if both fields are filled. Sample user input:
![alt text](filled-form.png "Filled Form")

The web application then saves the values in the database, then display the values in `index.hbs`. Use [`views/partials/card.hbs`](views/partials/card.hbs) to render the `<div>` for each contact. Upon submitting the form, the contact should be displayed immediately **without refreshing the page**.

**HINT:** the client should communicate with the server **asynchronously**.

**HINT:** The server can render the handlebars template and send the rendered HTML partial. See the [express documentation on `res.render`](https://expressjs.com/en/api.html#res.render) to know more.

The picture below shows how the web application should display the values that we have entered earlier:
![alt text](displayed-contact.png "Displayed Contact")

Each contact may be removed using the `X` button on the upper right of the `<div>`. Upon clicking the `X` button, the web application deletes the contact from the database then removes the corresponding `<div>` of the contact from [`views/home.hbs`](views/home.hbs). This operation should be done **without refreshing the page**.

Note that the number should be **UNIQUE** for each contact - no two contacts may have the same number. Thus, you are required to check if the current value entered by the user in the `number` text field has not yet been used by any other contact in the database. You need to check this **EVERY TIME** the user enters a number in the `number` text field.

If the current value in the `number` text field **IS IN THE DATABASE**:
- Change the background color of the `number` text field to `red`.
- Display the error message `Number already registered` in the `<p id="error">` element in [`views/home.hbs`](views/home.hbs).
- Disable the `submit` button.

Else if the current value in the `number` text field **IS NOT YET IN THE DATABASE**:
- Change the background color of the `number` text field back to `#E3E3E3`
- Remove the error message in the `<p id="error">` element in [`views/home.hbs`](views/home.hbs).
- Enable the `submit` button.

The picture below shows the changes in the form if the current value in the `number` text field is already in the database:
![alt text](error.png "Error")

Upon refreshing the web application, all contacts in the database should be displayed.

You are already provided with the skeleton code organized in MVC architecture. Your task is to study the web application and complete the code of the files below. You are **NOT ALLOWED** to modify other files except the files below. Editable parts of code are marked with `TODO` comments, where you can insert your code.
- [`controllers/controller.js`](controllers/controller.js)
- [`models/UserModel.js`](models/UserModel.js)
- [`public/js/home.js`](public/js/home.js)
- [`views/home.hbs`](views/home.hbs)

Goodluck and stay safe! :sunglasses:

#### References
Maximize the materials uploaded for class and the resources readily available on the internet.

* [ccapdev-ajax](https://github.com/arvention/ccapdev-ajax) code sample
* [ccapdev-mongoose](https://github.com/arvention/ccapdev-mongoose) code sample
