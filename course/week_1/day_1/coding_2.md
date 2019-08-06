# Week 1 - Day 1

#### Coding Session 2

**Introduction to git (Part 1)**

***NOTE**: Make sure that `git` is installed on your system!  
You can check with the command `git --version`, it should show the version of git that you currently have.  
If it is not installed you can do so using the command given below*  
Ubuntu

```
sudo apt-get install git
```

Mac

```
brew install git
```

### FSD.W1.1.2_1

Setup your name and email using the `git config` command.

### FSD.W1.1.2_2

- Go to your home directory `cd ~` and create a folder called `repos`
- Create a folder called `test` inside `repos` folder
- Navigate to `test` folder
- Initialise `test` folder with an empty repository  

### FSD.W1.1.2_3

- Create a file called `start`  inside `test` folder with the current `date` (HINT COMMAND:  `date > start`)
- Add the file `start` to `git` (HINT: use `git add` command)
- Check the status of the `start` file using `git status` command
- Commit the changes to `git` with the message "Start Time" (HINT: use `git commit` command)

### FSD.W1.1.2_4

- Go to http://github.com and create a new repository called `test` (**NOTE**: Don't tick the option Initialize this repository with a README)
- Add the newly created repository as remote to git repo in `test` folder (HINT: use `git remote` command)
- Sync the local commit to the remote repo (HINT: use `git push` command)
- Go to the repo page on http://github.com and see if you can see the start file in the repository

### FSD.W1.1.2_5

Create a new file in the repo page with the name `profile.md` put your name as the contents of the file and commit the new file with the message "Online Commit"

```
 echo "# SPARTANS - <FIRSTNAME LASTNAME>" > profile.md
```

### FSD.W1.1.2_6

- Download and unzip the file https://github.com/masai-school/assignments-data/raw/master/downloads/course.zip in the `test` repo folder (TIP : use`wget` and `unzip`)
- After unzipping you should in the `all` folder there is a file called `overall.txt` sync that file to the remote repo with the message "First File" (TIP: use the flow `add` `commit` `push`)

### FSD.W1.1.2_7

- Sync the folder `week_1` to the remote repo with the message "Week1 Course" (HINT: use the `git status` command to make sure only `week_1` folder is getting synced)

- Sync the folder `week2/day_5` to the remote repo with the message "W2 D5"

### FSD.W1.1.2_8

 Create a folder name `masai` in your home directory. Change directory to `masai` and initialise with an empty `git` repository.

  ### FSD.W1.1.2_9

  Create a file called `profile.md` inside `masai` folder with the content using the below command.

  ```
  echo "# SPARTANS - <FIRSTNAME LASTNAME>" > profile.md
  ```

  ### FSD.W1.1.2_10

  Create a repository on github with the name `masai-school-test` 

  ### FSD.W1.1.2_11

  Add the created repository `masai-school-test` on github as the new remote to the previously initialised repository in `masai` folder

  ### FSD.W1.1.2_12

  Make sure your file `profile.md` is synced and visible at the remote repo you created on github.

