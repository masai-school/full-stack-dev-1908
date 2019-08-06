# Week 1 - Day 1

#### Assignments

Create a folder called `repos` inside your home directory  
Clone the following Data Repository, https://github.com/masai-school/assignments-data 

## FSD.W1.1.A (10 min)

Go the `assignments-data` folder  
Organize the food items into their respective folders. The `data/food` folder contains a list of food items which are fruits, vegetables and meat.  
Organise (move) them into their respective folders inside the `food` folder.   
The names of the respective folders should be `fruits` `vegetables` `meats`.

## FSD.W1.1.B (10 min)

Lets create a new superhero team. The `data/superheros/avengers` folder also contains the Guardians of the Galaxy profiles for each Guardian (Drax, Gamora, Groot, Mantis, Rocket, Star Lord).  
Create a new team (folder) under the `superheros` folder called `guardians` with their profiles but also let them stay in the `avengers` team (folder).

## FSD.W1.1.C (10 min)

Create duplicate profiles of some of the superheros with their original names in the `original` folder under `superheros` folder.  
The following are the original names of the superheroes: 

```
iron_man >  tony_stark 
batman > bruce_wayne 
flash > barry_allen 
hulk > brunce_banner
```

## FSD.W1.1.D (20 min)

Your application created a lots of logs with the `.log` extension and dumps with the `.dump` extension files over the past years. The logs are of 2 categories, access and error logs.  
The logs and dumps for the years 2014-2016 are placed in the `archive` folder.  
You have been assigned the task to clean and organize the logs, with the following conditions mentioned below. Perform them in the same order as given:

1. Clean all the logs from 2014-2016 in archive folder
2. Clean all the logs for the year 2017
3. Clean all the access logs for the year 2018 
4. Create two folders called `access` and `error` inside `logs` and move the remaining logs into the respective folders according to their category
5. Rename the `archive` folder to `dumps` and move all the dump files into that folder
6. move the `dumps` folder outside (parent) of the `logs` folder

## FSD.W1.1.E (15 min)

**Submission of your assignment**

Go to `repos` folder inside your home directory  
Clone the repo https://github.com/masai-school/cohort_2

Navigate to folder  `~/repos/assignments-data` directory and execute the below command. Replace `<firstname_lastname>` with your own first name and last name. 

```
ls -1R data/ > <firstname_lastname>.txt
```
This should create a file with the given name.   
Copy this file in the `cohort_2` repo inside the folder `submissions/<your_folder>/week_1/day_1/assignments/`  (create the folders of they don't exist). Then, commit and push the file to the online GitHub repository.
