## Week Two - Module 2 Recap

Fork or re-pull this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.


### Week 2 Questions

**At a high level, what is ActiveRecord? What does it do/allow you to do?**

ActiveRecord is an ORM that allows you to do SQL operations on a Ruby object that models a record in your database.


**Assume you have the following model:**

```ruby
class Team << ActiveRecord::Base
end
```

**What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?**

.find, .all and .sum are two methods that you have access to. These are ActiveRecord methods that you have access to because Team is inheriting from the ActiveRecord base.

**Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?**

a) Team.find(4)

b) Team.find_by(:owner_id = 4)

**Assume that you added a line to your `Team` class as follows:**

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

**Now how would you find the owner of the team with an id of 4?**

Team.find(4).owner

**In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.**

Teacher has many students

| ID | Name        |  
| -- |-------------|
| 1  | Ms. Brown   |
| 2  | Mr. Baker   |
| 3  | Mr. Smith   |

Student belongs to a teacher

| ID | Name     | Teacher_id |
| -- |----------|------------|
| 1  | Lala     | 1          |
| 2  | Margaret | 1          |
| 3  | Wilson   | 3          |

**Define foreign key, primary key, and schema.**

A foreign key is a field on a table that references the id of a record on another table in order to access information on the second table vis a vi a SQL query.

A primary key is a unique identifier, often a number, for a single record in a table.

The schema is a blueprint of your entire database that defines all tables and their fields, including indexed fields and foreign keys.  

**Describe the relationship between a foreign key on one table and a primary key on another table.**

Essentially, the foreign key on one table is the primary key of another table. In the team example, the teams table would have a foreign key of owner_id, and the owner table has a primary key of owner. But both keys point to the same owner record.

**What are the parts of an HTTP response?**

The head and the body, where the head contains key value pairs that format the response. And then the body, which actually contains all the HTML-formatted information that the user wants.


### Optional Questions

**Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.**

* .select > allows you to say what information you want back from your query. One of my favs bc that's where the computation happens
* .group > allows you to organize the info from your query. One of my favs bc I forget it, then putting it in saves the day
* .join > allows you to query two (or more?) tables at once. One of my favs bc it is v. powerful.

**Name your three favorite ActiveRecord rake tasks and describe what they do.**

* rake db:setup > combines create, migrate and seed
* rake db:test:prepare > creates test enviroment that reflects production enviroment


**What two columns does `t.timestamps null: false` create in our database?**

created_at and updated_at

**In a database that's holding schools and teachers, what will be the relationship between schools and teachers?**

A school will have many teachers, and a teacher will belong to a school.

5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?

6. Give an example of when you might want to store information besides ids on a join table.
7. Describe and diagram the relationship between patients and doctors.
8. Describe and diagram the relationship between museums and original_paintings.
9. What could you see in your code that would make you think you might want to create a partial?

### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources

(I'm not sure that every answer is perfectly correct, but I think it's at least quite close.)

Choose One:

* I feel comfortable with the content presented this week
