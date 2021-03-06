# Recipe-App-API

### Project Introduction 
This is a Recipe App API project written in a Test Driven Development (TDD) approach. The API endpoints are written using Python/Django. Application and database are containerized using Docker. 

### How To Run Locally
Build the docker: `docker build .` </br>
Run: `docker-compose up`</br>
Stop: `docker-compose down`</br>

### Travis CI Automation 
This project is synced with Travis CI. Whenever a commit is pushed to the master branch, all the unit tests will be run and linting will me checked. 

### Django Custom Admin and User Model 
The Django Admin is customized for this project: /admin </br>
To create a superuser, please run: </br>
`sudo docker-compose run app sh -c "python manage.py createsuperuser"`</br>

### Database 
Database is set up to be postgresql </br>
In the docker-compose file setting, it will wait for database migration before it starts django application: </br>
`sh -c "python manage.py wait_for_db && python manage.py migrate && python manage.py runserver 0.0.0.0:9001"`

### Endpoints
#### User management endpoints
1. Create User: api/user/create/
2. Create Token: api/user/token/
3. Manage User: api/user/me/
#### Recipe endpoints
1. Recipe Root: api/recipe
2. Recipe Tag List: api/recipe/tags/
3. Recipe Ingredient List: /api/recipe/ingredients/
4. Recipe Recipes List: /api/recipe/recipes/
5. Recipe Recipe: /api/recipe/recipes/int: id/
6. Reciep Recipe Upload Image: /api/recipe/recipes/int: id/upload-image/ 
7. Recipe Tags and Ingredients Filtering: /api/recipe/recipes/?tags = int: id & ingredient = int: id
8. Recipe Tags Assigned Only Filtering: /api/recipe/recipes/tags/assigned_only = int: id 
9. Recipe Ingredients Assigned Only Filtering: /api/recipe/recipes/ingredients/assigned_only = int: id 

### Tests
Unit tests for models, admin and all the api end points. 
