# Itineraries
## Get All Itineraries

> returns JSON structured like this:

```json
[
    {
        "id": 1,
        "currency_code": "IDR",
        "price_rule_id": 1,
        "created_at": "2018-03-01T07:04:27.390Z",
        "updated_at": "2018-03-01T07:04:27.390Z"
    }
]
```

This endpoint retrieves all itineraries.

### HTTP Request

`GET http://35.224.189.34:3000/api/v1/itineraries`

## Get a Specific Itinerary

> returns JSON structured like this:

```json
{
    "id": 1,
    "currency_code": "IDR",
    "price_rule_id": 1,
    "created_at": "2018-03-01T07:04:27.390Z",
    "updated_at": "2018-03-01T07:04:27.390Z",
    "price_rule": {
        "id": 1,
        "adult": 100.4,
        "child": 200.1,
        "infant": 30,
        "created_at": "2018-03-01T07:04:27.335Z",
        "updated_at": "2018-03-01T07:04:27.335Z"
    },
    "flights": [
        {
            "id": 1,
            "itinerary_id": 1,
            "airline_id": 1905,
            "aircraft_id": 117,
            "number": "GA123",
            "origin": "CGK",
            "destination": "SYD",
            "departs_at": "2018-03-01T07:04:27.404Z",
            "arrives_at": "2018-03-01T07:04:27.404Z",
            "created_at": "2018-03-01T07:04:27.422Z",
            "updated_at": "2018-03-01T07:04:27.422Z"
        }
    ],
    "wlpsqueues": [
        {
            "id": 1,
            "number": 1,
            "contact_person_id": 1,
            "itinerary_id": 1,
            "total_price": 100,
            "created_at": "2018-03-01T07:04:27.589Z",
            "updated_at": "2018-03-01T07:04:27.589Z"
        }
    ],
    "bookings": [
        {
            "id": 1,
            "number": 1,
            "contact_person_id": 1,
            "itinerary_id": 1,
            "total_price": 100,
            "created_at": "2018-03-01T07:04:27.620Z",
            "updated_at": "2018-03-01T07:04:27.620Z"
        }
    ]
}
```

This endpoint retrieves a specific itinerary.

<aside class="notice">This includes the relations: price_rule, flights, wlpsqueues, bookings.</aside>

### HTTP Request

`GET http://35.224.189.34:3000/itineraries/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the itinerary to retrieve
