## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?
rails new then specify certain setup preferences
2. What do Models generally inherit from in rails?
Active Record
3. What do Controllers generally inherit from in a rails project?
Application Controller/ ActionController::Base
4. How would I create a route if I wanted to see a specific horse in my routes title assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
resources :horse only: [#show]
5. What rake task is useful when looking at routes, and what information does it give you?
rails routes shows us all available routes path helpers and actions
6. What is an example of a route helper? When would you use them?
horse_path from example 4 which would require us to pass it a horse object attached to a specific id like so horse_path(@horse) that responds to horses/:id. I would use them in my view to direct a form to a specific page after it posted/
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix? 
_path retiurns the path associated with the method while _url returns the host and port as well as the path prefix
8. What are strong params and why are the necessary?
strong params are a private method that requires a certain type of object params and permit certain attributes to be passed in. They help us protect user input. 
9. What role does `form_for` play in helping us create our forms?
it tells us which object to create the form for and lets us create object forms that are nested under other objects if we specify first the top level object and then it's child object such as form_for [@store, @pet] do |f| etc
10. How does `form_for` know where to submit the user's input?
The path we give it in the create method in the controller with our render or redirect_to methods
11. Create a form using a `form_for` helper to create a new `Horse`. 
<%=form_for @horse do |f|%>
<%=f.label :name%>
<%=f.text_area :name%>
<%end%>



12. Why do we want to validate our models?
To make sure we have all the necessary info passed in before we save an entry into our DB. Sometimes users will forget to enter all of the necessary info.
