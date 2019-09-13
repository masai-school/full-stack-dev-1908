![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK6-DAY5-green)

#### Coding Session 1
### FSD W6.5.1.A.1:

Write a fetch function which uses `Github API` for search users:

[Seach user Github API Documentation](https://developer.github.com/v3/search/#search-users)

After searching, the output should be displayed in `Search Results` table.
(Can be made with flex/grid/tables/bootstrap)

The table should contain information of each profile like image, name and other details.

From the returned data, use `repos_url`, `events_url` and other data points

In the table `Search Results` for each user you should also display:
- total no of repositories, list them in a drop down
- last commit details
- Show history of commit with date and no of commits on each day
- total followers
- total following
- total stars

### FSD W6.5.1.A.2:

- Make another table with the table name `Local Storage`
- You should have a `save` button for each user on the `Search Result` table
- The `save` button will store information of the user locally into the `Local Storage table`
- Ask the user if they would like to `overwrite` the data if there is a duplicate


### FSD W6.5.1.A.3:
- Add another button called `update` for each user in the Local Storage table
- Add another button called `delete` for each user in the Local Storage table
- `update` will only update the selected user
- `delete` will only delete the selected user