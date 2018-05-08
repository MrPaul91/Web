# Web

This web application is exposed on the ip: http://35.196.111.251/

If you want to run it locally you must download and install the current LTS (long term support) version of node.js from here https://nodejs.org/es/ this version includes npm.

In the root folder of the project /web/ you must run the following commands:

npm install -g @angular/cli

npm install

ng serve

Now the app is running on your localhost:4200 and you can open it from your browser.

## Folder - Files structure:

/web/ every configuration file is located here, please don't modify them.

/web/e2e -> tests folder, it is not important for us.

/web/src -> where all files are located.

/web/src/ -> More configuration files, don't modify them please.

/web/src/styles.css -> General css file for all the app.

/web/src/styleSheets/ -> Here are located all imported css files.

/web/src/app/app.module.ts -> This file contains all the information about the libraries imported, components created and URL routes of the application.

/web/src/app/general-service.service.ts -> The file we are using as dummy database.

/web/src/app/ -> Here are located all the important files for us, the files we created and modified, all the other folder and files are related with the components we will describe next.

## Components structure:

component.css file -> These files will contain all the aesthetics of a component.

component.html file -> These files will contain all the content of a component.

component.spec.ts file -> These files contain the tests for the functions on component.ts files.

component.ts file -> These files contain all the logic of the component.

## General components:

App: This is the father component, the atributes, templates, and everything programmed here will be used in all the other components. It doesn't have a route inside the application and its files are located in /web/src/app/, in this component we defined the general structure of the webpage as header - body - footer, and we defined that all the bodies will contain the mail component.

Header: This is the component that has the content that will be shown in the header of the app, from here they can reach all mayor functionalities on the app, also it changes depending on the role of the user who logged in. It doesn't have an specific URL route and its located in /web/src/app/header.

Footer: This is the component that has the content that will be shown in the footer of the app, it doesn't have an specific URL route and its located in /web/src/app/footer.

Home: This component is where the user reaches after logging in, from here they can reach all mayor functionalities on the app, also it changes depending on the role of the user who logged in. Its route in the app is /home and its located in web/src/app/home.

Restricted: This is the component that has the content that will be shown if an URL in which the user has not permissions to enter is typed. It's URL is /restricted and it's located in /web/src/app/restricted.

Not Found: This is the component that has the content that will be shown if a non-existant URL is typed. It doesn't have an specific URL route and it's located in /web/src/app/not-found.

## Module 1 - "Game Set-up" components:

### General component for Game set-up:

Set up: This component contains all the buttons of actions that the game administrator can perform in terms of the game setup, these buttons are: create project, update project, create question, update question, create puzzle, update puzzle and update parameters. Its URL route is /home/set-up and it's located in /web/src/app/set-up

### Comoponents related to project creation and project update:

Create project: This component is responsible for showing the two types of projects that can be created in software boulevard, so that the game administrator can select which of them he wants to create. Its URL route is /home/set-up/create-project and it's located in /web/src/app/create-user.

New bidding project: This component is responsible for the creation of bidding projects. It has a form that validates the input data. The form contain the following fields: name, kunit, time, cost, krequired, analyst level, developer level, tester level, amount of analyst questions, amount of developer questions and amount of tester questions. Its URL route is /home/set-up/create-project/new-bidding-project and it's located in /web/src/app/new-bidding-project.

New instant project: This component is responsible for the creation of instant projects. It has a form that validates the input data. The form contain the following fields: name, kunit, amount of analyst questions, amount of developer questions and amount of tester questions. Its URL route is /home/set-up/create-project/new-instant-project and it´s located in /web/src/app/new-instant-project.

Update project: This component is responsible for showing the projects available to the game administrator, dividing them into instant project and bidding project, and there you can select which one you want to update.Its URL route is /home/set-up/update-project and it's located in /web/src/app/update-project.

Update instant project: This component is responsible for showing the project selected by the game administrator and allowing the update of values ​​to the instant project. Its URL route is /home/set-up/update-project/update-instant-project and it´s located in /web/src/app/update-instant-project.

Update bidding project: This component is responsible for showing the project selected by the game administrator and allowing the update of values ​​to the bidding project. Its URL route is /home/set-up/update-project/update-bidding-project and it´s located in /web/src/app/update-bidding-project.

### Comoponents related to question creation and question update:

Create question: This component is responsible for allowing the game administrator to create new questions. It has a form that validates the input data. The form contain the following fields: desription, question category, question level, and the fourth answers whit its validates. Its URL route is /home/set-up/create-question and it's located in /web/src/app/create-question.

Update question: This component is responsible for displaying the questions that are found in the database to the game administrator, so that he can select which one he wants to update. Its URL route is /home/set-up/update-question and it´s located in /web/src/app/update-question.

Edit question:This component is responsible for showing the question selected by the game administrator and allowing the update of values ​​to the question. Its URL route is /home/set-up/update-question/edit-question and it´s located in /web/src/app/edit-question.

### Components related to puzzle creation and puzzle update:

Create puzzle: This is the component responsible for the creation of the puzzles, here the game administrator must upload an image that is stored on your computer, which must be a diagram, it will appear on the screen, you must also write the amount of resources it provides to the project manager solve the puzzle. Its URL route is /home/set-up/create-puzzle and it's located in /web/src/app/create-puzzle.

Update puzzle:This is the component responsible for the update of puzzles, here the puzzles that are stored will be displayed, and the game administrator will select the one that he wants to update.Its URL route is /home/set-up/update-puzzle and it's located in /web/src/app/update-puzzle.

### Component related to parameter update.

Update parameters: This is the component responsible for updating the threshold, which will be general for all projects and all estimates that will be made. Its URL route is /home/set-up/update-parametersand it's located in /web/src/app/update-parameters.

## Module 2 - "Game Management" components:

### Components related to account creation, account updates, log-in and log out:

Create user: This component is responsible for allowing the creation of accounts for new users. It has a form that validates the input data. The form contains the following fields: name, username, password, confirmation for the password and role. All fields are required to create a user. Only the game administrator has permissions to access this component. Its URL route is /home/users/create and it's located in /web/src/app/create-user.

Update user: This component is responsible for allowing the update of user accounts. It has a form that validates the input data. The form contains the following fields: name, username, password, confirmation for the password and role. Only one field is required to update a user. Only the game administrator has permissions to access this component. Its URL route is /home/users/user-status/update and it's located in /web/src/app/update-user.

Login: This component is responsible for allowing users to access the platform. It has a form that validates the input data. The form contains the following fields: username and password. These fields are required. In case the user is already logged in on the platform, it redirects them to the home page according to the user role. Its URL route is the root '/' and its located in /web/src/app/login.

Logout: This is **not** a component, it's a functionality included in the header component.

### Components related to company creation and company updates.

Create company: This component is responsible for allowing the creation of new companies. It has a form that validates the input data. The form contains the following fields: name, URL of the company's logo and project manager. Only the name field is required to create a company. Only the game administrator has permissions to access this component. Its URL route is /home/companies/create and it's located in /web/src/app/create-company.

Update company: This component is responsible for allowing the update of companies. It has a form that validates the input data. The form contains the following fields: name, URL of an image and project manager. Only one field is required to update a company.The game administrator and the project managers have permissions to access this component but the project manager can only update the image. Its URL route is /home/companies/company-status/update and it's located in /web/src/app/update-company.

### Components related to generating and viewing reports, viewing players, viewing companies and viewing their status.

Reports: In this component all the reports are shown to the game administrator, they are on tables and each table is shown in a tab. Its URL route is /home/reports and it's located in /web/src/app/reports.

Users: This component is responsible for showing the game administrator the characteristics of each one of the players. It shows a table with the users, also, from this component there are buttons which redirect to the Create user and the Update user components. Its URL route is /home/users/ and its located in /web/src/app/users.

Companies: This component is responsible for showing the game administrator the characteristics of each one of the companies. It shows a table with the companies, also, from this component there are buttons which redirect to the Create company and the Update company components. Its URL route is /home/companies/ and its located in /web/src/app/companies.

User status: In this component almost all information about a user is shown, its accessible by every kind of user but the game administrator can see the status of every user and each user can see only its status. From here the game administrator can reach the Update user component. Its URL route is /home/users/user-status/ and it's located in /web/src/app/user-status.

Company-status: In this component almost all information about a company is shown, its accessible by every kind of user but the game administrator can see the status of every company and each user can see only its company. From here the game administrator and the project managers can reach the Update company component.  Its URL route is /home/companies/company-status/ and it's located in /web/src/app/company-status.
### Module 5 - "Communication" component:
The Email (communication) component allows users to communicate between them. Allows to read inbox, sent emails, write new emails and send it. Shows a notification that counts unread messages. Know more : /src/app/email
