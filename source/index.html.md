---
title: WLPS API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - json

toc_footers:
  - <a href='https://github.com/omarcelh/wlps-core'>WLPS Github</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to flight waiting list passenger system API. You can get information on various flight and itinerary from different airlines in the world.

<!-- Passengers  -->
# Passengers
## Get All Passenger

> returns JSON structured like this:

```json
[
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
```

This endpoint retrieves all passengers.

### HTTP Request

`GET http://example.com/api/v1/passengers`

## Get a Specific Passenger

> returns JSON structured like this:

```json
{
    "id": 1,
    "user_id": 1,
    "category": "Adult",
    "name": "Octavianus Marcel Harjono",
    "title": "Mr.",
    "birth_date": null,
    "is_hidden": false,
    "user": {
        "id": 1,
        "name": "Octavianus Marcel Harjono",
        "username": "omarcelh",
        "email": "octavianusmarcel12@gmail.com",
        "phone": "087836901995",
        "api_token": null,
        "created_at": "2018-02-15T05:56:28.686Z",
        "updated_at": "2018-02-15T05:56:28.686Z",
        "password_digest": "$2a$10$FGljsowxyNvoZ1rKgRvKtuzSR05g1Yj5XhyCjkpw5Qe/yXDVg45ei",
        "remember_digest": null,
        "reset_digest": null,
        "reset_sent_at": null,
        "birth_date": "1995-10-07T00:00:00.000Z"
    },
    "wlpsqueues": [
        {
            "id": 1,
            "number": 1,
            "contact_person_id": 1,
            "itinerary_id": 1,
            "total_price": 100,
            "created_at": "2018-02-15T05:56:28.718Z",
            "updated_at": "2018-02-15T05:56:28.718Z"
        }
    ],
    "bookings": [
        {
            "id": 1,
            "number": 1,
            "contact_person_id": 1,
            "itinerary_id": 1,
            "total_price": 100,
            "created_at": "2018-02-15T05:56:28.759Z",
            "updated_at": "2018-02-15T05:56:28.759Z"
        }
    ]
}
```

This endpoint retrieves a specific passenger.

<aside class="notice">This includes the relations: user (contact person), wlpsqueues, and bookings.</aside>

### HTTP Request

`GET http://example.com/passengers/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the passenger to retrieve

## Delete a Specific Passenger

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "message": "Passenger is deleted"
}
```

This endpoint deletes a specific passenger.

### HTTP Request

`DELETE http://example.com/passengers/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the passenger to delete

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

`GET http://example.com/api/v1/bookings`

## Get a Specific Booking

> returns JSON structured like this:

```json
{
    "id": 1,
    "number": 1,
    "contact_person_id": 1,
    "itinerary_id": 1,
    "total_price": 100,
    "created_at": "2018-02-20T06:11:15.841Z",
    "updated_at": "2018-02-20T06:11:15.841Z",
    "contact_person": {
        "id": 1,
        "name": "Octavianus Marcel Harjono",
        "username": "omarcelh",
        "email": "octavianusmarcel12@gmail.com",
        "phone": "087836901995",
        "api_token": null,
        "created_at": "2018-02-20T06:11:15.774Z",
        "updated_at": "2018-02-20T06:11:15.774Z",
        "password_digest": "$2a$10$MSJobx233lLeguce9zpb2ehdx9mmdaq1T6BrrxZg9wdivOD3fhM9K",
        "remember_digest": null,
        "reset_digest": null,
        "reset_sent_at": null,
        "birth_date": "1995-10-07T00:00:00.000Z"
    },
    "itinerary": {
        "id": 1,
        "currency_code": "IDR",
        "price_rule_id": 1,
        "created_at": "2018-02-20T06:11:15.589Z",
        "updated_at": "2018-02-20T06:11:15.589Z"
    },
    "statuses": [
        {
            "id": 10,
            "tag": "rejected-c",
            "name": "Check-in rejected",
            "description": "Automatic check-in rejected; e-boarding pass cannot be obtained",
            "created_at": "2018-02-24T09:00:00.000Z",
            "updated_at": "2018-02-24T09:00:00.000Z"
        },
        {
            "id": 9,
            "tag": "rejected-a",
            "name": "Payment rejected by airline",
            "description": "Payment from user validated, but we cannot confirm payment to airline, therefore e-ticket cannot be obtained.",
            "created_at": "2018-02-23T09:00:00.000Z",
            "updated_at": "2018-02-23T09:00:00.000Z"
        },
        {
            "id": 8,
            "tag": "cancelled",
            "name": "Cancelled",
            "description": "User chooses “cancel” when status is “waiting for confirmation” or fails to respond until timeout. We request to cancel booking to the airline and offer seat to the next person in queue.",
            "created_at": "2018-02-22T09:00:00.000Z",
            "updated_at": "2018-02-22T09:00:00.000Z"
        },
        {
            "id": 7,
            "tag": "pay-timeout",
            "name": "Payment time-out",
            "description": "Payment hasn’t been made until time-out",
            "created_at": "2018-02-21T09:00:00.000Z",
            "updated_at": "2018-02-21T09:00:00.000Z"
        },
        {
            "id": 6,
            "tag": "b-pass-issued",
            "name": "E-boarding pass issued",
            "description": "Automatic check-in successful. Airline issued boarding pass",
            "created_at": "2018-02-20T09:00:00.000Z",
            "updated_at": "2018-02-20T09:00:00.000Z"
        },
        {
            "id": 5,
            "tag": "ticket-issued",
            "name": "E-ticket issued",
            "description": "Airline issued e-ticket",
            "created_at": "2018-02-19T09:00:00.000Z",
            "updated_at": "2018-02-19T09:00:00.000Z"
        },
        {
            "id": 4,
            "tag": "pay-v",
            "name": "Payment validated",
            "description": "Payment validated either automatically or manually. Confirm payment to airline.",
            "created_at": "2018-02-18T09:00:00.000Z",
            "updated_at": "2018-02-18T09:00:00.000Z"
        },
        {
            "id": 3,
            "tag": "val-p",
            "name": "Validating payment",
            "description": "User confirms payment, not yet validated",
            "created_at": "2018-02-17T09:00:00.000Z",
            "updated_at": "2018-02-17T09:00:00.000Z"
        },
        {
            "id": 2,
            "tag": "wait-p",
            "name": "Waiting for payment",
            "description": "For WL-booking: from “waiting for confirmation”, if user confirms, add more time to the remaining time from previous status",
            "created_at": "2018-02-16T09:00:00.000Z",
            "updated_at": "2018-02-16T09:00:00.000Z"
        },
        {
            "id": 1,
            "tag": "wait-c",
            "name": "Waiting for confirmation",
            "description": "User gets seat confirmation from queue, expected to give readiness confirmation before automatically changed to “cancelled”  (there’s countdown)",
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

`GET http://example.com/bookings/<ID>`

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

`DELETE http://example.com/bookings/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the booking to delete

## Create a Booking

```
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
            "tag": "wait-c",
            "name": "Waiting for confirmation",
            "description": "User gets seat confirmation from queue, expected to give readiness confirmation before automatically changed to “cancelled”  (there’s countdown)",
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

`POST http://example.com/bookings`

<!-- Aircrafts -->
# Aircrafts
## Get All Aircrafts

> returns JSON structured like this:

```json
[
    {
        "id": 1,
        "iata": "A4F",
        "icao": "A124",
        "description": "Antonov AN-124 Ruslan"
    },
    {
        "id": 2,
        "iata": "A40",
        "icao": "A140",
        "description": "Antonov AN-140"
    },
    {
        "id": 3,
        "iata": "A25",
        "icao": "A225",
        "description": "Antonov An-225 Mriya"
    },
    {
        "id": 4,
        "iata": "ABY",
        "icao": "A306",
        "description": "Airbus A300-600"
    },
    {
        "id": 5,
        "iata": "AB3",
        "icao": "A30B",
        "description": "Airbus A300"
    },
    {
        "id": 6,
        "iata": "310",
        "icao": "A310",
        "description": "Airbus A310"
    },
    {
        "id": 7,
        "iata": "318",
        "icao": "A318",
        "description": "Airbus A318"
    },
    {
        "id": 8,
        "iata": "319",
        "icao": "A319",
        "description": "Airbus A319"
    },
    {
        "id": 9,
        "iata": "320",
        "icao": "A320",
        "description": "Airbus A320"
    },
    {
        "id": 10,
        "iata": "321",
        "icao": "A321",
        "description": "Airbus A321"
    }
]
```

This endpoint retrieves all aircrafts.

### HTTP Request

`GET http://example.com/api/v1/aircrafts`

## Get a Specific Aircraft

> returns JSON structured like this:

```json
```

This endpoint retrieves a specific aircraft.

### HTTP Request

`GET http://example.com/aircrafts/<IataCode>`

### URL Parameters

Parameter | Description
--------- | -----------
IataCode | The IataCode of the aircraft to retrieve

