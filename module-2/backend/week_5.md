1. How do we make flash messages display on a page?
  We do a flash.each block in the application.html.erb and we use flash[:success]/flash[:error] = "The text we want displayed"
2. Where is cart information/temporary information usually stored?


The cart information is usually stored in a session

3. What might be some reasons not to store cart in our database? Are there any reasons why we would want to persist that information?

The cart information needs the ability to change easily

4. What is the purpose of the asset pipeline?
Give us a place to store our assets so that rails can easily find them and speed up our application.

5. Why do we precompile our assets?
  This helps speed up our application and reduce page load time.
6. What do each of the following tags do?

```ruby 
<%= stylesheet_link_tag "application" %>
Links our Css file
<%= javascript_include_tag "application" %>
links our JS file
<%= image_tag "rails.png" %>
links an image in the images folder
```

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
Developers/employers are more likely to interact with a program that has a good readme. One wants the information of all team members easily acccessible.One wants to list dependencies. One wants clear instructions and details about what the program can do. One wants code snippets and examples.

8. What are the top four accessibility issues that we as developers should be aware of?

Visual, mobility, and Cognition are the top issues and we should have something like axe installed so that we can inspect what we miss.

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?

It's a helper-method/callback that tells our program to do something before the program does anything else. before_action is another. This could be found in our application controller

10. Given the following object, how would we create a scope for all users who are active?


```ruby 
User.create(name: "Happy", active: true)

scope :true, where(active: true)

11. What is the difference between a scope and a class method?

They are very similar. Scopes are faster and class methods are better for queries that involve a bit more complexity. Scopes always have a callable object as an argument.Internally Active Record converts a scope into a class method.
