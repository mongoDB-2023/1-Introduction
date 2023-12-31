# 1-Introduction

1. [Installing MongoDB in Linux](#schema1)
2. [Run MongoDB Community Edition](#schema2)
3. [Time to Get Started](#schema3)
4. [Shell vs Drivers](#schema4)
5. [Ref](#schemaref)

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
- Insert one element 
  - 1. use nombre_base_de_datos
    ```
    test> use basedegatos
    switched to db basedegatos
    ``` 
  - 2. insertOne({})
  ```
       db.basedegatos.insertOne({name: "Paco", age:2})
       {
         acknowledged: true,
         insertedId: ObjectId('655f3c51048dd06a35c960b7')
       }
    ```
- Find elements `find()`
```
db.basedegatos.find()
[ { _id: ObjectId('655f3c51048dd06a35c960b7'), name: 'Paco', age: 2 } ]
```
<hr>

<a name="schema4"></a>

## 4 . Shell vs Drivers
Los controladores (o drivers) de MongoDB para Python son bibliotecas que proporcionan una interfaz para que 
las aplicaciones escritas en Python se comuniquen con una base de datos MongoDB. Estos drivers facilitan la conexión, 
la consulta y la manipulación de datos en MongoDB desde Python.
- Python
https://www.mongodb.com/docs/drivers/python-drivers/

https://www.mongodb.com/docs/drivers/pymongo/

- **pymongo:** Es el controlador oficial de MongoDB para Python. Proporciona una interfaz de bajo nivel para 
interactuar con MongoDB y es muy utilizado en aplicaciones Python que se conectan a bases de datos MongoDB. 
Pymongo permite realizar operaciones como la inserción, actualización, eliminación y consulta de documentos 
en una base de datos MongoDB.



<hr>

<a name="schemaref"></a>

## Ref

https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/#std-label-install-mdb-community-ubuntu