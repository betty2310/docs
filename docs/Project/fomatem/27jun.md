---
title: Mon 27 Jun 2022
---

## Database
Connect to the local postgreSQL database today. I use JBDC - an API for Java that defines how clients may access a database.
Make a connection using:

```java title="Database.java"
public Connection connection() {
        Connection conn = null;
        try {
            conn = DriverManager.getConnection(url, user, pass);
        } catch (SQLException e) {
            System.out.println(e.getMessage());
        }
        return conn;
    }
```

+ `url`: the URL of the database: `jbdc:postgresql://servername:port/dbname`
+ `user`: the username to connect to the database
+ `pass`: the password to connect to the database

After that, when I want to access my own. I can use the `connection()` method to get a connection to the database.

```java
Database db = new Database();
Connection connection = db.connection();
```

## Get data from database

The basic step is:

+ Create `TableView` 
+ Creat `TableColumn`
+ Get data from the database:
    ```java
    String query = "SELECT * FROM users";
    ResultSet rs = connection.createStatement().executeQuery(query);
   ```
+ Add data to each column and finally table.

For more details, see [code](https://github.com/betty2310/FOMATEM/blob/9339b041801ce140a6a033129cf8d135c26641cb/App/src/main/java/com/betty2310/app/FootballerOverview.java#L31)

## Application

As I mentioned in the last post, if I click on query button, the overview of the object will show in a new scene. Its display on table is based on the data in the database. The table always has ID column, so I want if I double click on a row, the detailed data of object also show in a new scene.

``` mermaid
graph LR
    A[dashboard] -->|query| B[overview] -->|id| C[detail];
```

And results today 😀

<blockquote class="imgur-embed-pub" lang="en" data-id="a/W4EER59"  ><a href="//imgur.com/a/W4EER59">video demo</a></blockquote><script async src="//s.imgur.com/min/embed.js" charset="utf-8"></script>