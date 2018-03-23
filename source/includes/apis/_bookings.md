<!-- Bookings -->
# Bookings
## Get All Bookings

> returns JSON structured like this:

```json
[
    {
        "id": 1,
        "number": 1,
        "contact_person_id": 1,
        "itinerary_id": 1,
        "total_price": 100,
        "created_at": "2018-02-20T03:31:27.274Z",
        "updated_at": "2018-02-20T03:31:27.274Z"
    },
    {
        "id": 2,
        "number": null,
        "contact_person_id": 2,
        "itinerary_id": 7,
        "total_price": 24733600,
        "created_at": "2018-02-20T04:50:37.298Z",
        "updated_at": "2018-02-20T04:50:37.298Z"
    }
 ]
 ```

This endpoint retrieves all bookings.

### HTTP Request

`GET http://35.224.189.34:3000/api/v1/bookings`

## Get a Specific Booking

> returns JSON structured like this:

```json
{
    "id": 1,
    "number": 1,
    "contact_person_id": 1,
    "itinerary_id": 1,
    "total_price": 100,
    "created_at": "2018-03-01T07:04:27.620Z",
    "updated_at": "2018-03-01T07:04:27.620Z",
    "contact_person": {
        "id": 1,
        "name": "Octavianus Marcel Harjono",
        "username": "omarcelh",
        "email": "octavianusmarcel12@gmail.com",
        "phone": "087836901995",
        "api_token": null,
        "created_at": "2018-03-01T07:04:27.558Z",
        "updated_at": "2018-03-01T07:04:27.558Z",
        "password_digest": "$2a$10$qapYKzJox49ftG4HbXskje76.3hx7d9oCbTv3YCYzYGhNnK6j8CGS",
        "remember_digest": null,
        "reset_digest": null,
        "reset_sent_at": null,
        "birth_date": "1995-10-07T00:00:00.000Z"
    },
    "itinerary": {
        "id": 1,
        "currency_code": "IDR",
        "price_rule_id": 1,
        "created_at": "2018-03-01T07:04:27.390Z",
        "updated_at": "2018-03-01T07:04:27.390Z"
    },
    "statuses": [
        {
            "id": 5,
            "tag": "pay-timeout",
            "name": "Payment timed-out",
            "description": "Initial state: customer hasn’t completed payment but runs out of time\nAction (WL-booking): cancel user’s booking (because payment time limit from airline might be longer)",
            "created_at": "2018-02-19T09:00:00.000Z",
            "updated_at": "2018-02-19T09:00:00.000Z"
        },
        {
            "id": 4,
            "tag": "eticket-issued",
            "name": "E-ticket issued",
            "description": "Init: e-ticket is received from airline and sent to customer via e-mail and app",
            "created_at": "2018-02-18T09:00:00.000Z",
            "updated_at": "2018-02-18T09:00:00.000Z"
        },
        {
            "id": 3,
            "tag": "pay-validated",
            "name": "Payment validated",
            "description": "Init: Payment validated either automatically or manually\nAction: System confirms payment to airline",
            "created_at": "2018-02-17T09:00:00.000Z",
            "updated_at": "2018-02-17T09:00:00.000Z"
        },
        {
            "id": 2,
            "tag": "val-payment",
            "name": "Validating payment",
            "description": "Init: User confirms that they have completed payment (and uploaded PoP)\nInit: Payment is not yet validated manually or automatically",
            "created_at": "2018-02-16T09:00:00.000Z",
            "updated_at": "2018-02-16T09:00:00.000Z"
        },
        {
            "id": 1,
            "tag": "wait-payment",
            "name": "Waiting for payment",
            "description": "Init (normal booking): User books flights\nInit (WL-booking): After user confirms to pay, add 7 more minutes to the countdown ",
            "created_at": "2018-02-15T09:00:00.000Z",
            "updated_at": "2018-02-15T09:00:00.000Z"
        }
    ],
    "passengers": [
        {
            "id": 1,
            "user_id": 1,
            "category": "Adult",
            "name": "Octavianus Marcel Harjono",
            "title": "Mr.",
            "birth_date": null,
            "is_hidden": false
        },
        {
            "id": 2,
            "user_id": 1,
            "category": "Adult",
            "name": "Fauzan",
            "title": "Mr.",
            "birth_date": null,
            "is_hidden": false
        },
        {
            "id": 3,
            "user_id": 1,
            "category": "Infant",
            "name": "Fiqie",
            "title": null,
            "birth_date": null,
            "is_hidden": false
        },
        {
            "id": 4,
            "user_id": 1,
            "category": "Adult",
            "name": "Afi",
            "title": "Ms.",
            "birth_date": null,
            "is_hidden": false
        },
        {
            "id": 5,
            "user_id": 1,
            "category": "Child",
            "name": "Wahid",
            "title": null,
            "birth_date": null,
            "is_hidden": false
        }
    ]
}
```

This endpoint retrieves a specific booking.

<aside class="notice">This includes the relations: user (contact person), itinerary, [booking] statuses [type], and passengers.</aside>

### HTTP Request

`GET http://35.224.189.34:3000/bookings/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the booking to retrieve

## Delete a Specific Booking

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "message": "Booking is deleted"
}
```

This endpoint deletes a specific booking.

### HTTP Request

`DELETE http://35.224.189.34:3000/bookings/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the booking to delete

## Create a Booking

```json
{
  "request": {
    "endpoint": "http:\/\/omarcelh.me:3000\/api\/v1\/booking",
    "method": "POST",
    "token": "69i57j0l2j69i60l32022j0j4"
  },
  "properties": {
    "itinerary": {
      "outbound": [
        {
          "id": null,
          "availability": 9,
          "seat_class": "ECONOMY",
          "departure_airport": {
            "airport": "LHR",
            "terminal": "2",
            "airport_name": "Heathrow"
          },
          "arrival_airport": {
            "airport": "WAW",
            "airport_name": "Frederic Chopin"
          },
          "departure_date": "2018-02-25T10:25",
          "arrival_date": "2018-02-25T13:55",
          "airline": "Lot - Polish",
          "airline_logo": "https:\/\/www.gstatic.com\/flights\/airline_logos\/70px\/LO.png",
          "aircraft": "7M8"
        },
        {
          "id": null,
          "availability": 9,
          "seat_class": "ECONOMY",
          "departure_airport": {
            "airport": "WAW",
            "airport_name": "Frederic Chopin"
          },
          "arrival_airport": {
            "airport": "EWR",
            "terminal": "B",
            "airport_name": "Newark Liberty International"
          },
          "departure_date": "2018-02-25T17:20",
          "arrival_date": "2018-02-25T20:55",
          "airline": "Lot - Polish",
          "airline_logo": "https:\/\/www.gstatic.com\/flights\/airline_logos\/70px\/LO.png",
          "aircraft": "788"
        }
      ],
      "inbound": [
        
      ]
    }
  },
  "price": {
    "currency": "IDR",
    "total_price": "24733600.00",
    "fare": {
      "price_per_adult": {
        "total_fare": "8629400.00",
        "tax": "569400.00"
      },
      "price_per_child": {
        "total_fare": "6614400.00",
        "tax": "569400.00"
      },
      "price_per_infant": {
        "total_fare": "860400.00",
        "tax": "54400.00"
      }
    }
  },
  "passenger": {
    "adults": 2,
    "children": 1,
    "infants": 1,
    "informations": [
      {
        "category": "Adult",
        "name": "Octavianus Marcel Harjono",
        "title": "Mr.",
        "birth_date": "1995-01-01"
      },
      {
        "category": "Adult",
        "name": "Fauzan Rifqy",
        "title": "Mr.",
        "birth_date": "1994-01-01"
      },
      {
        "category": "Adult",
        "name": "Older Brother",
        "title": "Mr.",
        "birth_date": "2012-01-01"
      },
      {
        "category": "Adult",
        "name": "Little Brother",
        "title": "Mr.",
        "birth_date": "2016-01-01"
      }
    ]
  },
  "user": {
    "name": "Fauzan Rifqy",
    "username": "fauzanrifqy",
    "email": "fauzanrifqy@mail.com",
    "phone": "08123456789"
  }
}
```

> The above request returns JSON structured like this:

```json
{
    "id": 2,
    "number": null,
    "contact_person_id": 2,
    "itinerary_id": 2,
    "total_price": 24733600,
    "created_at": "2018-02-20T06:11:32.797Z",
    "updated_at": "2018-02-20T06:11:32.797Z",
    "contact_person": {
        "id": 2,
        "name": "Fauzan Rifqy",
        "username": "fauzanrifqy",
        "email": "fauzanrifqy@mail.com",
        "phone": "08123456789",
        "api_token": null,
        "created_at": "2018-02-20T06:11:32.560Z",
        "updated_at": "2018-02-20T06:11:32.560Z",
        "password_digest": "$2a$10$Edk9WTgxXOTXdKPiMgDHQur7zAkSBhMESNPzQftA/fd5m7V.lXlgW",
        "remember_digest": null,
        "reset_digest": null,
        "reset_sent_at": null,
        "birth_date": "1995-01-01T00:00:00.000Z"
    },
    "itinerary": {
        "id": 2,
        "currency_code": "IDR",
        "price_rule_id": 2,
        "created_at": "2018-02-20T06:11:32.632Z",
        "updated_at": "2018-02-20T06:11:32.632Z"
    },
    "statuses": [
        {
            "id": 1,
            "tag": "wait-payment",
            "name": "Waiting for payment",
            "description": "Init (normal booking): User books flights\nInit (WL-booking): After user confirms to pay, add 7 more minutes to the countdown ",
            "created_at": "2018-02-15T09:00:00.000Z",
            "updated_at": "2018-02-15T09:00:00.000Z"
        }
    ],
    "passengers": [
        {
            "id": 6,
            "user_id": 2,
            "category": "Adult",
            "name": "Octavianus Marcel Harjono",
            "title": "Mr.",
            "birth_date": null,
            "is_hidden": false
        },
        {
            "id": 7,
            "user_id": 2,
            "category": "Adult",
            "name": "Fauzan Rifqy",
            "title": "Mr.",
            "birth_date": null,
            "is_hidden": false
        },
        {
            "id": 8,
            "user_id": 2,
            "category": "Adult",
            "name": "Older Brother",
            "title": "Mr.",
            "birth_date": null,
            "is_hidden": false
        },
        {
            "id": 9,
            "user_id": 2,
            "category": "Adult",
            "name": "Little Brother",
            "title": "Mr.",
            "birth_date": null,
            "is_hidden": false
        }
    ]
}
```

This endpoint creates a booking entry.

### HTTP Request

`POST http://35.224.189.34:3000/bookings`