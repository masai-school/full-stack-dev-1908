### Coding Task

**Build an application with the below mentioned features**

Guidelines

- Use Bootstrap or Material UI to build the application (The layout should be responsive)
- Write clean code with proper formatting with good variable and function naming
- Submission Deadline 12th Oct, 2019 19:00
- Folder `cohort_2/submissions/<your_folder>/week_10/day_6/`



**Application**

- Route `/home` should contain two buttons `Create` and `Show`
- On clicking the `Create` button it should a form with the below fields and should be able to save them (Using Redux and Localstorage)
  - Player Name (Text)
  - Country (Dropdown List of any 10 Countries)
  - T20 Score (Number Field)
  - ODI Score (Number Field)
  - Test Score (Number Field)
- On clicking the `Show` button you should be able to see all the players and their scores with a pagination of 10 results per page and should also have the ability to filter by Country and sort by T20 or ODI or Test Score in ascending or descending order
- On clicking on Name of any players you should show go to a new page with the Name, Country, T20, ODI, Test and Total (Sum of T20, ODI & Test) . This page should also show a random fact about the total score of the player using the numbers api  [http://numbersapi.com](http://numbersapi.com/) (If the total score is 12000 the url you have to call is `http://numbersapi.com/12000?json`)



**OPTIONAL FUNCTIONALITY**

-  On the player profile page show the  rank (Criteria for calculating the rank is mentioned below)
  - The ranks are calculated based on the total runs scored (So the top scorer in each country will get first rank)
  - If two players in the same country those who got scored same runs they will get same rank
  - The player placed next to the same score players will get the rank skipping the
    intermediate ranks. Refer to the example below
    Players in Avengers
    Iron Man - 1000, Spider Man - 1000, Captain Marvel - 1500, Thor - 1300, Hulk - 1000, Hawkeye - 800
    RANKS OF Players
    Captain Marvel - 1, Thor - 2, Iron Man - 3, Spider Man - 3, Hulk - 3, Hawkeye - 6

