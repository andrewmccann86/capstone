# Casting-Agency
## FullStack Nano-Degree Capstone Project

[Hosted on Heroku at: https://amc-casting-agency.herokuapp.com](https://amc-casting-agency.herokuapp.com)

The motivation for this project is to create my capstone project for Udacity's Fullstack Nanodegree program. It models a company that is responsible for creating movies and managing and assigning actors to those movies. The assumption is that I am an Executive Producer within the company and wants to create a system to simplify and streamline my process process.


## Project Dependencies
- **Python 3.7** - Follow instructions to install the latest version of python for your platform in the [python docs](https://docs.python.org/3/using/unix.html#getting-and-installing-the-latest-version-of-python)


- **Virtual Enviornment** - We recommend working within a virtual environment whenever using Python for projects. This keeps your dependencies for each project separate and organaized. Instructions for setting up a virual enviornment for your platform can be found in the [python docs](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/)


- **PIP Dependencies** - Once you have your virtual environment setup and running, install dependencies by running the below command. This will install all of the required packages we selected within the `requirements.txt` file:
```bash
pip install -r requirements.txt
```

- You may need to change the database url in setup.sh after which you can run:
```bash
source setup.sh
```

- The server can be started by running the following commands:
```bash
set FLASK_APP=app
set FLASK_ENV=development
set FLASK_DEBUG=True
flask run
```

- **Key Dependencies**
  - [Flask](http://flask.pocoo.org/)  is a lightweight backend microservices framework. Flask is required to handle requests and responses.

  - [SQLAlchemy](https://www.sqlalchemy.org/) is the Python SQL toolkit and ORM we'll use handle the lightweight sqlite database. You'll primarily work in app.py and can reference models.py. 

  - [Flask-CORS](https://flask-cors.readthedocs.io/en/latest/#) is the extension we'll use to handle cross origin requests from our frontend server. 

- **Authentication**
Authentication is implemented using Auth0, it uses RBAC to assign permissions using roles, these are tokens you could use to access the endpoints. Note: The tokens expires in 24 hours you can create your own tokens at [Auth0](https://auth0.com). you would need to refelct this in auth.py.

```bash
AUTH0_DOMAIN = '<your auth domain>'
ALGORITHMS = ['RS256']
API_AUDIENCE = '<your api audience>'
```
The most upto date tokens have been provided below:
>Casting Assistant: eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6InExeUFNVDZiMVJYcDVHVHdGU3B2eiJ9.eyJpc3MiOiJodHRwczovL2Rldi0wMmxucXV1dy5ldS5hdXRoMC5jb20vIiwic3ViIjoiYXV0aDB8NjEzYjUyNjdjNTQzNTYwMDZiNTEzOWIzIiwiYXVkIjoiY2FzdGluZyIsImlhdCI6MTYzMTgwNTA0MSwiZXhwIjoxNjMxODEyMjQxLCJhenAiOiJTVEZVc1NUWmJPMFg2bXFZQ1VhbDVwbFhqTWlTNFJ6bSIsInNjb3BlIjoiIiwicGVybWlzc2lvbnMiOlsiZ2V0OmFjdG9ycyIsImdldDptb3ZpZXMiXX0.W0F0WE0SDMBkFo9SYmvUvykEW_Ew3r6IMIhz5npPOIX1GugEdWfRmERHT0JGw7GmEW1zNxje96J3QUHhsa7nXFGeO9iosDpWHYUssqSVrHFOlI6qAucOUVYiXJZzrSpjsp1RBvyQS6bblDe7qLXsmPad421YmAVKc74LZt4jjZMRJ2mjtw1pBCGdbvox0iorwn261YGz6GTbncDNhxmiL7X5C8hHJTdsLKCIkldAN4iDe1xdNFmTQOEKGYx4A3y-y_y2kEtX-DgMG7rnJhAr6rIaQ2qyRKUjKYgN_x9jQWKpyw5OPfSvKDGo12TNpI2IuloQWPoqSJcbdbEd565cRw

>Casting Director: eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6InExeUFNVDZiMVJYcDVHVHdGU3B2eiJ9.eyJpc3MiOiJodHRwczovL2Rldi0wMmxucXV1dy5ldS5hdXRoMC5jb20vIiwic3ViIjoiYXV0aDB8NjEzYjUyOTFjNTQzNTYwMDZiNTEzOWM2IiwiYXVkIjoiY2FzdGluZyIsImlhdCI6MTYzMTgwNTE0MSwiZXhwIjoxNjMxODEyMzQxLCJhenAiOiJTVEZVc1NUWmJPMFg2bXFZQ1VhbDVwbFhqTWlTNFJ6bSIsInNjb3BlIjoiIiwicGVybWlzc2lvbnMiOlsiZGVsZXRlOmFjdG9ycyIsImdldDphY3RvcnMiLCJnZXQ6bW92aWVzIiwicGF0Y2g6YWN0b3JzIiwicGF0Y2g6bW92aWVzIiwicG9zdDphY3RvcnMiXX0.lM8DJSRkzE8xLaJskRbLGfLdHYJgdfQz0aWv9CI9KUhG9Ih-A4Gn2bBOn7NE1ZUIBghH-5qC-3XQbeeTXaJocVFwoF15gxKTydyH7Qmn0UIVkX8R-T3wqAiT_AHP8DXTHf5amhkU22s_Q_q98Eb0h_PALWQ51Un_DoG6tHY8_FOyvXC7uzyXk4ncGYkXUAqWbgfLqPi-lQQi3yXj_8yCLih0413oyyh17O_x5Aemqw5djapBTMYAZQ-FbIo3TkKP8jdtdqjAZ43o6zRtVaBVgczSBwa4wvHISWl1KowUNd_qhJandc-JHql6qsCvx8yjHjy37Zc2TQdcczGp6dIjeA

>Executive Producer: eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6InExeUFNVDZiMVJYcDVHVHdGU3B2eiJ9.eyJpc3MiOiJodHRwczovL2Rldi0wMmxucXV1dy5ldS5hdXRoMC5jb20vIiwic3ViIjoiYXV0aDB8NjEzYjUyYmFlZWMyZGMwMDY5MTA4NzBlIiwiYXVkIjoiY2FzdGluZyIsImlhdCI6MTYzMTgwNTI1MiwiZXhwIjoxNjMxODEyNDUyLCJhenAiOiJTVEZVc1NUWmJPMFg2bXFZQ1VhbDVwbFhqTWlTNFJ6bSIsInNjb3BlIjoiIiwicGVybWlzc2lvbnMiOlsiZGVsZXRlOmFjdG9ycyIsImRlbGV0ZTptb3ZpZXMiLCJnZXQ6YWN0b3JzIiwiZ2V0Om1vdmllcyIsInBhdGNoOmFjdG9ycyIsInBhdGNoOm1vdmllcyIsInBvc3Q6YWN0b3JzIiwicG9zdDptb3ZpZXMiXX0.GmdWmMwWG9LzhALpE72hOOD0blHUwMiH-JJPaU-iP-5WMGD31POSI_uYOuwlpZx1R5icvoaWh5TOxNgpjgVrzgV_MYBPy8vXxucCAdy2MXZANU97d4D9zoDYXIGOO2GJVLF467ZK1bIBjKNuAZDFaR0OFPYpyMt47i8EAYqaoCM2DEeNzWAVTTZACoUQP3Xb6qy89zq_IS1p1O1SclJD7Uik1fjCaR9YpTIctcYXtimXKqh35SLYjFjJfqFWmmHhl6WgrtkmsyIX6HG7WdIA-bS5JH8jqJ2CFKCRbD8ScKDK54U2LHbeue2Ql-wgax302MLUIm0hj-I1wwJ-xp0HHw

## API Documentation
This application can be run locally, although it is hosted as a base URL at: [https://amc-casting-agency.herokuapp.com](https://amc-casting-agency.herokuapp.com). Locally the app is hosted at http://127.0.0.1:5000/.

### Error Handling:
Errors are returned as JSON objects in the following format...
```
{
    "success": False,
    "error": 400,
    "message": "Bad Request"
}
```
The API will return three types of error when a request fails. These are listed below.
- 400: Bad request.
- 404: Not found.
- 422: Unprocessable entity.

### End Points
#### GET /movies

- General:
  - Returns all the movies.
  - Roles authorized : Casting Assistant,Casting Director,Executive Producer.


#### GET /movies/\<int:id\>

- General:
  - Route for getting a specific movie.
  - Roles authorized : Casting Assistant,Casting Director,Executive Producer.


#### POST /movies

- General:
  - Creates a new movie based on a payload.
  - Roles authorized : Executive Producer.


#### PATCH /movies/\<int:id\>

- General:
  - Patches a movie based on a payload.
  - Roles authorized : Casting Director, Executive Producer.


#### DELETE /movies/<int:id\>


- General:
  - Deletes a movies by id form the url parameter.
  - Roles authorized : Executive Producer.


#### GET /actors

- General:
  - Returns all the actors.
  - Roles authorized : Casting Assistant,Casting Director,Executive Producer.


#### GET /actors/\<int:id\>

- General:
  - Route for getting a specific actor.
  - Roles authorized : Casting Assistant,Casting Director,Executive Producer.


#### POST /actors

- General:
  - Creates a new actor based on a payload.
  - Roles authorized : Casting Director,Executive Producer.


#### PATCH /actors/\<int:id\>

- General:
  - Patches an actor based on a payload.
  - Roles authorized : Casting Director, Executive Producer.


#### DELETE /actors/<int:id\>


- General:
  - Deletes an actor by id form the url parameter.
  - Roles authorized : Casting Director,Executive Producer.


## Testing
To run the tests, run the following commands(The first time you run the tests there is no need to drop the database.):
```
dropdb agency_test
createdb agency_test
python test_app.py
```

##Authors
Andrew McCann



