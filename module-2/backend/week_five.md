### Week 5 Questions

Re-pull from this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

### Week 5 Questions
1. 
flash[:success] = "Success message"
flash[:whatever] = "Whatever message"

2. Cart and temporary information is usually stored in the session. 


3. One reason not to store a cart in our DB is that we're hoping with our successful whatever business, there will be lots and lots of carts, so storing them in the DB requires lots of room. Also sometimes carts don't resolve into orders, which means that information may be temporary. 

4. The purpose of the asset pipeline is to allow webpages to render really quickly by delivering all  of the application's css and jv as possible in minified application files.

5. I think part of the reason is so we can compact them, but another reason is that so that we can give them a fingerprint. Then the browser can hold onto the fingerprint and send it any follow up requests; if the server sees that the fingerprint is out of date, it'll send new precompiled css/jv back to the client

6. What do each of the following tags do? They are all for precompiling assets in our application.html.erb file. 
 
```ruby 
<%= stylesheet_link_tag "application" %> 
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```

7. Great Read Mes include code snippets, setup instructions and troubleshooting. Taking the time to update a readme for our project means that other people are more likely to actually use our product and also that maybe we'll better understand our project if we return to it. 

8. What are the top four accessibility issues that we as developers should be aware of? Color blindness, blindness, print size and ???. I reviewed this week's materials and didn't find where we learned about this, so this is a guess. 

9. `before_save` is an example of a callback method, so we would find it in our controller. 

10. Given the following object, how would we create a scope for all users who are active?

```ruby 
User.create(name: "Happy", active: true)
```

11. What is the difference between a scope and a class method? A scope is something that essentially replaces an ActiveRecord where statement and it's defined at the top of the model with syntax like "scope :red, -> { where(color: 'red') }". The class method can be more complicated, incorporating a where, but also select and more methods. Scopes are smarter and can return blank AR relations instead of nil if your query doesn't have any relations. 


### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?  cart[:48] = 4 
  12b. How would you increase the quantity of item 29?  cart[:29] += 1
  12c. How would you find out how many items your user is thinking about purchasing? cart.values.sum
  
13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?  Polymorphism is the concept that allows variables/parameters to become any type of object we assign them to. This relates to the idea of duck-typing because it means I can create duck = Duck.new and then duck becomes a Duck class object. Putting information into our models is one way we use this in Ruby: so our Cart class recieves information from a hash, but by creating a cart, we can use some cart-specific methods for that information. We also retrieve information from our post requests to create and edit model objects. 
14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  given.scan(/\d{3,}/).join(".") < *looked this up and it took me a while to get there.


### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week

