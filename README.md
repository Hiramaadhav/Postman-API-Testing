Restful-Booker API Testing with Postman 🚀
This repository contains API test cases for the Restful-Booker application, created and executed using Postman.
It covers CRUD operations, environment variables, pre-request scripts, and test scripts.
Additionally, it includes instructions for running the collection using Newman.

📌 1. Getting Started
✅ Prerequisites
Postman installed

Newman installed for CLI execution

Node.js installed (for Newman)

✅ Installation Steps
Clone the repository:

bash
Copy
Edit
git clone <repository_url>
cd restful-booker-postman
Install Newman globally:

bash
Copy
Edit
npm install -g newman
🔥 2. Environment Setup
✅ Environment Variables
The project uses environment variables to dynamically store values like base URLs and auth tokens.

🌐 Environment Variables Example
Variable	Value	Description
baseUrl	https://restful-booker.herokuapp.com	API base URL
authToken	{{token}}	Authentication token
bookingId	{{bookingId}}	Dynamic booking ID
🚀 3. CRUD Operations
✅ Endpoints Used
HTTP Method	Endpoint	Description
GET	/booking	Fetch all bookings
POST	/booking	Create a new booking
GET	/booking/:id	Get booking by ID
PUT	/booking/:id	Update booking by ID
DELETE	/booking/:id	Delete booking by ID
🔥 4. Postman Collection & Environment
✅ Collection Files
Restful-Booker.postman_collection.json → Contains all CRUD operations

Restful-Booker-Environment.postman_environment.json → Environment variables

🌐 Collection Overview
Create Booking (POST)

Adds a new booking with dynamic data

Validates response status and body

Get Booking (GET)

Fetches all booking records

Validates status and response

Update Booking (PUT)

Updates an existing booking

Verifies the updated data

Delete Booking (DELETE)

Deletes a booking by ID

Verifies status code and response

🔥 5. Running Collection with Newman
✅ Run Collection
To run the collection using Newman:

bash
Copy
Edit
newman run Restful-Booker.postman_collection.json -e Restful-Booker-Environment.postman_environment.json
✅ Run Collection with HTML Report
bash
Copy
Edit
newman run Restful-Booker.postman_collection.json -e Restful-Booker-Environment.postman_environment.json --reporters cli,html --reporter-html-export report.html
🔥 6. Tests and Scripts
✅ Pre-request Scripts
The project uses pre-request scripts to generate dynamic data like random names, dates, and tokens.

javascript
Copy
Edit
// Generate random names
const firstNames = ["Aryan", "Maadhav", "Rohan", "Shivam"];
const lastNames = ["Sharma", "Hira", "Kumar", "Verma"];

const randomFirstName = firstNames[Math.floor(Math.random() * firstNames.length)];
const randomLastName = lastNames[Math.floor(Math.random() * lastNames.length)];

pm.environment.set("firstName", randomFirstName);
pm.environment.set("lastName", randomLastName);
✅ Test Scripts
Tests are written in JavaScript using Chai.js assertions.

javascript
Copy
Edit
// Validate status code
pm.test("Status code is 200", () => {
    pm.response.to.have.status(200);
});

// Validate response time
pm.test("Response time is less than 500ms", () => {
    pm.expect(pm.response.responseTime).to.be.below(500);
});

// Validate response contains booking ID
pm.test("Response contains booking ID", () => {
    pm.expect(pm.response.text()).to.include("bookingid");
});
🔥 7. Reports and CI/CD Integration
✅ Newman HTML Reports
The collection generates detailed HTML reports after execution.

View the report by opening the report.html file in your browser.

✅ Jenkins Integration
To integrate into Jenkins:

Install the Postman and Newman plugins.

Add a build step to run Newman:

bash
Copy
Edit
newman run Restful-Booker.postman_collection.json -e Restful-Booker-Environment.postman_environment.json --
