# loopstock frontend developer challenge

This is a challenge for the frontend developers applying to work at [loopstock.io](http://www.loopstock.io).

For the general information about the challenges please check the [README.md](../README.md).


## Dashboard

The system you need to implement consists of the following components:

* An index.html containing the layout
* A react app with:
    * Login
    * Dashboard / Admin View with 1 route
    * A `/listings` page with two tabs


### Login / Authentification

* Write a React Redux based app that authenticates via firebase authentication
* When not logged in display a login
* When authenticated display a dashboard / admin page with a sidebar containing a link to `/listings`


### Dashboard / Admin View

* add some nice looking graphs / charts to the Admin view
    * the graphs can be based on random data or any other data source you have access to
    * don't spend to much time thinking about what to display here, we just wan't to see some nice looking graphs

Use any plotting library of your choice. If you don't know any feel free to use [recharts](http://recharts.org/#/en-US/)

### Listings Page

The `/listings` page should display two tabs

* A photos tab, the data for this must be fetched from `https://jsonplaceholder.typicode.com/photos`.
    * The tab must have pagination, autocomplete / search functionality, filter by odd / even id.

* A users tab, the data for this must be fetched from  `https://jsonplaceholder.typicode.com/users`.
    * Add expandable row functionality, in the expanded row display a google map with the data contained in the users.address.geo field


### Bonus points

* Add Internalisation to this app, so english and a language of your choice 
    * Add a button that allows a user to switch between languages


### Hints

* You are free to use any css framework out there (bootstrap/material design/semantic ui)
* You can also use create-react-app to speed things up
