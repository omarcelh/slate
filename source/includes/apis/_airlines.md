<!-- Airlines -->
# Airlines
## Get All Airlines

> returns JSON structured like this:

```json
[
    {
        "id": 1,
        "name": "135 Airways",
        "alias": null,
        "callsign": "GENERAL",
        "country": "United States",
        "created_at": "2018-02-20T06:10:00.350Z",
        "updated_at": "2018-02-20T06:10:00.350Z"
    },
    {
        "id": 2,
        "name": "1Time Airline",
        "alias": null,
        "callsign": "NEXTIME",
        "country": "South Africa",
        "created_at": "2018-02-20T06:10:00.356Z",
        "updated_at": "2018-02-20T06:10:00.356Z"
    },
    {
        "id": 3,
        "name": "2 Sqn No 1 Elementary Flying Training School",
        "alias": null,
        "callsign": "",
        "country": "United Kingdom",
        "created_at": "2018-02-20T06:10:00.367Z",
        "updated_at": "2018-02-20T06:10:00.367Z"
    },
    {
        "id": 4,
        "name": "213 Flight Unit",
        "alias": null,
        "callsign": "",
        "country": "Russia",
        "created_at": "2018-02-20T06:10:00.374Z",
        "updated_at": "2018-02-20T06:10:00.374Z"
    },
    {
        "id": 5,
        "name": "223 Flight Unit State Airline",
        "alias": null,
        "callsign": "CHKALOVSK-AVIA",
        "country": "Russia",
        "created_at": "2018-02-20T06:10:00.381Z",
        "updated_at": "2018-02-20T06:10:00.381Z"
    },
    {
        "id": 6,
        "name": "224th Flight Unit",
        "alias": null,
        "callsign": "CARGO UNIT",
        "country": "Russia",
        "created_at": "2018-02-20T06:10:00.389Z",
        "updated_at": "2018-02-20T06:10:00.389Z"
    },
    {
        "id": 7,
        "name": "247 Jet Ltd",
        "alias": null,
        "callsign": "CLOUD RUNNER",
        "country": "United Kingdom",
        "created_at": "2018-02-20T06:10:00.400Z",
        "updated_at": "2018-02-20T06:10:00.400Z"
    },
    {
        "id": 8,
        "name": "3D Aviation",
        "alias": null,
        "callsign": "SECUREX",
        "country": "United States",
        "created_at": "2018-02-20T06:10:00.411Z",
        "updated_at": "2018-02-20T06:10:00.411Z"
    },
    {
        "id": 9,
        "name": "40-Mile Air",
        "alias": null,
        "callsign": "MILE-AIR",
        "country": "United States",
        "created_at": "2018-02-20T06:10:00.419Z",
        "updated_at": "2018-02-20T06:10:00.419Z"
    },
    {
        "id": 10,
        "name": "4D Air",
        "alias": null,
        "callsign": "QUARTET",
        "country": "Thailand",
        "created_at": "2018-02-20T06:10:00.425Z",
        "updated_at": "2018-02-20T06:10:00.425Z"
    }
]
```

This endpoint retrieves all airlines.

### HTTP Request

`GET http://35.224.189.34:3000/api/v1/airlines`

## Get a Specific Airline

> returns JSON structured like this:

```json
{
    "id": 1,
    "name": "135 Airways",
    "alias": null,
    "callsign": "GENERAL",
    "country": "United States",
    "created_at": "2018-02-20T06:10:00.350Z",
    "updated_at": "2018-02-20T06:10:00.350Z"
}
```

This endpoint retrieves a specific airline.

### HTTP Request

`GET http://35.224.189.34:3000/airlines/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the airline to retrieve