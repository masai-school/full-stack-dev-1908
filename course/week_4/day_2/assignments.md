# Week 4 - Day 1

**NOTE:** Follow the instructions carefully and follow coding discipline

**SUBMISSION:**

- Folder `~/cohort_2/submissions/<your_folder>/week_4/day_2/assignments`
- Create a file `firstname_lastname.html` with your first name and last name
- Once you complete the assignment push that file to the online repo


## FSD.W4.1.A

- Complete the file `firstname_lastname.html` so that it looks similar to the link https://raw.githubusercontent.com/masai-school/full-stack-dev-1908/master/course/week_4/day_2/templates/score_card_players.jpg
- Functionality (HINE: Use Objects to store the names and scores)
  - By clicking on any number it shows up in the score box joined to any previous numbers already present (Eg: To enter a score of `423` you have to press `4` `2` `3`)
  - The name of the player can be entered in the input field above the `ENTER` button
  - Once the button `ENTER` is pressed the score gets compared with the `MIN` and `MAX` boxes, if the current score is less than the `MIN` score it gets updated with the current score, if the current score is greater than the `MAX` score it gets updated with the current score. The names of the `MIN` and the `MAX` players are also changed accordingly
  - The score should also be added to the board on the right side along with the name of the player  (Eg: Ajay - 30)
  - The `SCORE` box will be reset with empty value
  - The `NAME` box will be reset with empty value
  - By clicking the `REMOVE LAST` button the last game score should be removed from the score card, the `MIN` and `MAX` updated accordingly
