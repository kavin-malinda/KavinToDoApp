# KavinToDoApp

Flask is a micro web framework for Python that is often used to build RESTful APIs. 
It provides a simple and flexible way to create web applications and APIs by providing a
minimal set of tools for handling HTTP requests and responses. Flask provides a lightweight
and easy-to-use framework for creating web applications and APIs, with support for routing, 
request handling, and other common web development tasks.


1)//Create project with virtual environment
> mkdir myproject
> cd myproject
> py -3 -m venv venv

2)//activate the environment(Windows)
venv\Scripts\activate

3)Install Flask and Flask-SQLAlchemy which is used for our database.
pip install Flask==2.1.0
pip install Flask-SQLAlchemy==2.5.1

4)Install the jinja2 template engine
pip install Jinja2

5)sets the environment variable FLASK_APP to the value "app.py".
set FLASK_APP=app.py

6)tells Flask to run the application in development mode
set FLASK_ENV=development

Database =we use SQLAlchemy and SQLite Database
The application uses SQLAlchemy to interact with the SQLite database and the Todo model is defined as a class that inherits
from db.Model. The class has 3 attributes, id, title and complete, which are defined as columns in the database table. The
code also initializes the database and creates the table when the script is run.


This app is capable of
a. Add new TODOs
b. Delete existing TODOs
c. List existing TODOs
d. Update -finished or incomplete
e. Index in order 
Simple API that has three endpoints to perform above three tasks would be enough, No
need to implement any authentication mechanism, keep it simple.

Endpoints/routes to add, delete, and update new todos
1)@app.route("/"): This route renders the home page which lists all the To-Do items from the database.
2)@app.route("/add", methods=["POST"]): This route handles adding a new To-Do item to the database. It gets the title of the new
                                        item from the form data and creates a new Todo object with the title and complete set to False.
3)@app.route("/update/<int:todo_id>"): This route updates the completion status of a Todo item in the database by toggling the complete attribute.
4)@app.route("/delete/<int:todo_id>"): This route deletes a Todo item from the database.
