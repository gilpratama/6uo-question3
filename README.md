# Link to Other Questions and Answer
[Question 1](https://github.com/gilpratama/6uo-question1 "Question 1")

[Question 2](https://github.com/gilpratama/6uo-question2 "Question 2")

[Question 3](https://github.com/gilpratama/6uo-question3 "Question 3")

Answers are available on the bottom of the page

# Question 3: Troubleshooting React App Data Fetching

Background:

You've been provided with a React application designed to retrieve data from the backend of the "SecureLogin" web application project, which you've encountered in question 1. The frontend React app is integrated with the backend using API requests to fetch data.

The React app's primary function is to display data retrieved from the backend. The app architecture involves components, states, and asynchronous data fetching using JavaScript's built-in fetch() function.

Task:

Upon reviewing the React app's code, you've noticed that there's an issue affecting the data fetching process. Candidates are expected to identify the problem, explain the root cause, and propose a solution to resolve it.  

Deliverables:

- A concise description of the identified issue and the root cause.
- A clear and logical explanation of why the issue is occurring.
- A step-by-step resolution plan, including any code changes or adjustments required.

If applicable, candidates can include code snippets to illustrate their proposed solution.  

Note:

Candidates are not required to implement the solution in code. Focus on identifying the problem, diagnosing the root cause, and suggesting a solution.

# Answer

Based on my experience on the task and assignment given, these are my answer:

## Root Cause
Developer are unable to fetch the database because of SQL error on Docker Image, I have been trying to create the docker image both on Windows and Mac using MySQL and MariaDB (Mac doesnt support MySQL at the moment) and still resulting error on both device.

#### Incomplete MySQL Initialization: 
MySQL might not have been initialized correctly, which can result in missing or corrupted system tables.

#### Incorrect MySQL Configuration: 
The MySQL configuration might not be properly set up, leading to issues with the initialization process.

## Explanation
The error message I encountering when running docker-compose up -d mysql seems to be related to MySQL and not directly related to the React application. However, I can provide some guidance on how to approach this issue and explain the possible root cause.

## Resolution

Check Docker Compose Configuration:
Ensure that your docker-compose.yml configuration is correct and points to the right MySQL image and version. Double-check the configuration, especially the environment variables like MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, and others.

#### Data Volume: 
If you have a data volume specified in your docker-compose.yml, try removing it temporarily to rule out any potential issues with data persistence.

### Initialize MySQL Properly:
It's essential to ensure that MySQL initializes correctly. You can do this by deleting the existing MySQL data directory:

`rm -rf /path/to/mysql-data-directory`

Replace /path/to/mysql-data-directory with the actual path to your MySQL data directory specified in your Docker Compose file.

#### Recreate MySQL Container:
After deleting the data directory, recreate the MySQL container using docker-compose up -d mysql.

#### Check MySQL Container Logs:
After recreating the container, check the container logs to see if MySQL starts without errors:

`docker logs mysql`

Look for any error messages and address them accordingly.

#### Connect React App to MySQL:
Once you have MySQL up and running without errors, ensure that your React application's configuration is correctly connecting to the MySQL instance. Check your React app's environment variables or configuration files to make sure they match the MySQL container settings.
