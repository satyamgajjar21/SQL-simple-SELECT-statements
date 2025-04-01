## Hands-on Lab: Simple SELECT Statements

### Estimated time needed: 20 minutes

In this lab, you will learn one of the most commonly used statements of SQL (Structured Query Language), the **SELECT** statement.

The **SELECT** statement is used to select data from a database.

## Objectives

After completing this lab, you will be able to:

- Query a database to obtain a response as a result set
- Retrieve all or selected columns of a dataset
- Apply criteria commands to filter the result set

## Software Used in this Lab

In this lab, you will use **Datasette**, an open-source tool for exploring and publishing data. You can visit the repository here:  
[Datasette GitHub](https://github.com/simonw/datasette)

The **Datasette** tool offers a platform to input and execute SQL queries. By clicking the **Submit query** button, you can execute the SQL query.

---

## Database Used in this Lab

The database used in this lab comes from the following dataset source:  
**Film Locations in San Francisco** under a **Domain Dedication and License**.

### Exploring the Database

Let's first explore the **SanFranciscoFilmLocations** database using the **Datasette** tool:

1. If the first statement listed below is not already in the Datasette textbox on the right, then copy the code below by clicking on the little copy button on the bottom right of the code block below and then paste it into the textbox of the **Datasette** tool using either **Ctrl+V** or right-click in the text box and choose **Paste**.

   ```sql
   SELECT * FROM FilmLocations;
   ```

2. Click **Submit Query**.
3. Now, you can scroll down the table and explore all the columns and rows of the **FilmLocations** table to get an overall idea of the table contents.

### Column Attribute Descriptions

The **FilmLocations** table has the following attributes:

```plaintext
FilmLocations(
  Title: titles of the films,
  ReleaseYear: time of public release of the films,
  Locations: locations of San Francisco where the films were shot,
  FunFacts: funny facts about the filming locations,
  ProductionCompany: companies who produced the films,
  Distributor: companies who distributed the films,
  Director: people who directed the films,
  Writer: people who wrote the films,
  Actor1: person 1 who acted in the films,
  Actor2: person 2 who acted in the films,
  Actor3: person 3 who acted in the films
)
```

---

## Using SELECT Statement

### Example Queries

1. **Retrieve all details of all films from the `FilmLocations` table**

   ```sql
   SELECT * FROM FilmLocations;
   ```

2. **Retrieve the film names, director, and writer names**

   ```sql
   SELECT Title, Director, Writer FROM FilmLocations;
   ```

3. **Retrieve film names along with filming locations and release years for films released in 2001 and onwards**

   ```sql
   SELECT Title, ReleaseYear, Locations FROM FilmLocations WHERE ReleaseYear >= 2001;
   ```

---

## Practice Exercises on the SELECT Statement

1. **Retrieve the fun facts and filming locations of all films**

   ```sql
   SELECT FunFacts, Locations FROM FilmLocations;
   ```

2. **Retrieve the names of all films released in the 20th century and before (release years before 2000 including 2000), along with filming locations and release years**

   ```sql
   SELECT Title, ReleaseYear, Locations FROM FilmLocations WHERE ReleaseYear <= 2000;
   ```

3. **Retrieve the names, production company names, filming locations, and release years of the films not written by James Cameron**

   ```sql
   SELECT Title, ProductionCompany, Locations, ReleaseYear FROM FilmLocations WHERE Writer <> 'James Cameron';
   ```

---

## Conclusion

Congratulations on completing this lab!

You are now able to:

- Query a database using **SELECT** statements
- Retrieve all or selected columns of data
- Filter the query response to meet defined criteria

---

### Author(s)
- **Sandip Saha Joy**

### Other Contributor(s)
- **Abhishek Gagneja**

© IBM Corporation 2023. All rights reserved.
