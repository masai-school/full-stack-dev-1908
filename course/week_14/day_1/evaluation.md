## Week 14 - Day 1

### Python Evaluation 1

Submission folder `submissions/<your_folder>/week_14/day_1/evaluation`

- **USAGE OF ANY INBUILT FUCTIONS IS NOT ALLOWED**
- **WRITE CLEAN CODE WITH PROPER VARIABLE NAMES**
- **BREAK INTO SMALLER FUNCTIONS IF REQUIRED**

#### FSD.EVL.A.1

- FIle `email_domain.py`
- Given a valid email address find the domain name of the email
- Sample Output format
  ```python
  # For input hello@masaischool.com
  masaischool.com
  ```


#### FSD.EVL.A.2

- File `count_vowels.py`
- Given a string print the no. of lower case and upper case vowels seperately (`a,e,i,o,u`) & (`A,E,I,O,U`)
- Sample Output format
  ```python
  # MASAI School
  lower - 2
  UPPER - 3
  ```

#### FSD.EVL.A.3

- File `average_diff.py`
- Given a list of numbers find the difference between the sum of even and  odd indexes
- Sample Output format
  ```python
  # numbers = [1,2,3,4,5,6]
  # Even Index Sum - 1 + 3 + 5 = 9
  # Odd Index Sum - 2 + 4 + 6 = 12
  # Diff = 9-12
  -3
  ```
  

#### FSD.EVL.A.4

- File `sets_intersection.py`
- Given three sets find the common elements in those three sets
- Sample Output format
  ```python
  # a = {"a", "b", "c", "d", "e"}
  # b = {"a", "e", "f", "h", "k"}
  # c = {"a", "b", "c", "z", "m"}
  {"a"}
  ```
  
#### FSD.EVL.A.5

- File `student_ranks.py`
- Given a dict of students and the marks in 3 subjects print the names in the descending order of their totals (NOTE: Assume all the totals are unique) 
- Sample Output format
  ```python
  # scores = {"Thor": [1,2,3], "Ironman": [3,4,5], "Hulk": [2,3,4]}
  Ironman
  Hulk
  Thor
  ```

#### FSD.EVL.A.6

- File `grocery_list.py`

- It should take the item and quantity as input and store the data in the file `groceries.csv` (Headers: item, quantity)

- If the item is already present, it should increment the quantity of the item with the current amount

- Sample Output format
  ```python
  # Inputs (4 times)
  # Rice,3
  # Sugar,1
  # Salt,2
  # Rice,4
  
  # groceries.csv
  item,quantity
  Rice,7
  Sugar,1
  Salt,2
  ```