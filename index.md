## **digits-semantic-ui**

<img src="doc/digits-landing.png" alt="landing">

Digits is a Meteor application that allows users to: 

  * Register an account.
  * Create and manage a set of contacts.
  * Add a set of timestamped notes regarding interactions with each contact.

## Installation

First, [install Meteor](https://www.meteor.com/install).

Second, download a copy of [Digits.](https://github.com/jhasun/digits.git) Note that Digits is a private repo and so you will need to request permission from the author to gain access to the repo.

Third, cd into the app directory install the required libraries with:

```
$ meteor npm install
```
Once the libraries are installed, you can run the application by invoking:
```
$ meteor npm run start
```
The first time running the application, the output may be similar to this:
```
 meteor npm run start

 > meteor-application-template-react@ start /Users/philipjohnson/github/philipmjohnson/digits/app
 > meteor --no-release-check --settings ../config/settings.development.json

 [[[[[ ~/github/philipmjohnson/digits/app ]]]]]

 => Started proxy.                             
 => Started MongoDB.                           
 I20180305-18:06:02.764(-10)? Creating the default user(s)
 I20180305-18:06:02.803(-10)?   Creating user admin@foo.com.
 I20180305-18:06:02.803(-10)?   Creating user john@foo.com.
 I20180305-18:06:02.804(-10)? Creating default contacts.
 I20180305-18:06:02.804(-10)?   Adding: Johnson (john@foo.com)
 I20180305-18:06:02.804(-10)?   Adding: Casanova (john@foo.com)
 I20180305-18:06:02.804(-10)?   Adding: Binsted (admin@foo.com)
 => Started your app.

 => App running at: http://localhost:3000/
 W20180305-18:06:02.805(-10)? (STDERR) Note: you are using a pure-JavaScript implementation of bcrypt.
 W20180305-18:06:02.805(-10)? (STDERR) While this implementation will work correctly, it is known to be
 W20180305-18:06:02.806(-10)? (STDERR) approximately three times slower than the native implementation.
 W20180305-18:06:02.806(-10)? (STDERR) In order to use the native implementation instead, run
 W20180305-18:06:02.806(-10)? (STDERR) 
 W20180305-18:06:02.806(-10)? (STDERR)   meteor npm install --save bcrypt
 W20180305-18:06:02.806(-10)? (STDERR) 
 W20180305-18:06:02.806(-10)? (STDERR) in the root directory of your application.
```
**Note regarding bcrypt warning.** You will also get the following message when you run this application:
```
Note: you are using a pure-JavaScript implementation of bcrypt.
While this implementation will work correctly, it is known to be
approximately three times slower than the native implementation.
In order to use the native implementation instead, run

  meteor npm install --save bcrypt

in the root directory of your application.
```
On some operating systems (particularly Windows), installing bcrypt is much more difficult than implied by the above message. Bcrypt is only used in Meteor for password checking, so the performance implications are negligible until your site has very high traffic. You can safely ignore this warning without any problems during initial stages of development.

If all goes well, the template application will appear at http://localhost:3000. You can login using the credentials in **settings.development.json**, or else register a new account.

Lastly, you can run ESLint over the code in the imports/ directory with:
```
$ meteor npm run lint
```
## User Interface Walkthrough

### Landing Page
When you first bring up the application, you will see the landing page that provides a brief introduction to the capabilities of Digits:

<img src="doc/digits-landing.png" alt="landing">

### Register an Account
If you do not yet have an account on the system, you can register by clicking on “Login”, then “Sign Up”:

<img src="doc/digits-register.png" alt="register">

### Sign In
Click on the Login link, then click on the Signin link to bring up the Sign In page which allows you to login:

<img src="doc/digits-login.png" alt="login">

### User Home Page
After successfully logging in, the system takes you to your home page. It is just like the landing page, but the NavBar contains links to list contact and add new contacts:

<img src="doc/digits-home.png" alt="home">

### List Contacts
Clicking on the List Contacts link brings up a page that lists all of the contacts associated with the logged in user:

<img src="doc/list-contact.png" alt="list-contact">

This page also allows the user to add timestamped “notes” detailing interactions they’ve had with the Contact. The user can also click the “Edit” link associated with any Contact to bring up a page that allows that Contact information to be edited.

### Add Contact
From the home page, the user can click on the Add Contact link in the Navbar to create a new contact with on the Add Contact page:

<img src="doc/add-contact.png" alt="add-contact">

### Admin
It is possible to designate one or more users as “Admins” through the settings file. When a user has the Admin role, they get access to a special NavBar link that retrieves a page listing all Contacts associated with all users:

<img src="doc/admin.png" alt="admin">
