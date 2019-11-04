## Week 14 - Day 1

**Frontend Assignement**

Create a react application with routing having the following pages and use cases (use bootstrap and don't write any css) using the API from the site. The routes for the pages are mentioned at the starting of the each problem

https://reqres.in/

Code Location

```
~/submissions/<your_folder>/week_14/day_1/assignment
```
1. `login` - Show a login page (no navbar) on successful login you should be able to perform the tasks from 2 to 7 (having navbar) and showing the token in the navbar
2. `/home` - Default Page after login should have pagination based on the api (Should show the list of users in the form of a table).  
3. `/create` - Form Page with the fields 
4. `/show/<id>` - Can be navigated by clicking the id of the row, shows the page with all the details of the user
5. `/edit/<id>` - Show the form with the filled in details using the `api` of that particular user, you should be able to make changes and save them after successful completion the page comes back to `/show/<id>` page
6. `/delete/<id>` - Show a page with the name and a delete button, if that is clicked the show the response from the server and place a button on that page so that you can go to home page
7. `logout` - Should clear the token and show the registration page

Pages from 2 to 6 should not be accessible if the user is not logged in 