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

`GET http://35.224.189.34:3000/api/v1/aircrafts`

## Get a Specific Aircraft

> returns JSON structured like this:

```json
{
    "id": 1,
    "iata": "A4F",
    "icao": "A124",
    "description": "Antonov AN-124 Ruslan"
}
```

This endpoint retrieves a specific aircraft.

### HTTP Request

`GET http://35.224.189.34:3000/aircrafts/<IataCode>`

### URL Parameters

Parameter | Description
--------- | -----------
IataCode | The IataCode of the aircraft to retrieve

