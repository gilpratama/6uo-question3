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
The root cause of the issue with data fetching using JavaScript's built-in fetch() function in the React app cannot be definitively determined based on the code provided, but we can identify some potential root causes and discuss them further

To identify the root cause, we should carefully review the client-side code, consider the factors mentioned above, and use browser developer tools or debugging techniques to inspect network requests and responses for more detailed error information.

These are the potential issue that affecting the data fetching process:

##### Server Unavailability
One possible root cause could be that the server hosting the API is not available or not running when the React app is making fetch requests. If the server is down or experiencing issues, it won't be able to respond to client requests.

##### Incorrect API Endpoint
If the React app is trying to fetch data from an incorrect or non-existent API endpoint, it will not receive the expected data. The root cause, in this case, would be a misconfiguration of the API endpoint URL in the fetch() request.

##### CORS (Cross-Origin Resource Sharing) 
If the React app is hosted on a different domain or port than the server, CORS restrictions might be blocking the fetch requests. This could be due to improper CORS configuration on the server side or a mismatch between the client and server domains.

##### Network Issues
General network issues, such as a lack of internet connectivity or firewall restrictions, can prevent the fetch requests from reaching the server or receiving responses.

##### Authentication and Authorization
If the server requires authentication, but the fetch request is not providing valid credentials, the server may reject the request. Authentication-related issues could include incorrect tokens or missing authentication headers.

##### Error Handling
If the React app is not handling fetch errors properly, it may fail silently when a network or server error occurs. This would lead to a perception that data fetching is not working, when in fact, it's encountering errors but not reporting them.

##### Response Format
If the server is not sending responses in the expected format (e.g., not sending valid JSON when the client expects JSON data), the client-side code may fail to parse the response correctly, resulting in apparent data fetching issues.

##### Testing Environment
The issue could be specific to the testing environment setup. Ensure that the testing environment has network access to the server, and any mocking or stubbing of fetch requests in tests accurately reflects the behavior of real fetch requests.

## Resolution

To resolve the issues with data fetching using JavaScript's fetch() function, we will need to address the potential root causes mentioned earlier. Here are resolutions for each of those potential issues:

##### Server Unavailability:

Ensure that the server hosting the API is running and accessible.
Check server logs for any errors or issues that might be causing downtime.
Verify that the server is correctly configured to listen for incoming requests.

##### Incorrect API Endpoint:

Double-check and verify that the endpoint URL in your fetch() requests is accurate and matches the actual server API endpoint.
Ensure that the endpoint path and any query parameters are correctly formed.

##### CORS (Cross-Origin Resource Sharing) Issues:

Configure the server to allow requests from your React app's domain by setting up CORS headers.
Make sure that the client and server domains match (including protocol, port, and domain).
Consider using a proxy server if CORS restrictions cannot be resolved directly.

##### Network Issues:

Ensure that the client machine has internet connectivity and can access the server's domain.
Check for firewall or network restrictions that may be blocking outgoing requests.
Verify DNS settings to ensure proper domain resolution.

##### Authentication and Authorization:

If authentication is required, ensure that the fetch() requests include the necessary authentication tokens or headers.
Verify that the authentication information (e.g., tokens) is correctly generated and passed to the server.

##### Error Handling:

Implement proper error handling for fetch() requests in your React app. Use .catch() with fetch or a try...catch block to capture and handle errors.
Log error messages or display user-friendly error messages when fetch requests fail.

##### Response Format:

Ensure that the server is sending responses in the expected format (e.g., JSON) and with the correct content type headers.
Use .json() to parse JSON responses when processing data from fetch() requests.

##### Testing Environment:

Validate that your testing environment accurately simulates the behavior of real fetch() requests and responses.
Review your testing configurations and mock/stub implementations to ensure they are correct.
