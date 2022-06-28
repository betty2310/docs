---
title: Tue 28 Jun 2022
---

## Handle double click on table

When I view each row on the overview table of each object. I'd like to double click on this, and the detail table will be shown.

So, my task is handle double click on each row, get ID's object from it, and send to new scene.

#### Double Click

In Java, u should use class `MouseEvent` to get event of mouse. And the method `getClickCount()` will return the number of click.

```java
    if (mouseEvent.getClickCount() == 2 && !mouseEvent.isConsumed()) {
        // do something
    }
```
### Get data from selected row

With class `TableView` use to present the table. 

```java
    TableView<T> tableView = new TableView<T>();
    tableView.setOnMouseClicked(event -> {
        if (event.getClickCount() == 2 && !event.isConsumed()) {
            T selectedItem = tableView.getSelectionModel().getSelectedItem();
        }
    });
```
`T` is my data type. In my case, `T` is present for table of database. So, use `T.getID()` to get ID of object.

## UI

One thing I done to day is update UI of landing page. I found [materialFX](https://github.com/palexdev/MaterialFX) - a framework of JavaFX for make a beautiful component with material design. IT make button, checkbox, etc more beautiful.

But actually, just use little bit of it :v. 

![image](https://i.imgur.com/JSqY2jr.png)

