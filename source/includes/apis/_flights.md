# Flights
## Get All Flights

> returns JSON structured like this:

```json
[
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
]
```

This endpoint retrieves all flights.

### HTTP Request

`GET http://35.224.189.34:3000/api/v1/flights`

## Get a Specific Flight

> returns JSON structured like this:

```json
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
    "updated_at": "2018-03-01T07:04:27.422Z",
    "aircraft": {
        "id": 117,
        "iata": "CL4",
        "icao": "CL44",
        "description": "Canadair CL-44"
    },
    "airline": {
        "id": 1905,
        "name": "Corporate Jets",
        "alias": null,
        "callsign": "SEA JET",
        "country": "United States",
        "created_at": "2018-03-01T07:03:33.928Z",
        "updated_at": "2018-03-01T07:03:33.928Z"
    },
    "flight_facility": {
        "id": 1,
        "flight_id": 1,
        "has_flight_entertainment": true,
        "has_meal": true,
        "has_wifi": true,
        "created_at": "2018-03-01T07:04:27.453Z",
        "updated_at": "2018-03-01T07:04:27.453Z"
    },
    "itinerary": {
        "id": 1,
        "currency_code": "IDR",
        "price_rule_id": 1,
        "created_at": "2018-03-01T07:04:27.390Z",
        "updated_at": "2018-03-01T07:04:27.390Z"
    }
}
```

This endpoint retrieves a specific flight.

<aside class="notice">This includes the relations: aircraft, airline, flight_facility, itinerary.</aside>

### HTTP Request

`GET http://35.224.189.34:3000/flights/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the flight to retrieve
