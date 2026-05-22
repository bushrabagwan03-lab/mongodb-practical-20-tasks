# MongoDB Practical Tasks (1–20)

## Project Overview

This project demonstrates practical MongoDB operations using MongoDB Community Server and Mongosh on Windows.

The project includes beginner to advanced MongoDB concepts such as CRUD operations, indexing, aggregation, replica sets, sharding, validation, backup, and cluster-related operations.



## Technologies Used

* MongoDB 8.2.4
* Mongosh 2.6.0
* Windows PowerShell
* MongoDB Database Tools



## Topics Covered

### Basic Operations

* Database creation
* Collection creation
* Insert operations
* Update operations
* Delete operations

### Querying & Performance

* Filtering
* Sorting
* Indexing
* Aggregation
* Lookup (Join)

### Advanced MongoDB

* Validation
* Replica Set
* Sharding
* Backup and Restore
* Cluster Commands



## Replica Set

A replica set was configured using a separate MongoDB instance running on port 27018.

Commands used:

bash
mongod --replSet rs0 --port 27018 --dbpath "C:\data\db2"
mongosh --port 27018
rs.initiate()


## Sharding

Sharding setup included:

* Config Server
* Mongos Router
* Shard Server
* Multiple PowerShell terminals

Commands used:

bash
mongod --configsvr --replSet configReplSet --port 27019 --dbpath "C:\configdb"

mongosh --port 27019
rs.initiate()

mongos --configdb configReplSet/localhost:27019 --port 27020

mongosh --port 27020
sh.addShard("rs0/localhost:27018")


## Backup

MongoDB Database Tools were used for backup:

bash
.\mongodump.exe --db studentDB --out C:\Users\HP\backup


## Author

Bushra

