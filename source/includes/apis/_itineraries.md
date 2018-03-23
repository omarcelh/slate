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

`GET http://35.224.189.34:3000/api/v1/itineraries/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the itinerary to retrieve

## Search Itineraries

> Format

```json
{
  "origin": "{{origin_city}}",
  "destination": "{{destination_city}}",
  "out_date": "{{out_date}}",
  "service_class": "{{service_class}}",
  "adults": "{{number_of_adults}}",
  "children": "{{number_of_children}}",
  "infants": "{{number_of_infants}}"
}
```

> Example request

```json
{
  "origin": "CGK",
  "destination": "DPS",
  "out_date": "2018-05-01",
  "service_class": "eco",
  "adults": "1",
  "children": "1",
  "infants": "1"
}
```

> The above request returns JSON structured like this:

```json
{
    "log_id": "1521785515-7111e17c854a9e7753fbc50035309d2714fdb277",
    "session_id": "196C1K9M3MJN8JFUH34UCVE3T0:9B601E5F6A909D618F175BB1A9601DDFD8106FA6",
    "cabin": {
        "economy": [
            "L",
            "H",
            "S",
            "V",
            "T",
            "Q",
            "N",
            "K",
            "M",
            "B",
            "Y",
            "W"
        ],
        "business": [
            "I",
            "D",
            "C",
            "J"
        ],
        "first": [
            "A",
            "F"
        ],
        "all": [
            "L",
            "H",
            "S",
            "V",
            "T",
            "Q",
            "N",
            "K",
            "M",
            "B",
            "Y",
            "W",
            "I",
            "D",
            "C",
            "J",
            "A",
            "F"
        ],
        "availability": [
            "L",
            "H",
            "S",
            "V",
            "T",
            "Q",
            "N",
            "K",
            "M",
            "B",
            "Y"
        ]
    },
    "classes": [
        {
            "num_flights": 1,
            "flights": [
                {
                    "flight_id": "400",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0101",
                    "origin": "CGK",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 05:40:00",
                    "arrives_at": "2018-05-01 08:40:00"
                }
            ]
        },
        {
            "num_flights": 1,
            "flights": [
                {
                    "flight_id": "438",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0102",
                    "origin": "CGK",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 07:05:00",
                    "arrives_at": "2018-05-01 10:10:00"
                }
            ]
        },
        {
            "num_flights": 1,
            "flights": [
                {
                    "flight_id": "402",
                    "airline_id": "GA",
                    "aircraft_id": "333",
                    "number": "0103",
                    "origin": "CGK",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 07:45:00",
                    "arrives_at": "2018-05-01 10:45:00"
                }
            ]
        },
        {
            "num_flights": 1,
            "flights": [
                {
                    "flight_id": "404",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0104",
                    "origin": "CGK",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 09:35:00",
                    "arrives_at": "2018-05-01 12:30:00"
                }
            ]
        },
        {
            "num_flights": 1,
            "flights": [
                {
                    "flight_id": "408",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0105",
                    "origin": "CGK",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 11:30:00",
                    "arrives_at": "2018-05-01 14:30:00"
                }
            ]
        },
        {
            "num_flights": 1,
            "flights": [
                {
                    "flight_id": "422",
                    "airline_id": "GA",
                    "aircraft_id": "333",
                    "number": "0106",
                    "origin": "CGK",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 13:10:00",
                    "arrives_at": "2018-05-01 16:10:00"
                }
            ]
        },
        {
            "num_flights": 1,
            "flights": [
                {
                    "flight_id": "410",
                    "airline_id": "GA",
                    "aircraft_id": "333",
                    "number": "0107",
                    "origin": "CGK",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 14:25:00",
                    "arrives_at": "2018-05-01 17:20:00"
                }
            ]
        },
        {
            "num_flights": 1,
            "flights": [
                {
                    "flight_id": "414",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0108",
                    "origin": "CGK",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 14:55:00",
                    "arrives_at": "2018-05-01 18:00:00"
                }
            ]
        },
        {
            "num_flights": 1,
            "flights": [
                {
                    "flight_id": "420",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0109",
                    "origin": "CGK",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 16:30:00",
                    "arrives_at": "2018-05-01 19:30:00"
                }
            ]
        },
        {
            "num_flights": 1,
            "flights": [
                {
                    "flight_id": "426",
                    "airline_id": "GA",
                    "aircraft_id": "333",
                    "number": "0110",
                    "origin": "CGK",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 17:15:00",
                    "arrives_at": "2018-05-01 20:15:00"
                }
            ]
        },
        {
            "num_flights": 1,
            "flights": [
                {
                    "flight_id": "424",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0201",
                    "origin": "CGK",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 21:10:00",
                    "arrives_at": "2018-05-02 00:10:00"
                }
            ]
        },
        {
            "num_flights": 1,
            "flights": [
                {
                    "flight_id": "652",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0202",
                    "origin": "CGK",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 21:40:00",
                    "arrives_at": "2018-05-02 00:40:00"
                }
            ]
        },
        {
            "num_flights": 2,
            "flights": [
                {
                    "flight_id": "216",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0301",
                    "origin": "CGK",
                    "destination": "JOG",
                    "departs_at": "2018-05-01 18:25:00",
                    "arrives_at": "2018-05-01 19:40:00"
                },
                {
                    "flight_id": "254",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0302",
                    "origin": "JOG",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 20:45:00",
                    "arrives_at": "2018-05-01 23:05:00"
                }
            ]
        },
        {
            "num_flights": 2,
            "flights": [
                {
                    "flight_id": "236",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0303",
                    "origin": "CGK",
                    "destination": "SRG",
                    "departs_at": "2018-05-01 11:50:00",
                    "arrives_at": "2018-05-01 13:05:00"
                },
                {
                    "flight_id": "447",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0304",
                    "origin": "SRG",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 14:15:00",
                    "arrives_at": "2018-05-01 16:35:00"
                }
            ]
        },
        {
            "num_flights": 2,
            "flights": [
                {
                    "flight_id": "316",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0305",
                    "origin": "CGK",
                    "destination": "SUB",
                    "departs_at": "2018-05-01 13:30:00",
                    "arrives_at": "2018-05-01 15:05:00"
                },
                {
                    "flight_id": "344",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0306",
                    "origin": "SUB",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 16:25:00",
                    "arrives_at": "2018-05-01 18:40:00"
                }
            ]
        },
        {
            "num_flights": 2,
            "flights": [
                {
                    "flight_id": "102",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0307",
                    "origin": "CGK",
                    "destination": "PLM",
                    "departs_at": "2018-05-01 07:35:00",
                    "arrives_at": "2018-05-01 08:45:00"
                },
                {
                    "flight_id": "266",
                    "airline_id": "GA",
                    "aircraft_id": "CRK",
                    "number": "0308",
                    "origin": "PLM",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 09:45:00",
                    "arrives_at": "2018-05-01 13:00:00"
                }
            ]
        },
        {
            "num_flights": 2,
            "flights": [
                {
                    "flight_id": "202",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0309",
                    "origin": "CGK",
                    "destination": "JOG",
                    "departs_at": "2018-05-01 05:20:00",
                    "arrives_at": "2018-05-01 06:35:00"
                },
                {
                    "flight_id": "250",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0310",
                    "origin": "JOG",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 08:25:00",
                    "arrives_at": "2018-05-01 10:50:00"
                }
            ]
        },
        {
            "num_flights": 2,
            "flights": [
                {
                    "flight_id": "210",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0311",
                    "origin": "CGK",
                    "destination": "JOG",
                    "departs_at": "2018-05-01 13:00:00",
                    "arrives_at": "2018-05-01 14:20:00"
                },
                {
                    "flight_id": "252",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0312",
                    "origin": "JOG",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 16:15:00",
                    "arrives_at": "2018-05-01 18:40:00"
                }
            ]
        },
        {
            "num_flights": 2,
            "flights": [
                {
                    "flight_id": "306",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0401",
                    "origin": "CGK",
                    "destination": "SUB",
                    "departs_at": "2018-05-01 07:25:00",
                    "arrives_at": "2018-05-01 09:00:00"
                },
                {
                    "flight_id": "342",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0402",
                    "origin": "SUB",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 11:00:00",
                    "arrives_at": "2018-05-01 13:10:00"
                }
            ]
        },
        {
            "num_flights": 2,
            "flights": [
                {
                    "flight_id": "316",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0403",
                    "origin": "CGK",
                    "destination": "SUB",
                    "departs_at": "2018-05-01 13:30:00",
                    "arrives_at": "2018-05-01 15:05:00"
                },
                {
                    "flight_id": "338",
                    "airline_id": "GA",
                    "aircraft_id": "CRK",
                    "number": "0404",
                    "origin": "SUB",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 17:10:00",
                    "arrives_at": "2018-05-01 19:15:00"
                }
            ]
        },
        {
            "num_flights": 2,
            "flights": [
                {
                    "flight_id": "314",
                    "airline_id": "GA",
                    "aircraft_id": "332",
                    "number": "0405",
                    "origin": "CGK",
                    "destination": "SUB",
                    "departs_at": "2018-05-01 12:50:00",
                    "arrives_at": "2018-05-01 14:30:00"
                },
                {
                    "flight_id": "344",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0406",
                    "origin": "SUB",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 16:25:00",
                    "arrives_at": "2018-05-01 18:40:00"
                }
            ]
        },
        {
            "num_flights": 2,
            "flights": [
                {
                    "flight_id": "610",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0407",
                    "origin": "CGK",
                    "destination": "UPG",
                    "departs_at": "2018-05-01 15:00:00",
                    "arrives_at": "2018-05-01 18:30:00"
                },
                {
                    "flight_id": "621",
                    "airline_id": "GA",
                    "aircraft_id": "738",
                    "number": "0408",
                    "origin": "UPG",
                    "destination": "DPS",
                    "departs_at": "2018-05-01 19:35:00",
                    "arrives_at": "2018-05-01 21:00:00"
                }
            ]
        }
    ]
}
```

This endpoint gives availability on itineraries search result.

### HTTP Request

`POST http://35.224.189.34:3000/api/v1/itineraries/search`

or

`GET http://35.224.189.34:3000/api/v1/itineraries/search?origin=CGK&destination=DPS&out_date=2018-05-01&service_class=eco&adults=1&children=1&infants=1`

## Get Single Fare

> Format

```json
{
    "log_id": "{{log_id_from_availability}}",
    "session_id": "{{session_id_from_availability}}",
    "origin": "{{origin_city}}",
    "destination": "{{destination_city}}",
    "out_date": "{{out_date}}",
    "service_class": "{{service_class}}",
    "adults": "{{number_of_adults}}",
    "children": "{{number_of_children}}",
    "infants": "{{number_of_infants}}"
    "selected_departure": {
        "flight_id": "{{flight.flight_id}}",
        "airline_id": "{{flight.airline_id}}",
        "aircraft_id": "{{flight.aircraft_id}}",
        "number": "{{flight.number}}",
        "origin": "{{flight.origin}}",
        "destination": "{{flight.destination}}",
        "departs_at": "{{flight.departs_at}}",
        "arrives_at": "{{flight.arrives_at}}"
    }
}
```

> Example request

```json
{
    "log_id": "1521785515-7111e17c854a9e7753fbc50035309d2714fdb277",
    "session_id": "196C1K9M3MJN8JFUH34UCVE3T0:9B601E5F6A909D618F175BB1A9601DDFD8106FA6",
    "origin": "CGK",
    "destination": "DPS",
    "out_date": "2018-05-01",
    "service_class": "eco",
    "adults": "1",
    "children": "1",
    "infants": "1",
    "selected_departure": {
        "flight_id": "438",
        "airline_id": "GA",
        "aircraft_id": "738",
        "number": "0102",
        "origin": "CGK",
        "destination": "DPS",
        "departs_at": "2018-05-01 07:05:00",
        "arrives_at": "2018-05-01 10:10:00"
    }
}
```

> The above request returns JSON structured like this:

```json
{
    "log_id": "1521788093-b7a91a79ce26eaf96054e2e3fb674a793701280c",
    "session_id": "196C1K9M3MJN8JFUH34UCVE3T0:9B601E5F6A909D618F175BB1A9601DDFD8106FA6",
    "price": {
        "adults": {
            "basicFare": "970000.00",
            "taxs": {
                "YR": "5000.00",
                "D5": "130000.00",
                "ID": "97000.00"
            },
            "taxsDetail": {
                "YRVB": "5000",
                "D5CB": "130000",
                "IDLO": "97000"
            },
            "taxTotal": "232000.00",
            "netTotal": "1202000.00",
            "pax": 1,
            "total": "1202000.00"
        },
        "childs": {
            "basicFare": "970000.00",
            "taxs": {
                "YR": "5000.00",
                "D5": "130000.00",
                "ID": "97000.00"
            },
            "taxsDetail": {
                "YRVB": "5000",
                "D5CB": "130000",
                "IDLO": "97000"
            },
            "taxTotal": "232000.00",
            "netTotal": "1202000.00",
            "pax": 1,
            "total": "1202000.00"
        },
        "infants": {
            "basicFare": "97000.00",
            "taxs": {
                "YR": "5000.00",
                "ID": "9700.00"
            },
            "taxTotal": "14700.00",
            "netTotal": "111700.00",
            "pax": 1,
            "total": "111700.00"
        }
    },
    "price_total": "2515700.00"
}
```

This endpoint gives fare on specific itinerary.

### HTTP Request

`POST http://35.224.189.34:3000/api/v1/itineraries/fare`