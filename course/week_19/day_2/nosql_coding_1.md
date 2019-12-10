## Week 19 Day 2

### Mongo Part-8


**Tasks List Manager**

Create an application to manage the tasks lists of a user

- A user can have multiple task list
- A task list can have multiple tasks
- The application should have the ability to show the task list for a particular user along with the number of tasks in each list

| id   | List Name | Tasks |
| ---- | --------- | ----- |
| 1    | Music     | 4     |
| 2    | Movies    | 5     |
| 3    | Books     | 2     |

**User 3 approaches for building the backend**

- One to Many with embedded documents
- One to Many with list of child references in the parent document
- One to Many with the parent reference in the parent document