# DAMS
Dyno APIs Mobile Server

Before starting, Please configure the db. Currently the db is set to postgres.
You can configure the db to mysql or postgres. In order to configure, please navigate to src->main->resources->application.properties

Minimum Java JDK required is Java 1.8
After configuring, You can build a jar file and run it from the command line (it should work just as well with Java 11 or newer)
Use the below command to start the server on port 8080
```
./mvnw package
java -jar target/*.jar
```
Or you can run it from Maven directly using the Spring Boot Maven plugin. If you do this it will pick up changes that you make in the project immediately (changes to Java source files require a compile as well - most people use an IDE for this):

```
./mvnw spring-boot:run
```
To get the orders from the server, query the below endpoint

### GET: /<res_id>/orders?token=<access_token>
Sample Response

```
[
    {
        "order": {
            "aggregator": 1,
            "aggname": "Test",
            "orderno": "7646707645",
            "restaurantid": "12345",
            "token": "1000",
            "discount": "0",
            "packingcharges": "0"
        },
        "items": [
            {
                "item": "Item Name",
                "qty": 1,
                "amount": "73",
                "variant": "null",
                "positemcode": null,
                "aggitemcode": "677"
            }
        ],
        "createdAt": "2022-08-31T10:11:43.416+00:00",
        "updatedAt": null
    }
]
```
