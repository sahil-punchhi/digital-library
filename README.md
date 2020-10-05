# Digital Library

Application for customers who would like to store information on the different books they have read.


## Deployment instructions

(Download this project from GitHub:)
```
git clone https://github.com/Mate-work/Project-Integration.git
cd libraryproject
```

You may set up a Python virtual environment
and install the required Python packages.
Use Python3.7
```

pip install -r requirements.txt  
```
If pip successfully installed all the required packages, that is a success!

Run the backend server,
```
python manage.py runserver  
```  
Go to http://localhost:8000/login/


## Unit tests

Run the following command once you are inside 'libraryproject' folder to perform the unit tests. You can set the 'flag' to 'False' in library/tests.py file to False if you don't want to print statements on the terminal explaining the test cases.
```
python manage.py test
```


## User guide and main features

### Add a book
User can add a book by clicking on 'Add a Book' tab in the sidebar of homepage. A book can be added only if user has logged into the system. This page opens a form which requires 3 fields - 'Title', 'Author' and 'ISBN'. Once user clicks on 'submit' button, ISBN field is validated using Google Books API and upon successful validation, new book is added to user's list of books. The system automatically keeps track of the book addition time.

### View a collection
User can view a collection by clicking on 'View Books' tab in the sidebar of homepage. This is also the homepage for the user. Book collection can only be viewed if user has logged into the system.

### View a collection over the last x number of days
User also has an option to view collection he/she has added over the specific number of last days. This can be done by entering the number of days on 'View Books' tab and the book collection will accordingly change. Example: enter '7' if you want to view the book collection you have added in last 7 days.

### Delete a book
User can delete a book by clicking on 'Delete a Book' tab in the sidebar of homepage. A book can be deleted only if user has logged into the system. This page shows list of all the user's books and asks the user to delete a particular book from the current collection by entering the book 'title' or book 'ISBN'.

### Google Books API
'Goob' service through 'isbntools' library is used for validating ISBN number. This is a free service and does not require API key.

### Validation of country field
django-countries library is used for validating country field. A list of countries is shown from which user can select a particular country. This field cannot be left blank.



## File structure documentation

### Backend  

**libraryproject/db.sqlite3**  
Database  

**libraryproject/libraryproject/settings.py**  
Django settings file

**libraryproject/libraryproject/urls.py**  
URL mappings file

**libraryproject/manage.py**
Django runner file  

**libraryproject/library/admin.py**  
Admin settings file

**libraryproject/library/views.py**  
General API views

**libraryproject/library/addBook.py**  
Book Form to add a new book

**libraryproject/library/migrations/**
Database migration files directory

**libraryproject/library/models.py**  
Object Relational Mappings file

**libraryproject/library/serializers.py**  
Object serializers file

**libraryproject/register/forms.py**  
Register form to add a new user

**libraryproject/register/views.py**  
Register view

**libraryproject/requirements.txt**  
Packages and dependencies requirements file


## FAQ

Q: How to view your source code?
A: I prefer you to use Atom IDE.

Q: What are the assumptions made?
A: ISBN number is 13 digits and is considered without dashes and spaces.

Q: How are books validated?
A: Books are validated by matching ISBN number from Google Books API. 'Goob' service through 'isbntools' library is used for validation.

Q: What are the constraints used?
A: Various constraints are used for password field, email field, username, country field. A user cannot add/ delete/ view book unless he/she is logged in.

Q: How is front end code developed?
A: Bootstrap and crispy forms are used for developing front end code.

Q: Where are uni tests stored?
A: Unit tests are written in "/library/tests.py"
