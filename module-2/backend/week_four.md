## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. A cookie is a small piece of information stored by the client's browser used to by an application to identify a user and serve them relevant information based on their user id. 
2. A session is generally stored on the server and a cookie is generally stored on the client's browser. A session stores information about a series of requests and responses, whereas a cookie is something that is used to identify a specific user. 
3. A flash is a temporary message set by the previous user action, like a successful/unsuccessful creation action. You want to use flashes to indicate to a user that their behavior was successful or unsuccessful while allowing them to continue with their navigation of the website. 
4. People say that http is stateless because it doesn't store information from either the request or the response. Because of that, the second request doesn't know anything about the first one, and so each request and response exists as it is the first/last/only one. 
5. Authentication is when we check that someone has signed up to use our site and they've inputted their login information correctly. ETA: We're mainly checking to see that a user is who they say that they are.
6. Authorization is when we check that a user is permitted in a certain parts of the site, authentication is when we check if they are signed up to use the site. 
7. A before filter is something we use at the top of an Active Record model in order to perform another action before certain methods. It can be used to DRY up some parts of the create, update or destoy, or more recently, we have used it to authorize admins to see certain views. 
8. How do we keep track of a user once they’ve logged in? With a cookie. 
9. You want to namespace a resource when it's never going to be its own set of views -- for example, there's really not an Admin index. You want to nest a resource if it's a child of another resource. So comments only exist when there's an article, so nesting the resource comments inside of articles makes senses. The difference, other than why you use them, is how the urls appear: admin/articles vs article/1/comments.
10. At a high level, what tools can you use to implement authorization? How would you use them? To have authorization, you must have authentication, so bcrypt or a related gem is need to secure passwords. Then I'd need to have some before filters if I wanted users to see something that visitors could not, and to do that, I'd need to have sessions in place to see if a visitor is logged in. 
11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum? You declare an enum in the model and it's used to map a value to an integer in your database. To use an enum, you need to have a column of integers. The benefit of using an enum is that it takes less space to store the number in your database. 
12. Partials seem like the main one -- if you're repeating code, write it once in a partial, then render that partial. To a lesser extent, I guess you're using controller -- like if you're going to be referencing all companies, then you define a varible @companies, rather than write Company.all. 


### Reviews Questions 
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}
]
```  
given.sort_by do |holiday|
  holiday[:name]
 end
 
14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300? 

if given.include?("$")
 given.delete("$").to_i
else 
 given.to_i
end


### Self Assessment:
Choose One:

* I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources 

Choose One:

* I feel comfortable with the content presented this week

