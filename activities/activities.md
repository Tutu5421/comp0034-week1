# Week 1 flipped activities

## Set-up

You may need to alter your IDE (VS Code) to support HTML and CSS. Please check the documentation for your IDE.

- [HTML programming in VS Code](https://code.visualstudio.com/docs/languages/html)
- [HTML support in PyCharm](https://www.jetbrains.com/help/pycharm/editing-html-files.html)

To view HTML pages in a browser from VS Code requires an extension such as [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) to be installed. Once you have installed Live Server, if you right click on an HTML file in VS Code explorer then you can select an option to 'open with Live Server'. This opens the file in a browser.

You will need to a Python environment for the final activity only e.g create and activate a venv. Install Flask in the environment, e.g. run `pip install flask` or `python -m pip install flask` in the Terminal in VS Code or PyCharm.

## Activity 1: Create an html document [30 mins]

Read [html_intro.md](/activities/html_intro.md)

For this course, you will not write a lot of HTML. You will need to:

- be able to create a basic HTML document structure with head and body; and understand the purpose of each and what they contain
- understand the general syntax of HTML tags; and know where to find an HTML reference that explains how to use specific tags.

Aim to complete the activities before the lab session if possible, then use the session to ask questions.

By convention the main page of a website is often called  `index.html`.

Create a new html file called `index.html`.

The following code provides a basic html page structure. Add this to `index.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>Add page title here</title>
</head>
<body>
<!-- Add the main page elements here -->
</body>
</html>
```

Add the html elements listed below to the body of the html page. Add content to each of the elements (this is not given to you in the code below, you will need to read the reference and then add appropriate content yourself!).

[W3 schools HTML element reference](https://www.w3schools.com/tags/default.asp)

HTML elements to add:

```html
<title></title>
<h1></h1>
<ol>
    <li></li>
</ol>
<p><a href=""></a></p>
<img src="" alt="" height="" width="">
<table>
    <tr>
        <td></td>
    </tr>
</table>
```

## Activity 2: Add CSS styling your html [30 mins]

Read [css_intro.md](/activities/css_intro.md)

For this course you are not expected to write any CSS; further there are no marks in the coursework for writing CSS. You do need to understand what CSS is and how to apply CSS styling to your HTML elements.

This first activity introduces you to using an external stylesheet that you create yourself so you understand the structure and syntax. However, in the coursework you are more likely to use a third party stylesheet, ie an open source stylesheet created by someone else.

Create a stylesheet called `mystyles.css`

Add a link to the stylesheet in the `<head>` section of your html, e.g.

```html

<head>
    <link rel="stylesheet" type="text/css" href="mystyles.css">
</head>
```

Add styling for the html elements you included in your html.

The general syntax is explained here: [W3Schools CSS syntax](https://www.w3schools.com/css/css_syntax.asp)

A reference for the selectors is here: [W3Schools CSS reference](https://www.w3schools.com/cssref/default.asp)

```css
h1 {
    color: plum;
    text-decoration-line: underline;
}

img {
}

ol {
}

li {
}

a {
}

table {
}

tr {
}

th {
}

td {
}
```

## Activity 3: Use bootstrap to make your page follow a responsive design

Read [responsive_intro.md](/activities/responsive_intro.md)

For this course you are encouraged to use a third-party CSS such as Bootstrap. If used correctly, then a web page using Bootstrap should adhere to responsive design principles.

Replace your `mystyles.css` stylesheet with the [Bootstrap styles](https://getbootstrap.com/docs/5.2/getting-started/introduction/).

You will need to add the `<meta>` tag as well as the link to the online version of the stylesheet (or download the stylesheet and save to your folder, this is explained in their getting started documentation).

You also need to wrap your body content in a [container](https://getbootstrap.com/docs/5.2/layout/containers/).

```html
<head>
    <!-- Refer to https://getbootstrap.com/docs/5.2/getting-started/introduction/ -->
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous"> 
</head>
<body>
<div class="container">
  <!-- Content here -->
</div>
</body>

```

What does your page look like now?

To change the style of each of the elements on your page, you should apply specific Bootstrap styles to them also.

For example, remove any height and width tags from your image and instead add [Bootstrap image styling]() e.g.

```html
<img src="https://upload.wikimedia.org/wikipedia/commons/9/9e/Iris_sanguinea.JPG" alt="Iris" class="img-fluid">
```

Open the page in Live Server and see what happens to the image when you make the browser smaller and larger. Remove the Bootstrap class property to see the non-responsive version of the image.

## Activity 4: Create a basic Flask app

There are many freely available Flask tutorials; such at the one in the [Flask documentation](https://flask.palletsprojects.com/en/2.2.x/tutorial/) or the [VS Code Flask tutorial](https://code.visualstudio.com/docs/python/tutorial-flask).

This activity aims to give you 'just enough' knowledge to get a basic Flask webpage that uses both HTML and Bootstrap CSS. It is adapted from '[A minimal application](https://flask.palletsprojects.com/en/2.2.x/quickstart/#a-minimal-application)' in the Flask documentation.

To complete this activity you will need to have a Python environment in which Flask has been installed (see setup at the start of this document).

Create a Python file to launch the Flask app. Do not call it `flask.py` as this conflicts with Flask itself. `app.py` or the name of your app is a more typical name.

Add the following code. This creates an instalve of the Flask class which is our web app.

The route decorator tells Flask what URL to trigger the function. In this case we want the URL for our homepage `index`.

When the function for the route is called, it will return HTML paragraph tag with the words 'hello world'.

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def index():
    return "<p>Hello, World!</p>"
```

To run the app in VS Code, go to Terminal and type `flask --app run` where --app tells Flask where you app code is. If this is in a directory, e.g. in the `flask_app` directory then you would type `flask --app flask_app/app run`.

Note: if you saved your python file (e.g. `app.py`) in a directory other than the root of the project, you will need to set an envio e.g. `export FLASK_APP=hello`. Please refer to the documentation here as the syntax for mac and windows is different.

To run the app in PyCharm, you should be able to run it using the green arrow run function from within the python file.
