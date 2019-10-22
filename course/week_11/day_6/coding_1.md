### Coding Task

**Build an application with the below mentioned features**

Guidelines

- Use Bootstrap or Material UI to build the application (The layout should be responsive)
- Write clean code with proper formatting with good variable and function naming
- Submission Deadline 22th Oct, 2019 17:30
- Folder `cohort_2/submissions/<your_folder>/week_11/day_6/`



**Application**

- Route `/home` should show the list of countries and the code from the API http://country.io/names.json and should also contain a button called `Data`
- On clicking the country name it should a form with the below fields and should be able to save them (Using Redux and Localstorage)
  - Capital (Text)
  - Continent (Dropdown)
  - GDP (Number Field)
  - Population (Number Field)
- On clicking the `Data` button you should be able to see all the countries for which the data has been entered 5 results per page and should also have the ability to filter by Continent and sort by GDP or Population in ascending or descending order. The table headers and data should look like the one provided below (The ranks for GDP and Population are calculated based one the descending order of values)
- If you click on the country name from `/home` page and the data for that particular country is already filled previously the form should show the previously filled data

| Code | Country | Continent | GDP | Population | Rank (GDP) | Rank (Population) |
|------|---------|-----------|-----|------------|------------|-------------------|
|      |         |           |     |            |            |                   |
|      |         |           |     |            |            |                   |
|      |         |           |     |            |            |                   |
