## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?
**rails new projectname -T -d="postgres" --skip-spring --skip-turbolinks**

2. What do Models generally inherit from in rails? **ActiveRecord::Base**
3. What do Controllers generally inherit from in a rails project? **ApplicationController**
4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
**resources :horses, only: [:show]**
5. What rake task is useful when looking at routes, and what information does it give you? **Rake routes and it shows you all the available paths you have, their prefix in rails, their corresponding controller action and something else I'm not remembering without notes. *ETA: Was forgetting the verb***
6. What is an example of a route helper? When would you use them? **horses_path would be an example of an index route helper for horses. Generally, we use them in the controller for redirects, or I like to use them in testing to save a few keystrokes.**
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix? **I thought the difference was a `_url` path refers to an outside resource, while a path refers to uri that corresponds with a model and controller that you built. But Rails says the difference is that a _url path helper puts in the current host, port and path prefix.**
8. What are strong params and why are they necessary? **They are good for DRY and they are necessary bc it makes the params less interceptable with the private method.**
9. What role does `form_for` play in helping us create our forms? **`form_for` allows us to either create or update an object by giving us a form that is capable of accessing or creating a record in the database.**
10. How does `form_for` know where to submit the user's input? **We tell it where to put the input when we're defining the instance variable that the form accesses -- eg @horse = Horse.new. But it then knows where to post that information based on the RESTful design.**
11. Create a form using a `form_for` helper to create a new `Horse`.
```ruby
<%= form_for @horse do |f| %>
  <%= f.label :name %>
  <%= f.text_area :name %>
  <%= f.submit %>
  <% end %>
```
12. Why do we want to validate our models? **It can act as a check against bad data if one of your fields is misformatted, but also, we want all our records to be complete so as to get the best analysis possible.**

13. What are the steps of the DNS lookup? **1. The client browser checks to see if the URL's IP address is in the local cache. 2. If the answer is no, the browser hand the URL to the Resolving Name Server. 3. The RNS first checks the Root Name Server, which probably doesn't have, but does have an address for the com name servers. 4. The RNS goes to the com servers, which probably don't know the IP address, but do know the Authoritative Name Server's address. 5. The RNS goes to the ANS which likely has it, at which point the RNS can take that address to the browser.**


### Review Questions
14. How would you call the method `prance` from within the method `move` on a `Horse` instance?
```ruby
def move
  prance
end
```
15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?  
to return true
```ruby
furniture[:purchased]
```
to return 3
```ruby
furniture[:table][:height]
```
16. What is inheritance? **Inheritance is the concept that allows objects to have the same behavior as their parent object. It is indicated at the class level, e.g. class SuperMutt < Dog.**

### Self Assessment:
Choose One:

* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:

* I feel comfortable with the content presented this week
