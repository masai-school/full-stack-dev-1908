# Week 5 - Day 4

**NOTE:** Follow the instructions carefully and follow coding discipline

**SUBMISSION:**

- Folder `~/cohort_2/submissions/<your_folder>/week_5/day_4/session_1` 

**Use jQuery to build the whole functionality and Bootstrap for the design use of any custom classes and inline styles is not allowed**

### FSD.W5.3.1_1
- Create the file `registration.html` so that it looks similar to the link (also responsive the black box should be show below in mobile screen size) https://raw.githubusercontent.com/masai-school/full-stack-dev-1908/master/course/week_3/day_3/templates/registration.jpg
- Functionality
  - The user should be able to fill the three fields in the form
  - Once the register button is clicked it should perform the below validations
    - Name show be more than 3 characters and less than 10 characters
    - The email should be valid one you can use the function from your previous assignments
    - The mobile must only consist of 10 digits
  - If any of the validations fail you should show the error messages below that particular field
  - If all the validations pass, the filled values should appear on the right side black box and the form should be reset to blank values
- Workflow
  
  - Intially only the Name field should be visible as the users starts typing you should do a live validation and show the error message once the name is valid, the error message should be gone and  the email field should be shown
  
  - Once the email field is being filled, live validation should be shown and if its valid the mobile field should appear
  
  - Once the mobile field is filled and valid the Submit button should appear
  
  - On clicking the submit button this form should disappear and the right block should appear
  

HINT: Use show(), hide(), after(), events to achieve the end result