# Golang Microservices

A **Microservices Architecture** consists of a collection of small, autonomous **services**. Each **service** is self-contained and should implement a single business capability. 

Below is an example of designing and implementing **Microservices** using:
* [**Gin Gonic**](https://github.com/gin-gonic/gin)
* [**Traefik**](https://github.com/containous/traefik)
* [**MongoDB**](https://www.mongodb.com/download-center)


***
### Movie Service Build & Run
####  Setup development environement
* Install Golang
* Install MongoDB

    <https://docs.mongodb.com/manual/installation>

* Start MongoDB
```sh
$ mongod --dbpath="[your_database_path]"
```
* Install neccessary Golang packages 
```sh
$ go get -u github.com/swaggo/swag/cmd/swag github.com/swaggo/gin-swagger github.com/swaggo/gin-swagger/swaggerFiles github.com/alecthomas/template github.com/gin-gonic/gin github.com/sirupsen/logrus gopkg.in/mgo.v2/bson github.com/natefinch/lumberjack
```


<em><strong>NOTE:</strong> You can change host and basePath of the service by editting the file <strong>./docs/docs.go</strong></em>

##### - Change configuration file
<em>Update values of file **./config/config.json**</em>
```sh
{
    "port": ":8808",
    "enableGinConsoleLog": true,
    "enableGinFileLog": false,

    "logFilename": "logs/server.log",
    "logMaxSize": 10,
    "logMaxBackups": 10,
    "logMaxAge": 30,

    "mgAddrs": "127.0.0.1:27017",
    "mgDbName": "go-microservices",
    "mgDbUsername": "",
    "mgDbPassword": "",

    "jwtSecretPassword": "raycad",
    "issuer": "seedotech"
}
```

##### -  Run services
* Run the <strong>Authentication</strong> service
```sh
$ cd [go-microservices]/src/user-microservice
$ go run main.go
>> [GIN-debug] Listening and serving HTTP on :8808
```
