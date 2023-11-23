# 1-Introduction

1. [Installing MongoDB in Linux](#schema1)
2. [Run MongoDB Community Edition](#schema2)
3. [Time to Get Started](#schema3)

2. [Ref](#schemaref)

<hr>

<a name="schema1"></a>

## 1. Installing MongoDB in Linux
- Import the public key used by the package management system
```
sudo apt-get install gnupg curl
```
To import the MongoDB public GPG key from 
https://pgp.mongodb.com/server-7.0.asc
, run the following command:
```
curl -fsSL https://pgp.mongodb.com/server-7.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \
   --dearmor
```
- Create a list file for MongoDB
```
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
```
- Reload local package database
```
sudo apt-get update
```

- Install the MongoDB packages
```
sudo apt-get install -y mongodb-org
```

<hr>

<a name="schema2"></a>


## 2. Run MongoDB Community Edition

- Start MongoDB
```
sudo systemctl start mongod
```
- Verify that MongoDB has started successfully
```
sudo systemctl status mongod
```
- You can optionally ensure that MongoDB will start following a system reboot by issuing the following command:
```
sudo systemctl enable mongod
```

- Stop MongoDB
```
sudo systemctl stop mongod
```
- Restart MongoDB
```
sudo systemctl restart mongod
```
- Begin using MongoDB
```
mongosh
```
- Exit MongoDb shell
```
exit
```

<hr>

<a name="schema3"></a>

## 3. Time to Get Started
- Show the DB
Muestra las base de datos que tenemos.
```
show dbs
```




<hr>

<a name="schemaref"></a>

## Ref

https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#std-label-install-mdb-community-ubuntu