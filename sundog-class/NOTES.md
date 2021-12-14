# Class notes

### Convert Json to single line
+ https://www.text-utils.com/json-formatter/

### Tips
+ add repo path to custom curl script to .bash_profile

### works of shakespeare
+ wget http://media.sundog-soft.com/es7/shakes-mapping.json
+ curl -H "Content-Type: application/json" -XPUT 127.0.0.1:9200/shakespeare --data-binary @shakes-mapping.json
+ wget http://media.sundog-soft.com/es7/shakespeare_7.0.json
+ curl -H "Content-Type: application/json" -XPOST '127.0.0.1:9200/shakespeare/_bulk' --data-binary @shakespeare_7.0.json

### movielens db
+ curl -XPUT 127.0.0.1:9200/movies -d '{"mappings": { "properties": { "year": { "type": "date" }}}}'
+ wget http://media.sundog-soft.com/es7/movies.json
+ curl -XPUT 127.0.0.1:9200/_bulk?pretty --data-binary @movies.json

### Nested data types
+ wget http://media.sundog-soft.com/es7/series.json
+ curl -XPUT 127.0.0.1:9200/_bulk?pretty --data-binary @series.json

### flattened and exceptions commands
+ wget media.sundog-soft.com/es/flattened.txt
+ wget media.sundog-soft.com/es/exceptions.txt

