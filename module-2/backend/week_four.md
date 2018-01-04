## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

* What is a cookie?
A cookie is some small piece of data stored on the client side/browser
* What’s the difference between a session and a cookie?
Sessions are more secure than cookies. They are stored on the server while the cookie is stored on the browser. A session is associated with a user
* What’s a flash and when do you want to use flashes?
A flash is a special message that pops up when a user does something to let them know if they were successful or if they encountered an error or if they should be aware of something moving forward. It's good to use them when they fill out some sort of form.
* Why do people say “HTTP is stateless”?
Every time a request is sent everything is reset. So HTTP does not hold onto state such as which user is using the application. We have to build that in our sessions. 
* What’s authentication? Explain.
Authentication is the process of validating that a user exists in the database and has entered the right credentials in the login form. 
* What’s the difference between authentication and authorization?
Authentication means you are who you say you are and authorization means you have the right credentials to access a certain part of the site
* What’s a before filter?
It's a way to run a check method on your controller to make sure something is valid before proceeding. 
* How do we keep track of a user once they’ve logged in?
We keep track of the user via the session_helper methods and by defining a current_user method in the application controller to validate authorization as our user navigates our page
* When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
Namespacing a resource is a good approache when we have different types of users that are accessing pages and controllers that have the same name, but have different features depending on the type of user. Nesting resources is a way to express database/model relationships within your paths/routes.
* At a high level, what tools can you use to implement authorization? How would you use them?
Namespacing is a good tool to use to implement and using a role in your user model will also help you keep your code DRY and give different levels of access to certain users. 
* What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
An enum is a way to define a role for your user. You declare it in the user model. It needs to be an integer in your database. They allows us to call things by name even though we stored them as integers in the database. 
* What are some strategies you can use to keep your views DRY?
You can utilize application.html.erb to implement things like nav bars and flash messages once, but they will appear across every page of your application. You can also use the same class names for certain html types images/headers/etc that you want styled the same way. 
