# KavinToDoApp

a simple To-Do list application built using Flask and SQLAlchemy.<br>


1)//Create project with virtual environment<br>
> mkdir myproject<br>
> cd myproject<br>
> py -3 -m venv venv<br>

2)//activate the environment(Windows)<br>
venv\Scripts\activate<br>

3)Install Flask and Flask-SQLAlchemy which is used for our database.<br>
pip install Flask==2.1.0<br>
pip install Flask-SQLAlchemy==2.5.1<br>

4)Install the jinja2 template engine<br>
pip install Jinja2<br>

5)sets the environment variable FLASK_APP to the value "app.py".<br>
set FLASK_APP=app.py<br>

6)tells Flask to run the application in development mode<br>
set FLASK_ENV=development<br>

Database =we use SQLAlchemy and SQLite Database<br>
The application uses SQLAlchemy to interact with the SQLite database and the Todo model is defined as a class that inherits<br>
from db.Model. The class has 3 attributes, id, title and complete, which are defined as columns in the database table. The<br>
code also initializes the database and creates the table when the script is run.<br>


This app is capable of<br>
a. Add new TODOs<br>
b. Delete existing TODOs<br>
c. List existing TODOs<br>
d. Update -finished or incomplete<br>
e. Index in order <br>
Simple API that has three endpoints to perform above three tasks would be enough, No<br>
need to implement any authentication mechanism, keep it simple.<br>

Endpoints/routes to add, delete, and update new todos<br>
1)@app.route("/"): This route renders the home page which lists all the To-Do items from the database.<br>
2)@app.route("/add", methods=["POST"]): This route handles adding a new To-Do item to the database. It gets the title of the new<br>
                                        item from the form data and creates a new Todo object with the title and complete set to False.<br>
3)@app.route("/update/<int:todo_id>"): This route updates the completion status of a Todo item in the database by toggling the complete attribute.<br>
4)@app.route("/delete/<int:todo_id>"): This route deletes a Todo item from the database.<br>
