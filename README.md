# 0x01. NoSQL

## Resources
### Read or watch:
* [NoSQL Databases Explained](https://riak.com/resources/nosql-databases/)
* [What is NoSQL ?](https://www.youtube.com/watch?v=qUV2j3XBRHc)
* [Building Your First Application: An Introduction to MongoDB](https://www.youtube.com/watch?v=ClAQEARNUoQ)
* [MongoDB Tutorial 2 : Insert, Update, Remove, Query](https://www.youtube.com/watch?v=CB9G5Dvv-EE)
* [Aggregation](https://docs.mongodb.com/manual/aggregation/)
* [Introduction to MongoDB and Python](https://realpython.com/introduction-to-mongodb-and-python/)
* [mongo Shell Methods](https://docs.mongodb.com/manual/reference/method/)
* [The mongo Shell](https://docs.mongodb.com/manual/mongo/)
* [Mongo Official installation guide](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)
* [Fixing /data/db not found error in MacOS X when starting MongoDB](https://bryantson.medium.com/fixing-data-db-not-found-error-in-macos-x-when-starting-mongodb-d7b82abb2479)
* [MongoDB data/db not found](https://stackoverflow.com/questions/37702957/mongodb-data-db-not-found)

## Learning Objectives
At the end of this project, you are expected to be able to [explain to anyone](https://fs.blog/2012/04/feynman-technique/), without the help of Google:
### General
* What NoSQL means
* What is difference between SQL and NoSQL
* What is ACID
* What is a document storage
* What are NoSQL types
* What are benefits of a NoSQL database
* How to query information from a NoSQL database
* How to insert/update/delete information from a NoSQL database
* How to use MongoDB

## Requirements
* A ```README.md``` file.

## More Info
### Install MongoDB 4.2 in Ubuntu 18.04

[Official installation guide](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/)

```bash
$ wget -qO - https://www.mongodb.org/static/pgp/server-4.2.asc | apt-key add -
$ echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.2 multiverse" > /etc/apt/sources.list.d/mongodb-org-4.2.list
$ sudo apt-get update
$ sudo apt-get install -y mongodb-org
...
$  sudo service mongod status
mongod start/running, process 3627
$ mongo --version
MongoDB shell version v4.2.8
git version: 43d25964249164d76d5e04dd6cf38f6111e21f5f
OpenSSL version: OpenSSL 1.1.1  11 Sep 2018
allocator: tcmalloc
modules: none
build environment:
    distmod: ubuntu1804
    distarch: x86_64
    target_arch: x86_64
$  
$ pip3 install pymongo
$ python3
>>> import pymongo
>>> pymongo.__version__
'3.10.1'
```
Potential issue if documents creation doesn’t work or this error: `Data directory /data/db not found., terminating` (`source` and `source`)
```bash
$ sudo mkdir -p /data/db
```
Or if `/etc/init.d/mongod` is missing, please find here an example of the file:

## Use “container-on-demand” to run MongoDB

* Ask for container` Ubuntu 18.04 - MongoDB`
* Connect via SSH
* Or via the WebTerminal
* In the container, you should start  MongoDB before playing with it:

```bash
$ service mongod start
* Starting database mongod                                              [ OK ]
$
$ cat 0-list_databases | mongo
MongoDB shell version v4.2.8
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("70f14b38-6d0b-48e1-a9a4-0534bcf15301") }
MongoDB server version: 4.2.8
admin   0.000GB
config  0.000GB
local   0.000GB
bye
$
```
## Tasks
* [x] 0. List all databases
Write a script that lists all databases in MongoDB.
* [x] 1. Create a database Write a script that creates or uses the database `my_db`:
* [x] 2. Insert document Write a script that inserts a document in the collection `school`:

    * The document must have one attribute `name` with value “Holberton school”
    * The database name will be passed as option of `mongo` command

* [x] 3. All documents 
Write a script that lists all documents in the collection `school`:

    * The database name will be passed as option of `mongo` command

* [x] 4. All matches
Write a script that lists all documents with `name="Holberton school"` in the collection `school`:

    * The database name will be passed as option of `mongo` command

* [x] 5. Count
* [x] 6. Update
* [x] 7. Delete by match
* [x] 8. List all documents in Python
* [x] 9. Insert a document in Python
* [x] 10. Change school topics
* [x] 11. Where can I learn Python?
* [x] 12. Log stats
* [x] 13. Regex filter
* [x] 14. Top students
* [ ] 15. Log stats - new version

## Software engineer
Chacha Alex Chacha  
:octocat: [GitHub](https://github.com/Chacha-A-Chacha/)
