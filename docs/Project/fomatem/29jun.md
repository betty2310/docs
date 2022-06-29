---
title: Wed 29 Jun 2022
---

## Static variables

The biggest task done to day is handle fitlers from user. Like text field, checkbox, etc.
With text field, to get text in present, use method `getText()` and same for checkbox and etc. But because the handle data from user scene need that fitler data, not the scene display this. So, we need to pass the fitler data to the that scene.

=== "Fitler.java"
    ``` java
    class Fitler {
        public TextField textField;
        public void handleClick(e -> {
            /*
            call data scene
            */
        })
    }
    ```
=== "Data.java"
    ``` java
    class Data {
        String data = new Fitler().textField.getText();
    }
    ```

Is that right? Oh, no, it's not. Because `new Fitler()` will create a new instance of `Fitler` class. So, the `textField` will be different for each instance of `Fitler`. So, we create new static variable `_textField` and in `hanleClick` method, pass the value of `textField.getText()` to the `_textField`.

=== "Fitler.java"
    ``` java
    class Fitler {
        public TextField textField;
        public static String _textField;
        public void handleClick(e -> {
            _textField = textField.getText();
            /*
            call data scene
            */
        })
    }
    ```
=== "Data.java"
    ``` java
    class Data {
        String data = Fitler._textField;
    }
    ```
It is my solution to solove problems today. So happy but feel something wrongs :v. Maybe I don't understand so much about Java.

But more practive more vjp pro soon, right?

## Separate code of each object from landing page

Before, the landing page contain all the code of each `Footballer`, `Coach`, `Club`. Today, I add fitler to each object,  this file is like spaghetti code 🍝.

This project structure now is like this:

```
├──ClubPane.java
├──CoachPane.java
├──FootballerPane.java
├──LandingPage.java
└──Main.java
```

And last, some show case image

![](https://imgur.com/QR4FJbX.png)

And the club overview also done today

![](https://i.imgur.com/ERu7Ms6.png)

