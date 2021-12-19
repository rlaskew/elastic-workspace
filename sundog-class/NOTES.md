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

### auto complete and related
+ wget media.sundog-soft.com/es/sayt.txt

## import via script
+ wget http://files.grouplens.org/datasets/movielens/ml-latest-small.zip
+ wget media.sundog-soft.com/es7/MoviesToJson.py
+ curl -XPUT 127.0.0.1:9200/_bulk --data-binary @moremovies.json

## import via python library 
+ wget http://media.sundog-soft.com/es7/IndexRatings.py

## script exercise
+ wget http://media.sundog-soft.com/es7/IndexTags.py

## from https://askubuntu.com/questions/1327737/mysql-connector-java
+ sudo apt-add-repository universe
+ sudo apt-get update
+ sudo apt-get install libmysql-java

## logstash and mysql
+ wget  http://files.grouplens.org/datasets/movielens/ml-100k.zip

## CSV section
+ curl -O https://raw.githubusercontent.com/coralogix-resources/elk-course-samples/master/csv-schema-short-numerical.csv
+ sudo wget -P /etc/logstash/conf.d https://raw.githubusercontent.com/coralogix-resources/elk-course-samples/master/csv-read.conf
+ sudo wget -P /etc/logstash/conf.d https://raw.githubusercontent.com/coralogix-resources/elk-course-samples/master/csv-read-drop.conf
+ wget http://media.sundog-soft.com/es/sample-json.log
+ wget http://media.sundog-soft.com/es/sample-json-split.log
