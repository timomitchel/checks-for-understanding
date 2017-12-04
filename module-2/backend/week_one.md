## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

1. List the five common HTTP verbs and what the purpose is of each verb.
  GET > Retrieve information from specified URL Route
  PUT > Allow an update to a specific entity within the params/id
  POST > Add an entry/form from the user
  DELETE > Delete a specific entity within the params/id
  PATCH > Make partial changes to a specific entity
2. What is Sinatra?
An ORM that sits between our model and DB and is inherited by our app within our controller
4. What is MVC?
Model View Controller. Industry standard model for creating web applications. Model holds logic. View holds webpage skeleton and styling ie: HTML/CSS. Controller holds routes ie: ORM/framework inheritance and HTTP requests/paths
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
So that our code is clear to other developers looking at our application and so that the web is not a bunch of chaos with anyone choosing unique interactions/routes.
6. What types of variables are accessible in our view templates without explicitly passing them?
Any instance variables or local variables defined within our controllers do blocks
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  Call @count within a <%= %> or <% %> in our ERB file
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
  Same as @ count within the do block but defined name = "Mr. Ed"
9. What's the purpose of ERB?
  To allow for ruby logic within an html-like skeleton layout
10. Why do I need a development AND test database?
  You need one that will be displayed and updated with user input/interaction and one to test pre-defined DB's that will not change so that we can ensure accurate tests
11. What is CRUD and why is it important?
  Create, Read, Update, Delete - It's how our DB interacts with our web application
12. What does HTTP stand for? 
Hypertext Transfer Protocol
13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
  "#{}" that allows for us to pass in ruby variables/methods within a string. Also the two lobster claws. <%= %> outputs to our screen while <% %> allows for logic without output. 
14. What's an ORM?
Object Relational Mapper
15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
Rails
16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
GET '/restaurants' > Allows us to view all restauraunts
GET '/restaurants/:id' Allows us to grab a specific restauraunt entry by its DB ID
GET '/restaurants/new' Allows us to add a restauraunt entry to Our DB
POST '/restaurants' Allows user to add a restauraunt entry to our DB
GET '/restaurants/:id/edit' Allows user to edit info on specific restauraunt entry by its DB ID
PUT '/restaurants/:id allows user to actually submit the with updated info to the DB by ID
DELETE '/restaurants/:id' allows user to delete specific entry in DB by ID
17. What's a migration? 
A migration is how we run our seeds and create our Databases with any data such as CSV's and or pre-defined Instances of a class.
18. When you create a migration, does it automatically modify your database?
It depends. You can use rake db:reset to clear the databases and then seed them from scratch. But if you migrate twice it will add to your existing DB
19. How does a model relate to a database?
It turns your DB data/seeds into ruby objects and provides the instance variables classes and methods to manipulate your db data.
20. What is the difference between `#new` and `#create`?
  new is a class method that creates a new instance of the class while create creates a new entry in our database and is an AR method. 
Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  
csv = Csv.open(filename, headers: true).readlines
  csv.each do |row|
  Films.Create(
    id: row[:id],
    title: row[:title],
    description: row[:description]
  )
  end
22. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']} 
}
```
How would I add 'granola bar' to things you should have when hiking?
activities[:hiking][:supplies] << 'granola bar'
23. What are the 4 Principles of OOP? Give a one sentence explanation of each.
Abstraction - Putting complex functionality into easily readable method verbs
Encapsulation - keeping things in classes/methods to keep objects from knowing about one another unless theya absolutely need to so that your code is easier to change in the future.
Inheritance - Every class inherits from another class and has certain behavior/state depending on its class
Polymorphism - Some objects can be represented/manipulated in similar ways to different objects ie: bracket notation

