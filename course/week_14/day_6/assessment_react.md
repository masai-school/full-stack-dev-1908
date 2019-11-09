## Week 14 - Day 6

**React Assessment**

Create a react application with routing having the following pages and use cases (use bootstrap or material-ui and don't write any css) using the API from the site. The routes for the pages functionalities are mentioned 

```
~/submissions/<your_folder>/week_14/day_6/assessment_react
```
### FSD.EVL.RCT.C.1

`login` - Show a login page with the dropdown of Names fetched from the API https://reqres.in/api/users and a `LOGIN` button (To login a particular user you have to select the userfrom the dropdown and click the login button)

### FSD.EVL.RCT.C.2

`/home` - Home Page after login show have a navbar with the Name of the loggedin user and a `LOGOUT` button (This navbar should be the same for all pages and click on the Name should bring you to `/home` page). This page should contain two buttons `COMMENTS` & `WRITE`

### FSD.EVL.RCT.C.3

`/comments` - Shows a list of all the comments along with the Name & Image of the user in reverse order (Newest first and Oldest last). The list of comments are stored using the `redux` store. The comments corresponding the current loggedin user should have `EDIT` and `DELETE` buttons

### FSD.EVL.RCT.C.4

`/write` - Form Page with a text box and a button `ADD` which will add the written text to the comments list corresponding to the current logged in user

### FSD.EVL.RCT.C.5

`/edit/<id>` - Show the form with the preview comment text and a `SAVE` and `CANCEL` button, when clicked on the `SAVE` button it should update the comment with the new text and take back the `/comments` page where as clicking on the `CANCEL` button will not save it

### FSD.EVL.RCT.C.6

`/delete/<id>` - Show a page with the comment and a `DELETE` and `CANCEL` button, when clicked on the `DELETE` button it should remove the corresponding comment and take back to `/home` page on clicking the `CANCEL` button it should take back to `/comments` page

### FSD.EVL.RCT.C.7

`LOGOUT` - On clicking the button in the navbar it should clear the current user and take back to `login` page