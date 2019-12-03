## Week 18 Day 2

### SQL Part-7

**Primary Key & Auto Increment**

**Primary Key** - Unique Identifier

```mysql
CREATE TABLE users (
    id int NOT NULL AUTO_INCREMENT,
    name varchar(255) NOT NULL,
    PRIMARY KEY (id)
);
```

```mysql
CREATE TABLE countries (
    id int NOT NULL AUTO_INCREMENT,
    name varchar(255) NOT NULL,
    PRIMARY KEY (id)
);
```

**Foreign Key**

```mysql
CREATE TABLE users (
    id int NOT NULL AUTO_INCREMENT,
    name varchar(255) NOT NULL,
    country_id int,
    PRIMARY KEY (id),
    FOREIGN KEY (country_id) REFERENCES countries(id)
);
```

