ostman Introduction
Postman is an API client used to develop,test,share and document APIs.It is used for backend testing where we enter the end-point URL,it sends the request to the server and receives the response back from the server.The same thing can be accomplished through API template like swagger.

Request
A request is a combination of a complete URL(which includes all parameters or keys), HTTP,header,body or payload.

Collection
A collection is a repository/folder in which we can save all our requests.

How to create Collection & Request
Step 1: After opening your postman click the collection from the left sidebar.
Step 2: You will see + button click on this button and set an name you want
Step 3: Creating collection you add a request in collection repository
Step 4: Click 3dot(…) on collection you create then choose add request from dropdown
Step 5: Set a name of requset then choose a method from dropdown and given your link
Step 6: Once you have a complete request, click on the “Send button” and see the response code. A 200 OK code stands for successful operation. In the image below you can see that we have successfully hit the URL.
Environment
An environment is a set of variables you can use in your Postman requests. You can use environments to group related sets of values together and manage access to shared Postman data if you are working as part of a team.

How to create Environment
Step 1: Select an environment’s name to open the environment editor.
Step 2: To create a new environment, select Environments on the left and select +.
Step 3: Enter a name for your environment, and initialize it with any variables you need—you can alternatively specify variables for the environment later.
Step 4: Adding environment variables.Enter a name for your variable, and specify its Initial and Current values. By default the current value will copy the initial value.
Step 5: Creating your environment save it
Accessing environments
You can access your environment variables from Postman and from your request elements, including the URL, parameters, body data, and test scripts.
To use the variables in an environment, select it from the environment selector at the top right of Postman.

When you choose an environment using the environment selector, Postman treats it as the active environment and runs all requests against that environment (if your requests reference environment variables).

To use an environment variable value in a request, reference it by name, surrounded with double curly braces {{base_url}}

Save and click on the “Send button” and see the response code. A 200 OK code stands for successful operation. In the image below you can see that we have successfully hit the URL.

Postman | Newman | Report
What is Newman?
Newman is a cli(command line interface) tool which allows you to run a postman collection directly from the command line.

Install Newman
Prerequisite

NodeJs
To check if the node is installed or not, simply check the node version on your cmd using the below command.
$ node -v
If the command show any version it means that node is install in your PC.If not download node js from here https://nodejs.org/en/
After completing the node installation,you can install Newman from your cmd using the below command.

npm install -g newman
For confirmation you can also check the version in your cmd

newman -v
Running Collections Using Newman
To run a collection through Newman, we have two ways to proceed.

URL of the hosted collection
The collection in JSON format.
URL of the hosted collection
Step 1: Click on the 3 dots(…) besides the collection name.
Step 2: Click on Share select json link and copy the link
Step 3: Open your CMD and paste the link with below command
newman run <your JSON link>
Your collection has successfully executed if you have no dependency on the environment.

The collection is in JSON format
Step 1: Click on collection and export it to(recommended) JSON format
Step 2: Save the json file in your system and remember the directory.
Step 3: Open a command prompt and run the collection using Newman run command
newman run "Path/CollectionName.json"
Your collection has successfully executed if you have no dependency on the environment.

Newman Integration With Environment Variables
For a collection that does not rely on any environment variables, the collection could be simply executed using the Newman run command. But for collections, using the environment variables, we need to provide the environment variable JSON as well along with the collection JSON.

Step 1: Choose Environment based on your collection.Click three dots(…) and select export from dropdown.
Step 2: Save the json file in your system and remember the directory.
Step 3: Open a command prompt and run the collection using Newman run with enviroment command
newman run "Path/CollectionName.json" -e Path/EnvironmentName.json
Report Generation Using Newman
There are some custom node modules available for generating Newman test execution reports. We will walk through an example using a newman-html-reporter.
To generate report need to separately install newman report file using below command

npm install -g newman-reporter-htmlextra
Open a command prompt run the collection and generate report using Newman run with enviroment command

newman run "Collection Link" -e "Path/EnvironmentName.json" -r cli,htmlextra
After Enter you successfully generate a report with newman folder

Postman Test Snippets
Environment
How to set environment variable

pm.environment.set('name of Environment variable', 'value of variable')
How to set environment variable from your response

var jsonData =  pm.response.json();
pm.environment.set('Id',jsonData.bookingid)
How to get variable from environment

pm.environment.get('<name of Environment variable>')
console.log(pm.environment.get('<name of Environment variable>'))
How to delete variable from environment

pm.environment.unset('env_variable1'))
console.log(pm.environment.get('env_variable1'))
Global
How to set global variable in environment

pm.globals.set("variable_key", "variable_value");
How to set global variable from your response

var jsonData =  pm.response.json();
pm.globals.set('Breakfast',jsonData.booking.additionalneeds);
How to get global variable from environment

pm.globals.get("variable_key");  
console.log(pm.globals.get('<name of Environment variable>'))
How to delete global variable from environment

pm.globals.unset("variable_key");
Sending requests from scripts
You can use the pm.sendRequest method to send a request asynchronously from a Pre-request or Test script.

pm.sendRequest("https://restful-booker.herokuapp.com/booking/", function (err, response) {
    if (err) {
    console.log(error);
    } else {
     console.log(response.json());
    }
});
Test(pm.test)
Status Code

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
pm.test("Status code is 200", () => {
  pm.expect(pm.response.code).to.eql(200);
});
This test checks the response code returned by the API. If the response code is 200, the test will pass, otherwise it will fail. Select Send and go to the Test Results tab in the response area.
Using multiple assertions
Your tests can include multiple assertions as part of a single test. Use this to group together related assertions:

pm.test("The response has all properties", () => {
    //parse the response JSON and test three properties
    const responseJson = pm.response.json();
    pm.expect(responseJson.booking.additionalneeds).to.eql('Breakfast');
    pm.expect(responseJson.bookingid).to.be.a('number');
});
If any of the contained assertions fails, the test as a whole will fail. All assertions must be successful for the test to pass.

Reference
Postman JavaScript reference: Using variables
Test script examples: getting-started-with-tests
