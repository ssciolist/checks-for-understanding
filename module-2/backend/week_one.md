## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.

Get Post Delete Put Patch

2. What is Sinatra?

Sinatra is a lightweight Ruby framework for building web applications. 

4. What is MVC?

MVC stands for models, views, and controller and it is a model for our apps that delinates which files are responsible for which actions. So the models are ruby objects that represent a record in our database, views are the files that render our web page layout, and the controller directs requests from the server to either the model, the view, or some combination of all of them.


5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?

Because those conventions are actually methods in Sinatra. So when we write 
  ```ruby
  get '/merchants/new' do
    erb :'merchants/new'
  end
  ```
  ... we're actually calling a get method, which knows to look for our erb file in the views directory. 
  
6. What types of variables are accessible in our view templates without explicitly passing them?

I'm not sure if HTML elements count as variables in this context, but that's what I think you can access. That also means that CSS is accessible from the html link tag. 


7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view? @name = "Mr. Ed"
9. What's the purpose of ERB?

To have a file format that can dynamically create web pages. 


10. Why do I need a development AND test database?

You need a development and test database because you want to control your testing enviroment with values that you can see immediately. If you used just development database, testing a simple function like an average becomes kind of a black box because unless you calculate an average yourself for all 100+, 1,000+, 10,000+ records, you're just trusting that active record is doing its job. 

11. What is CRUD and why is it important?

CRUD is create, read, update, and delete and it's important because it provides a model for most of the actions that we would want to do in a database setting. 


12. What does HTTP stand for? Hypertext Transfer Protocol.
13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?

You can either interpolate Ruby as "<%= something %>" or <% something %>. The first way displays executed Ruby, the second way executes Ruby code, but does not display it on the page. 


14. What's an ORM?

ORM stands for Object Relational Mapping and it's a means to interact with our database using Ruby.


15. What's the most commonly used ORM in ruby (Sinatra & Rails)?

Active Record


16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
* get '/restaurants' to go to our homepage
* get '/restaurants/id' to see an individual restaurant
* get '/restaurants/new' to see the page on which we create a restaurant
* post '/restaurants' to create a new restaurant
* get '/restaurants/id/edit' to navigate to a page where we can change individual attributes of the restaurant
* put '/restaurants/id' to submit update details from the edit page
* delete '/restaurant/id' to delete a restaurant

17. What's a migration? 

A migration is a file that can be filled with instructions that determine the layout (schema) for your database tables. So far, we have used migrations to create tables, add table columns and drop table columns. 


18. When you create a migration, does it automatically modify your database?

No, not unless you run the migration. 

19. How does a model relate to a database?

A model is a Ruby object that represents a record of a database.


20. What is the difference between `#new` and `#create`?
Method .new will make a new instance of your active record model, but it will not save it. Whereas method .create will create a new instance and save it in your environment. 

### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  

CSV.foreach(films.csv) do |row|

⋅⋅⋅Film.new(row.to_hash)

end

22. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone'],
  brunch: {cost: $35, supplies: ['mimosa flutes'],
  antiquing: {cost: $200, supplies: ['list of antique stores'] 
}
```
How would I add 'granola bar' to things you should have when hiking?

activities[hiking][supplies].push("granola bar"]

23. What are the 4 Principles of OOP? Give a one sentence explanation of each.

###### Encapsulation

Encapsulation says we should limit direct access to our Ruby objects

###### Abstraction

Abstraction tells us to build classes so that one class doesn't need to know the details of another class in orde to use it. 

###### Inheritance

Inheritances is the idea that if a class shares core behaviors with another class, it's possible that we'd want that class to have access to those behaviors via inheritance.  

###### Polymorphism

It means one name many forms. It is further of two types - static and dynamic. Static polymorphism is achieved using method overloading and dynamic polymorphism using method overriding.


### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few
Used outside resources for 2,8,14,23


Choose One:
* I feel comfortable with the content presented this week

