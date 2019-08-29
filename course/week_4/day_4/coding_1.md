# Week 4 - Day 4

#### Coding Session 1

**SUBMISSION:**

- Pull the `cohort_2` repo
- Go to `templates/week_4/day_4/` 
- Copy  the folder `session_1`  to `submissions/<your_folder>/week_4/day_4`
- Complete all the problems given below in the file `index.html`
- Push your completed folder back to the online repo

**NOTE:** Follow the instructions carefully and follow coding discipline

**NOTE2:** Indent your code correctly and stick to one kind of naming style

**NOTE3:** You have only been given a basic HTML file. YOU MUST FILL`id` and other basic attributes for all tags! You must also define your own JavaScript Functions!  


### FSD.W4.4.1_1

A button with the text `Click here to print the JSON object` is given to you.

An variable `items` is given to you. It contains an array of Objects.

A div with `id="container1` is given to you.

**Using JavaScript do the following:**

1. When the button is clicked, you must convert a given array value from `object` to `JSON`. 
2. You must then create `p` tags and display the `name` and `price` of each object within the `p` tag you created. You must not display the value of the `id` key!
3. Append the `p` tags to the div with `id="container1`.

### FSD.W4.4.1_2

2 input elements are given to you. 

A `p` tag with the text `Output:` is given to you

A button with the text `Calculate` is given to You. 

**Using JavaScript do the following:**

1. Create a function with the name `exponent`. It must have 3 arguments `x` `y` `callBack`. `x` and `y` are of type `number`. `callBack` of type `function`.
2. It must calculate the result of `x ** y` and pass that value to `callBack` after calculating that value.
3. Write a function expression (also known as a function as a variable) called `display`. It must accept a single argument `input`. It must append the string `The exponent is:` to the start of the input. It must return the appended string.  
**Example:**
```
display(9) -> "The exponent is: 9"
```
4. When the button is clicked, you must call the function `exponent` with the appropriate inputs from the input elements for `x` and `y` from the input boxes. You must also pass the `display` function as the `callback` argument. Store the output in a variable.
5. Print the output to a `p` tag with the text `Output:`.  
6. Step 4 and 5 should be done by an anonymous function passed to the button listener.

### FSD.W4.4.1_3

**Using Javascript do the following**

1. When the button  `Generate Tables` is clicked you should reset the  global variable `multiply` to an empty array `[]`
2. Fill the array with numbers from `1` to the limit provided
3. Using `arr.forEach()` fill the table so that it looks like the one provided below (Limit: 3)

| *1  | *2  | *3  | *4  | *5  |
|---|---|---|---|---|
| 1 | 2  | 3  | 4  | 5  |
| 2  | 4  | 6  | 8  | 10  |
| 3  | 6  | 9  | 12  | 15  |

### FSD.W4.4.1_4

1. When the button `Genenrate CAPS and small` is click convert the given input of words (comma separated)  into an array (HINT: Use `split` function)
2. Using `arr.map()` create two more arrays one containing the `UPPERCASE` of the words and the other `lowercase` of the words (HINT: Use inbuilt functions)
3. Fill the table so that it looks like the one provided below from the three arrays generated above

Sample Input: `Masai,School`

| Normal | UPPER | Lower |
| ---- | ---- | ---- |
| Masai | MASAI | masai |
| School | SCHOOL | school |