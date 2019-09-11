# Week 6 - Day 3
![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK6-DAY3-green)

![](https://img.shields.io/badge/CODING-SESSION1-red)

[Codepen Example](https://codepen.io/albseb511/pen/RwbyNoo?)

**SUBMISSION:**
- Create the files into the location `~/repos/cohort_2/submissions/<your_folder>/week_6/day_3/session_1/` 
- Push the file  back to the online repo

**NOTE:**
1. Seperate out HTML, CSS and JS files.
2. Write clear functions with Unix philosophy in mind.
3. Try to use ES6 syntax and methods wherever possible.
4. Write clean code
5. Use map, filter, reduce wherever you can

### FSD W6.3.1.A.1:

Create a Class `Header`:
It will contain the following variable(s):
- String `name` - contains name of the header
- String `color` - color of header 
- Integer `font-size` - font of the header 

It will have the following methods/functions inside it:
1. `displayDetails`: return all the information in a formatted way in console
2. `render`: return a div with an h1 tag along with the name inside it. You should also style the font color with the color variable in the class

### FSD W6.3.1.A.2:
To the same class above:

Add the following methods:
1. `updateName`: change the value of the name
2. `updateColor`: change the value of the color
3. `updateFontSize`: change the value of the font size

HTML/CSS:
Create an input form for the following inputs:
1. `name`
2. `color`
3. `font-size`

Following Buttons to be made:
- `Name`: will create a new instance of a class if not created. Do not take any other arguments in the constructor.
         If the class is already created then you will call updateName. color will be black by default, and font-size will be 20px.
- `color`: will change the value of the color
- `font-size`: will update the value of font-size
- `Render`: When clicked, you should display the name with a div and h1 tag.


### FSD W6.3.1.A.3:
`Extend` the Class Header to make a new Class `listHeader`
name should be an array of strings

Add/Edit the following methods: (HINT: only write the methods if its required either due to overriding or if the methods are not inherited)
1. `displayDetails`: return all the information in a formatted way in console
2. `render`: return a div with an h1 tag along with the name inside it. Since its an array of strings, each element has to have its own div and h1 tag.
3. `updateName`: change the value of the name
4. `updateColor`: change the value of the color
5. `updateFontSize`: change the value of the font size
6. `deleteName`: delete a name by searching through your array.

Make seperate input forms and buttons for this problem
HTML/CSS:
Create an input form for the following inputs:
1. `name`
2. `color`
3. `font-size`
4. `update-name` (Keep a drop-down or select option to select which name to update)
4. `delete-name`

Following Buttons to be made:
- `Name`: will create a new instance of a class if not created. Do not take any other arguments in the constructor.
         If the class is already created then you will call add to the array of names. color will be black by default, and font-size will be 20px.
- `color`: will change the value of the color
- `font-size`: will update the value of font-size
- `Delete Name`: will delete a particular name from the array inside the class
- `Render`: When clicked, you should display all the name in seperate div and h1 tag in the form of a list