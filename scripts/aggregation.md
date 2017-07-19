# Aggregation

### group

db.books.aggregate(
   { $group: { 0_id: "$editorial", editionSum: { $sum: "$edition" } } }
);

# count books by editorial
db.books.aggregate( 
   { $group: { _id: "$editorial", Total: { $sum: 1 } } } 
);

### match
db.books.aggregate(
[
   { $group: { 0_id: "$editorial", editionSum: { $sum: "$edition" } } },
   { $match: { editionSum: {$lt : 20000}} }
]
);



### References

#### Aggregation Zip Codes example

https://docs.mongodb.com/manual/tutorial/aggregation-zip-code-data-set/
