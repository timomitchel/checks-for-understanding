## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?

ActiveRecord is a framework that allows us to interact with our DB using ruby objects and methods that perform Raw SQL queries in a ruby environment
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? 
  Team.all
  Team.group()
  Team.join()
  Team.sum
  Team.maximum
  Team.minimum
  Team.order
If these methods aren't defined in the class, how do you have access to them?

  They are methods that are inherited from ActiveRecord
3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4?

  Team.find(4).name
 Assuming your class only included the code from question 2, how could you find the owner of the same team?
Something like: Team.joins(:owner) will give you access to the owner objects attributes

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?
Team.find(4).owner

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.
students belong to teachers and teachers have_many students
each student would have a foreign key associated with a teacher ID
6. Define foreign key, primary key, and schema.
foreign_key is a key that is placed as a column on the object that belongs to another object
Primary key is the key that is in the ID column(generally) of an object that has many of another object
schema is your db relationships matcher that shows attributes, foreign keys and primary keys
7. Describe the relationship between a foreign key on one table and a primary key on another table.
Primary key lives on the object that has many of another object and foreign key is that same key/id that is a column on the object that belongs to the object with the primary key
8. What are the parts of an HTTP response?
start line that describes the message, headers with attributes, body that is optional with data

### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
rake db:test:prepare prepares the test database
rake db:migrate runs a migration
3. What two columns does `t.timestamps null: false` create in our database?
created_at and updated_at
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
Teachers belong to a school and a school has many teachers
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
put a column for school_id on the teacher object
6. Give an example of when you might want to store information besides ids on a join table.

When you have dates that correlate between two objects
7. Describe and diagram the relationship between patients and doctors.
8. Describe and diagram the relationship between museums and original_paintings.
9. What could you see in your code that would make you think you might want to create a partial?
