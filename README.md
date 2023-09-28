# Test Assignment: Docker Compose Configuration and CodeIgniter Controller Development

Objective: This test assignment is designed to assess your skills in configuring Docker Compose and developing a CodeIgniter controller with five essential functions. 
You will create a Docker Compose file with three containers (PHP, MySQL, and Redis) and develop a CodeIgniter controller with functions for basic CRUD operations.

## Instructions:

**Part 1: Docker Compose Configuration**

Configure the docker-compose.yml file to include the following three containers:

   1. PHP (app) container: As you can see there is already added PHP (web) container in docker-compose.yml file. 
All you need to do is, to fix/add/remove libraries in Dockerfile.development (so your container will run properly with Codeigniter 2)
   2. MySQL container: You need to configure .env variables, so mysql will read and configure mysql user and password
   3. Redis container: It's all set. It should work out of the box

**Part 2: CodeIgniter Controller Development**
 
Docs for Codeigniter 2 can be found on following url:
https://codeigniter.com/userguide2/

1. In your CodeIgniter 2 project, create a new controller named ToDoController.php.
2. Prepare migration file, which will create/generate database table to_do_lists, with following columns

| id (int(11), autoincrement) | title (varchar 255) | description (text) | date_from (TIMESTAMP) | date_to (TIMESTAMP) | finished (BOOLEAN) | date_created (TIMESTAMP DEFAULT CURRENT_TIMESTAMP) |
|:------------------------|:-------------------:|:-------------------:|:-------------------:|:-------------------:|:-------------------:|:-------------------:|

3. Inside ToDoController.php, develop five functions that correspond to the following CRUD operations:
   * getAll(): Retrieve and return all records from to_do_lists database table. 
   * get($id): Retrieve and return a single record based on the provided $id. 
   * create(): Insert a new record into the database. 
   * update($id): Update an existing record based on the provided $id. 
   * delete($id): Delete a record based on the provided $id.

4. Create View files (pages) where you will be able to create/read/update/delete ToDos.
 
**Implement proper error handling and validation for these functions.**

Bonus points:
- When a ToDo is created and successfully inserted into the database, store it in Redis.
- When a ToDo is fetched (via the "get" method), check if we already have the value in Redis. If it exists in Redis, return the result immediately. If it's not in Redis, read it from the database, store it in Redis, and then return the result.
- When a ToDo is updated and the update is successful, also update the entry in Redis. This ensures that you retrieve fresh and up-to-date results when calling the "get" method.
- When a ToDo is deleted, remove the corresponding entry from Redis.

Submission:
Be prepared to discuss your code and the choices you made during the interview.
Note: Please make sure your code is well-documented and follows best practices for Docker Compose and CodeIgniter development. Good luck with the assignment!
