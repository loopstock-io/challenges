# loopstock devop engineer challenge

This is a challenge for the devop engineers applying to work at [loopstock.io](http://www.loopstock.io).

For the general information about the challenges please check the [README.md](../README.md).


## summary of tasks

You need to do the following:

* Design and explain a microservices architecture for inventory management
* Map out the datamodel and explain how to set up the databases
* Come up with a deployment, automated testing and CI strategy
* Talk about scaling it up, logging and monitoring
* Build a little service in python or golang


### Microservices

As you may know loopstock automates inventory management in hospitals. This includes for example automated stocktakes of the consumables in every room, automated and manual requests for restocking of specific items, the ordering and delivery process, tracking of consumables throughout the hospital and demand prediction functionality amongst other things. 

We'd like you to take a moment and think about exactly what functionality is needed in order to automate all inventory related tasks in hospitals. Now think about how you would devide these functions in a microservice architecture. 

* Give each service a name, list input and output data of the service, briefly explain what is does and what other services it communicates with.

For example:

```
{
  "name": "restock service",
  "input": ["storage room id", "items in storage room", "minimum required quantity of each item"],
  "output": ["trigger order for specific items", "none"],
  "functions": ["Service compares desired item quantity in a room with actual item count.", "Where item count is smaller than minimum quantity, trigger an order for the item."],
  "comms": ["ordering service", "rfid reader service"]
}
```


### Datamodel and database structure

* Map out the datamodel for your inventory management application. (No need to get fancy here, you can use pen and paper if you like.) 
* Explain how you would set up your databases and how that would play along with the service architecture you set up.


### Deployment strategy

Please take a minute and get familiar with Google Cloud Services, if you are not already. 

* Would you deploy your application to App Engine, Container Engine or Compute Engine? What are the benifits and caveats of your solution? 
* How do you orchestrate your app within this environment?
* What tools would you use for automated testing and continuous integration?
* What are things to consider for development of the app? 


### Building for scale

* How do you separate deployments for different hospitals?
* Which of your microservices will need automated scaling or loadbalencing and what tools are you using to accomplish this?
* What parts of the system would you monitor, what tools would you be using and what is it that you are hoping to catch?
* How do you go about logging?


### Building a simple service in python or golang

Static read in a storage room with filtering items that are still there...

TODO!
