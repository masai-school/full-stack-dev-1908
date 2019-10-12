# Week 5 - Day 4

#### Coding Session 2

**SUBMISSION:**

- Folder `~/cohort_2/submissions/<your_folder>/week_5/day_4/coding_2`
- Create a files as per the questions with your first name and last name
- Once you complete the coding session push that file to the online repo

**NOTE:** Follow the instructions carefully and follow coding discipline

**NOTE2:** Indent your code correctly and stick to one kind of naming style

**NOTE3:** You must not write any JavaScript code within the `html`file! ***All*** your JS must be in the `js` file! Use the script tag to link your JS file from your HTML file. 

**NOTE4:** Use jQuery, AJAX  to accomplish the 

**NOTE5:** Use Bootstrap to build the UI elements

You must set up your own API server, follow the instructions here [https://github.com/masai-school/api-mocker/wiki](https://github.com/masai-school/api-mocker/wiki).

### FSD.W5.4.1_1

An simple API that allows you to showcase the different codenames of the versions of the choosen operating systems.  

You can read the documentation here https://github.com/masai-school/api-mocker/wiki/Operating-Systems-API

**Do the following**

1. Create a file called `os.html` and a file called `os.js`. Link `os.js` from `os.html`.

2. Create a simple dropdown with different names of operating systems
3. When the users clicks submit get the data using the API and showcase the version numbers and names in the form of a table

------

A simple API that allows you to register a user, login a user and view the profile of a user is given to you.

You can read the documentation here [https://github.com/masai-school/api-mocker/wiki/Authentication-API](https://github.com/masai-school/api-mocker/wiki/Authentication-API).

### FSD.W5.4.1_2

**Do the following:**

1. Create a file called `register.html` and a file called `register.js`. Link `register.js` from `register.html`.

2. Create a simple ***registration page*** that will allow a user to register with the necessary details mentioned in the API docs. 

### FSD.W5.4.1_3

**Do the following:** (HINT: User **beforeSend** in jQuery ajax to send the headers information)

1. Create a file called `login.html` and a file called `login.js`. Link `login.js` from `login.html`.
2. Create a simple **login page** that allows a user to enter their username and password.
3. When the user submits their login details you must send the data to the api.
4. If the login data is correct, you must display all the profile information. You must also delete the login page elements.
5. If the login data is incorrect you must tell the user `The username or password was incorrect, please try again!`