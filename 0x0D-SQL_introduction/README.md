First, what are databases for?

Storing data in your application (in memory) has the obvious shortcoming that,
whatever the technology you’re using, your data dies when your server stops.
Some programming languages and/or frameworks take it even further by being stateless,
which, in the case of an HTTP server, means your data dies at the end of an HTTP request.
Whether the technology you’re using is stateless or stateful,
you will need to persist your data somewhere. That’s what databases are for.

Then, why not store your data in flat files,
as you did in the “Relational databases, done wrong” project?
A solid database is expected to be acid, which means it guarantees:

Atomicity:
transactions are atomic, which means if a transaction fails,
the result will be like it never happened.

Consistency:
you can define rules for your data, and expect that the data abides by the rules,
or else the transaction fails.

Isolation:
run two operations at the same time, and you can expect that the result is as though
they were ran one after the other.
That’s not the case with the JSON file storage you built:
if 2 insert operations are done at the same time,
the later one will fetch an outdated collection of users because the earlier one is not finished yet,
and therefore overwrite the file without the change that the earlier operation made,
totally ignoring that it ever happened.

Durability:
unplug your server at any time,
boot it back up, and it didn’t lose any data.
Also, a solid database will provide strong performance (because I/O is your bottleneck and databases are I/O, so their performance makes a whole lot more of a difference than the performance of your application’s code) and scalability (inserting one user in a collection of 5 users should take about the same time as inserting one user in a collection of 5 billion users).

ACID is a cool acronym!
CRUD is another cool one
You will definitely run into the concept of “CRUD” operations.
It’s just a fancy way to refer to the 4 operations that can be performed on the data itself:

Create some data;
Read some data;
Update some data;
Destroy some data.
Obviously, a database should allow all four. Yes, that’s it.

2+ kinds of databases
When people talk about databases,
they’re usually referring to relational databases (such as PostgreSQL, MySQL, Oracle, …);
but there are many other kinds of databases used in the industry,
which are globally referred to as “NoSQL” databases,
even though they can be very different from each other,
and serve very various purposes.
Also, the name “NoSQL” comes from SQL,
which is the name of the syntax used to give orders
(CRUD operations, creating and deleting tables, …) to a relational databases;
however, some non-relational databases,
which are referred to as “NoSQL” give the option to use the SQL syntax.
Therefore, the term “NoSQL” is quite controversial to refer to non-relational databases,
but it is still widely used.

“NoSQL” (non-relational) databases have known a boost in popularity,
over the last decade or so, so much that there was a point, a few years ago,
where people were wondering if they were to replace relational databases entirely.
But years later, the market has now solidified, NoSQL databases’
market share doesn’t progress much anymore and is now quite steady.
The result: many NoSQL databases have made it into solid maturity,
and are used in some very ambitious projects (as well as small ones),
but relational databases are still by far the most used in projects,
and are not going anywhere after all.

Therefore: it is crucial for a software engineer to know very well how relational databases work,
because the odds are very strong that you will encounter them in your career;
but it is also very important to get acquainted with the most popular types of NoSQL databases,
because the odds that you run into them, however kinda smaller, are pretty strong too.

SQL
In order to work with relational databases,
you will need to get familiar with SQL syntax.
A lot of developers will acknowledge that they find the SQL syntax unpleasantly hard to use,
which has some outcomes:

Engineers that are comfortable with SQL are very respected in the industry,
even more so in this age where data has gotten so valuable.
To be honest, the fact that I aced the SQL challenge on my Apple interview
is probably a huge reason for me to have gotten the job;
it turns out the initial role was a lot about manipulating data.
The fear of SQL explains a lot why non-relational databases got called “NoSQL”,
a bit like if it was a statement, a complain.
Non-relational databases push a lot the button of not having to use SQL.
