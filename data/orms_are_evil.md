# [O]bject [R]elational [M]apping  is evil

## What
- Root of all evil for me is a ORM called Hibernate
- but there are many many more [List](https://en.wikipedia.org/wiki/List_of_object%E2%80%93relational_mapping_software)
- They all have in common, that they add another abstraction to the database layer


## Exception
- We do not speak from very little projects with three database tables
- Small database schemas are really an exception and maybe the only location where ORMs have its place
- But only if you have very few tables, very few record counts and trivial conditions (filters)

  
## Why (Long)
- For relational databases there is SQL to do queries on the data
- SQL is very powerful for specific filters/queries and you really need to tune it if you want max performance
- As you already can see  

## Why (Short)
- SQL is very powerful and can do lots of complex filtering
- Complex data structures cannot sufficiently modeled by ORMs
- ORMs are another un-neccessary layer of abstraction
- You end very fast on a dead-end if you have a slightly complicated query
- Optimizations cannot be done in an ORM and that is the really big problem of ORMs
- You can only do very simple things aka (select * from table ... maybe with one or two columns as filter) but when you have to join several tables and do aggregations, window functions and stuff, its over 

## Solution
- You really need to stay on plain SQL
- There are some relly interesting solutions, like using only SQL functions, so you can have all SQL logic at the right place (not in your code)
- You can use some lightweight SQL verification framework
- You can even put your SQL statements in external files
- Do everything but not use an ORM if you have a medium/big project
- Small projects can be done with ORMs where no performace issues arise and nothing complex
- If you use an ORM you need to always ensure, that there is a way around for your special queries (here it becomes ugly)
