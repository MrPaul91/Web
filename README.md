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

## Module 3 - "Project Manager" components:

### Components related to recruit members, choose project, elicitation project and generate resources:

Recruit members: This component is responsible for allowing Project Managers to add members to their company. It has a dropdown list with the users that belong to the category team members (Analyst, Developer and Tester) and who do not belong to any company. For each user, the username and the user's name. When the desired user is chosen, he is sent an invitation to join the company. Only the project manager has permissions to access this component. Its URL route is home/users/projectmanager/functions and it's located in /web/src/app/recruit-members.

Choose Project: In this component, a Project Manager belonging to a company without an active development can choose a project of two categories (Bidding or Instant). It has a table with all projects available and for each project it will show the Project ID, Project Name, Required K, Rewarded K, Required Analyst Level, Required Developer Level, Required Tester Level. Only Project Managers belonging to a company and without a project already assigned to their company have permission to access this component. If a PM clicks Select on an available project, the project will be assigned to his company. Its URL route is home/users/projectmanager/chooseproject and it's located in /web/src/app/chooseproject.

Cost & Time Estimation: This component allows a Project Manager to elicitate the cost and time for a given Bidding Project. It has a form with two fields, Cost and Time and two buttons, Exit and Validate. The Validate button is used to verify a PM's estimation, everytime its clicked, it will subtract one point out of the resource pool of said PM's company and it will send the information to a list containing estimations. If the estimation is wrong in at least one field, a message will alert the user telling him what did he get wrong. If the estimation is correct, a message will congratulate the user and tell him that he can advance to the next stage of the project. Its URL route is home/users/projectmanager/estimation and it's located in /web/src/app/estimation.

Generate Resources: In this component a Project Manager can add resources to his company's resource pool by way of solving sliding puzzles, though the functionality is pretty bare-bones at the moment. It has a frame containing the puzzle (right now a static image) and a little text, with two buttons to Exit or Validate the puzzle. Its URL route is home/users/projectmanager/generate and it's located in /web/src/app/generateresources.

### Additional Components:

Pmfunctions: This component displays all the actions that a Project Manager can do. It has four buttons (Recruit Member, Choose Project, Estimate Cost & Time and  Generate Resources. Clicking each button will redirect the user to the specified Use Case. Only the PM has permission to access this. Its URL route is home/users/projectmanager and it's located in /web/src/app/pmfunctions.

### Module 5 - "Communication" component:
The Email (communication) component allows users to communicate between them. Allows to read inbox, sent emails, write new emails and send it. Shows a notification that counts unread messages. Know more : /src/app/email


