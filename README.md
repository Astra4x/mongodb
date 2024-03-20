# mongodb

This repository is documenting two queries using mongodb for a assingment for cs:3980.

The first query is to find all movies with runtime greater than 200 minuets made in the year 1983 sorted by runtime ascending as seen below.

![alt text](<query 1.png>)

using the following query:
db.movies.find({"year":1983, "runtime": { $gt: 200 }}, {_id:0, runtime:1, title:1, year:1}).sort({runtime:1})

The second query is find all movies made after 2014 with an IMDB rating above 9 as seen below. (to emmulate what is seen in the example image it must be sorted by rating decending)

![alt text](<query 2.png>)

using the following query:
db.movies.find({"year":{ $gt:2014 }, "imdb.rating": {$gt:9}}, {_id:0, title:1, year:1, imdb:{rating:1}}).sort({"imdb.rating":-1})
