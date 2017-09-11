# loopstock backend developer challenge

This is a challenge for the backend developers applying to work at [loopstock.io](http://www.loopstock.io).

For the general information about the challenges please check the [README.md](../README.md).


## Average integer calculator

The system you need to implement consists of the following components:

- Two instances of random integer generator
- A message broker
- Integer average calculator
- A SQL Database
- A basic API

All the components should be run with docker. The details of what each of the components should do are below.

You need to do the following:

- Write the simple random integer generator
- Write the integer average calculator
- Write the API that stores avarages in a SQL database and serves them to an http endpoint
- Write configuration and/or explain how to run it locally
- Describe how you would provision a set of linux machines and how'd you orchestrate, monitor and troubleshoot these services.


### Random integer generators

You need to write and run two instances of the following simple service:

- every 100ms generates a random integer between 1 and 10000
- the value gets pushed through the message broker of your choice


### Message broker

The services are communicating through a message broker. You can use any protocol and broker you like. The simpler the better.
If you don’t have any preferences we suggest to use MQTT protocol. You can run MQTT broker using the toke/mosquitto image:

```
docker run -it -p 1883:1883 --name=mosquitto  toke/mosquitto
```


### Integer average calculator

The avarageing service you need to write and run:

- subscribes to the topic where generators publish the values
- computes the average integer for the last 5 seconds


### API

- Stores the 5s avarages in the database with timestamp
- exposes an http endpoint where the last 5s avarages could be obtained from the database via GET request


### SQL Database

You can use any SQL database you like. If you don't have any favorites use PostgreSQL.

- Stores the 5s avarages with timestamps via the API
- Serves simple API requests for the last 5s avarage


### Hints

At the end it should roughly look like this:

![Image of services](/backend-devs/backend-challenge.png)

- You're free to use any languages and any libraries.

- The fastest way to get mqtt broker is to run mosquitto with docker:
    ```
    docker run -it -p 1883:1883 --name=mosquitto  toke/mosquitto
    ```

### Bonus points

* have both random integer generators coordinate with each other so that you never get the same random number from both of them at the same time
