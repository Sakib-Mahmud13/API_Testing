# API_Testing

## Table of contents


<!-- toc -->
- [Setup and installation](#install)
- [Make the Report]
- [POST Create Booking]
-[Body]
-[GET Get Booking info]
-[POST Create Token]
-[PUT Update Booking info]
-[DELETE DeleteBooking]
<!-- tocstop -->


## Install
After cloning the repo locally you can install it by opening a command prompt in the location to which you have cloned it and then calling the command below. Note that this requires you to have the npm package manger installed. If you don't have it, you can easily install it from [here](https://www.npmjs.com/get-npm)
First Postman install. Link This:
https://www.postman.com/downloads/
```bash
$ npm install
```

### Setup
Once you have it installed you can start the server for the challenge you are interested in by calling

```bash
  Set the environment 
$ node <server-name>
```

#### Routes

The find the secret challenge can be solved using the following routes:

```
POST    /Baseurl/Create Booking
GET    /Baseurl/Create Booking/<id>
POST    /Baseurl/auth
PUT    /Baseurl/New Update Booking/<id>
```

You may also need to use the following parameters:
### POST Create Booking
https://restful-booker.herokuapp.com/booking/
Body raw (json)
{
	"firstname" : "",
	"lastname" : "",
	"totalprice" : ,
	"depositpaid" : ,
	"bookingdates" : {
    	"checkin" : "",
    	"checkout" : ""
	},
	"additionalneeds" : ""
}

### GET Get Booking info
https://restful-booker.herokuapp.com/booking/id

### POST Create Token
Body raw (json)
{
	"username": "admin",
	"password": "password123"
}

### PUT Update Booking info
https://restful-booker.herokuapp.com/booking/id
Body raw (json)
{
	"firstname" : "",
	"lastname" : "",
	"totalprice" : ,
	"depositpaid" : ,
	"bookingdates" : {
    	"checkin" : "",
    	"checkout" : ""
	},
	"additionalneeds" : ""
}

### DELETE DeleteBooking
https://restful-booker.herokuapp.com/booking/id


##### Relationships

To include children resources, add `_booking`

```
POST    /Baseurl/Create Booking?_booking=api
GET    /Baseurl/Create Booking/<id>?_booking=api
```

To include parent resource, add `_update_booking`

```
POST    /Baseurl/auth?_update_booking=authentication
PUT     /Baseurl/New Update Booking/<id>?_update_booking=new booking details
```

### Find The 500 Errors
The challenge:

There are (at least) two 500 errors to be found in this little application. See if you can find them using only API calls.

#### Report
We are install the new man 
```
bash
Then command
newman run Batch20.postman_collection.json -e Batch20.postman_environment.json

first report:
newman run Batch20.postman_collection.json -e Batch20.postman_environment.json -r cli,html

2nd report
newman run Batch20.postman_collection.json -e Batch20.postman_environment.json -r cli,htmlextra
```

DELETE commands will also work, but you shouldn't need them to solve this challenge

NOTE that you can get the database for this into a bad state. If you feel like things are a mess and you can't proceed anymore you can reset the challenge and start over, by reseting the find_the_500_db.json file back to it's original state (use git to do this) and then restarting the server.

You may also need to use the following parameters:

