## Week 14 - Day 6

### Python Asessment 2

Submission folder `submissions/<your_folder>/week_14/day_6/assessment_python`

- **WRITE CLEAN CODE WITH PROPER VARIABLE NAMES**
- **BREAK INTO SMALLER FUNCTIONS IF REQUIRED**
- **WRITE COMMENTS EXPLAING THE LOGIC IF REQUIRED**

#### FSD.EVL.B.1

- FIle `print_numbers.py`
- Given a starting and ending number print the numbers (excluding the starting and including the ending) with the following rules
  - Print `@` instead of the number if the number is divisible by `2`
  - Print `#` instead of the number if the number is divisible by `3`
  - Print `%` instead of the number if the number is divisible by `5`
  - Print `^` instead of the number if the number is divisible by `2` and `3`
  - Print `!` instead of the number if the number is divisible by `2` and `5`
  - Print `*` instead of the number if the number is divisible by `3` and `5`
  - Print `$` instead of the number if the number is divisble by `2` `3` and `5`


#### FSD.EVL.B.2

- File `count_letters.py`
- Given a string print the no. of lower case and upper case occurance of each character (NOTE: Ignore Spaces)
- Sample Output format
  ```python
  # Masai School
  M - 1
  a - 2
  s - 1
  i - 1
  S - 1
  c - 1
  h - 1
  o - 2
  l - 1
  ```

#### FSD.EVL.B.3

- File `sorting_counter.py` (NOTE: You can't use any inbuilt function for doing the sorting)
- Given a list of numbers sort them in descending order using bubble sort and print the number of swaps done to achieve the result 

#### FSD.EVL.B.4

- File `brick_wall.py`

- Given the width and height print a brick wall [Full brick `|___|` (Pipe seperated by 3 underscores) Half brick `__|` or `|__` (2 underscores) ]

- Sample brick wall of width four bricks and height 5 bricks

  ```python
  |___|___|___|___|
  __|___|___|___|__
  |___|___|___|___|
  __|___|___|___|__
  |___|___|___|___|
  ```

#### FSD.EVL.B.5

- File `drinks_calculator.py`

- You are hosting a party for superheros and each of them have their preference of drinks they would like to have. Count the number of each drink required for the party so that each superhero should get atleast one drink of their preference and the total cost of the party is minimum

- The price of the drinks follows the order Coffee > Milk > Tea

- Sample Output format
  ```python
  # Thor - Milk or Tea
  # Ironman - Milk or Coffee
  # Hulk - Coffee
  Tea - 1
  Milk - 1
  Coffee - 1
  ```

#### FSD.EVL.B.6

https://raw.githubusercontent.com/masai-school/assignments-data/master/data/lists/colornames.csv

- File `color_splitter.py`

- The mentioned csv file contains a colors with their name and color codes, split the file into multiple files using the below mentioned criteria (The headers and format should remain the same as the original file)
  - `colors_red.csv` - With all the colors that have the word `Red` in their name
  - `color_green.csv` - With all the colors that have the word `Green` in their name
  - `color_blue.csv` - With all the colors that have the word `Blue` in their name
  - `shade_gray.csv` - With all the colors the have the same RGB values in the color hex code some of the examples are mentioned below
  - `shade_funky` - With all the colors that have six different characters in the color hex code some of the examles are mentioned below 

Sample Gray Colors 
```css
#666666
#d3d3d3
#808080
#333333
```

Sample Funky Colors
```css
#231f20
#76b583
#50647f
```