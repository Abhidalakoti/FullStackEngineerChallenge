# Full Stack Developer Challenge
This is an interview challengs. Please feel free to fork. Pull Requests will be ignored.

## Requirements
Design a web application that allows employees to submit feedback toward each other's performance review.

*Partial solutions are acceptable.*  It is not necessary to submit a complete solution that implements every requirement.

### Admin view
* Add/remove/update/view employees
* Add/update/view performance reviews
* Assign employees to participate in another employee's performance review

### Employee view
* List of performance reviews requiring feedback
* Submit feedback

## Challenge Scope
* High level description of design and technologies used
* Server side API (using a programming language and/or framework of your choice)
  * Implementation of at least 3 API calls
  * Most full stack web developers at PayPay currently use Java, Ruby on Rails, or Node.js on the server(with MySQL for the database), but feel free to use other tech if you prefer
* Web app
  * Implementation of 2-5 web pages using a modern web framework (e.g. React or Angular) that talks to server side
    * This should integrate with your API, but it's fine to use static responses for some of it 
* Document all assumptions made
* Complete solutions aren't required, but what you do submit needs to run.

## How to complete this challenge
* Fork this repo in github
* Complete the design and code as defined to the best of your abilities
* Place notes in your code to help with clarity where appropriate. Make it readable enough to present to the PayPay interview team
* Complete your work in your own github repo and send the results to us and/or present them during your interview

## What are we looking for? What does this prove?
* Assumptions you make given limited requirements
* Technology and design choices
* Identify areas of your strengths
## The way this solution has been implemented.
Implementation: Admin have authorization to Add/remove/update/view employees

Add/update/view performance review

Assign employees to participate in another employee's performance review

Employee have authorization to List of performance reviews requiring feedback

Submit feedback

Technologies used: Frontend: React.js with Redux, react-bootstrap

Backend: Node.js with Express.js

Database: MongoDB

Other tools: babel, webpack

Future unit tests: mocha.js, chai.js, and enzyme.js

Live Memo (admin username: "admin" password: "password")

Quick test Clone this repo or download the .zip file, install dependencies, then npm run dev for server and npm start for client:

"performance_review_server"

    > cd performance_review_server
	> npm install
	> npm install -g nodemon
	> npm run dev
"performance_review_client" (2nd terminal)

    > cd performance_review_client
	> npm install
	> npm start
Database setup:

Option 1. Download MongoDB and run MongoDB server such as localhost:27017

Inside employee-performance-server/server/index.js, change mongoose.connect('mongodb://dbuser:dbpassword@hostname:port/dbname'); with your setting

Option 2: mLab sign up and get 500 MB free MongoDB

Inside employee-performance-server/server/index.js, change mongoose.connect('mongodb://dbuser:dbpassword@hostname:port/dbname'); with your setting

On browser, go to http://localhost:8080/

Now, we can't create admin through the browser as expected.

To create sample admin, download Postman or similar app for the browser.

In Postman, post http://localhost:8080/createAdmin => sample admin will be create

username: "admin" / password: "password"

User scenarios Scenario 1

Login as admin
Add 3 employees
Update 1 employee's profile
Delete 1 employee
refresh the page to make sure if the page is same as expected
Click "view details" of first employee
Click "Performance review" to create the employee's performance review
On the bottom of the performance review form, click Request Feedback' box to request feedback from other employees
On Feedback, click "X" to reject feedback from other employees
Fill some of the fields in the form and save it.
Close the form, and re-open to check if it saved correctly.
Scenario 2

Login as employee
Check if I have requiring feedback
Fill one of the feedback and save
check if it saved correctly
Submit one of the feedback (the feedback will move to submitted feedback section)
Check if I can change the submitted feedback (it will not be able to change)
Scenario 3

Pre-step: employees submitted their requiring feedbacks

Login as admin
Click "view details" to see the specific employee
Click "Performance Review" to see the review form
On the bottom, check if I can see the submitted feedback from other employees.
