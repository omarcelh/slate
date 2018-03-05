<!-- Airports -->
# Airports
## Get All Airports

> returns JSON structured like this:

```json
[
    {
        "id": 1,
        "name": "Goroka Airport",
        "city": "Goroka",
        "country": "Papua New Guinea",
        "iata": "GKA",
        "icao": "AYGA",
        "latitude": -6.081689834590001,
        "longitude": 145.391998291,
        "altitude": 5282,
        "timezone": 10,
        "dst": "U",
        "created_at": "2018-02-20T06:09:13.140Z",
        "updated_at": "2018-02-20T06:09:13.140Z"
    },
    {
        "id": 2,
        "name": "Madang Airport",
        "city": "Madang",
        "country": "Papua New Guinea",
        "iata": "MAG",
        "icao": "AYMD",
        "latitude": -5.20707988739,
        "longitude": 145.789001465,
        "altitude": 20,
        "timezone": 10,
        "dst": "U",
        "created_at": "2018-02-20T06:09:13.149Z",
        "updated_at": "2018-02-20T06:09:13.149Z"
    },
    {
        "id": 3,
        "name": "Mount Hagen Kagamuga Airport",
        "city": "Mount Hagen",
        "country": "Papua New Guinea",
        "iata": "HGU",
        "icao": "AYMH",
        "latitude": -5.826789855957031,
        "longitude": 144.29600524902344,
        "altitude": 5388,
        "timezone": 10,
        "dst": "U",
        "created_at": "2018-02-20T06:09:13.158Z",
        "updated_at": "2018-02-20T06:09:13.158Z"
    },
    {
        "id": 4,
        "name": "Nadzab Airport",
        "city": "Nadzab",
        "country": "Papua New Guinea",
        "iata": "LAE",
        "icao": "AYNZ",
        "latitude": -6.569803,
        "longitude": 146.725977,
        "altitude": 239,
        "timezone": 10,
        "dst": "U",
        "created_at": "2018-02-20T06:09:13.166Z",
        "updated_at": "2018-02-20T06:09:13.166Z"
    },
    {
        "id": 5,
        "name": "Port Moresby Jacksons International Airport",
        "city": "Port Moresby",
        "country": "Papua New Guinea",
        "iata": "POM",
        "icao": "AYPY",
        "latitude": -9.443380355834961,
        "longitude": 147.22000122070312,
        "altitude": 146,
        "timezone": 10,
        "dst": "U",
        "created_at": "2018-02-20T06:09:13.175Z",
        "updated_at": "2018-02-20T06:09:13.175Z"
    },
    {
        "id": 6,
        "name": "Wewak International Airport",
        "city": "Wewak",
        "country": "Papua New Guinea",
        "iata": "WWK",
        "icao": "AYWK",
        "latitude": -3.58383011818,
        "longitude": 143.669006348,
        "altitude": 19,
        "timezone": 10,
        "dst": "U",
        "created_at": "2018-02-20T06:09:13.183Z",
        "updated_at": "2018-02-20T06:09:13.183Z"
    },
    {
        "id": 7,
        "name": "Narsarsuaq Airport",
        "city": "Narssarssuaq",
        "country": "Greenland",
        "iata": "UAK",
        "icao": "BGBW",
        "latitude": 61.1604995728,
        "longitude": -45.4259986877,
        "altitude": 112,
        "timezone": -3,
        "dst": "E",
        "created_at": "2018-02-20T06:09:13.191Z",
        "updated_at": "2018-02-20T06:09:13.191Z"
    },
    {
        "id": 8,
        "name": "Godthaab / Nuuk Airport",
        "city": "Godthaab",
        "country": "Greenland",
        "iata": "GOH",
        "icao": "BGGH",
        "latitude": 64.19090271,
        "longitude": -51.6781005859,
        "altitude": 283,
        "timezone": -3,
        "dst": "E",
        "created_at": "2018-02-20T06:09:13.198Z",
        "updated_at": "2018-02-20T06:09:13.198Z"
    },
    {
        "id": 9,
        "name": "Kangerlussuaq Airport",
        "city": "Sondrestrom",
        "country": "Greenland",
        "iata": "SFJ",
        "icao": "BGSF",
        "latitude": 67.0122218992,
        "longitude": -50.7116031647,
        "altitude": 165,
        "timezone": -3,
        "dst": "E",
        "created_at": "2018-02-20T06:09:13.206Z",
        "updated_at": "2018-02-20T06:09:13.206Z"
    },
    {
        "id": 10,
        "name": "Thule Air Base",
        "city": "Thule",
        "country": "Greenland",
        "iata": "THU",
        "icao": "BGTL",
        "latitude": 76.5311965942,
        "longitude": -68.7032012939,
        "altitude": 251,
        "timezone": -4,
        "dst": "E",
        "created_at": "2018-02-20T06:09:13.215Z",
        "updated_at": "2018-02-20T06:09:13.215Z"
    }
]
```

This endpoint retrieves all airports.

### HTTP Request

`GET http://35.224.189.34:3000/api/v1/airports`

## Get a Specific Airport

> returns JSON structured like this:

```json
{
    "id": 2258,
    "name": "Soekarno-Hatta International Airport",
    "city": "Jakarta",
    "country": "Indonesia",
    "iata": "CGK",
    "icao": "WIII",
    "latitude": -6.1255698204,
    "longitude": 106.65599823,
    "altitude": 34,
    "timezone": 7,
    "dst": "N",
    "created_at": "2018-02-20T06:09:32.544Z",
    "updated_at": "2018-02-20T06:09:32.544Z"
}
```

This endpoint retrieves a specific airport.

### HTTP Request

`GET http://35.224.189.34:3000/airports/<IATACODE>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the airport to retrieve

## Delete a Specific Airport

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "message": "Airport is deleted"
}
```

This endpoint deletes a specific airport.

### HTTP Request

`DELETE http://35.224.189.34:3000/airports/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the airport to delete

## Create a Airport

```json
{ 
  "name": "Soekarno-Hatta International Airport",
  "city": "Jakarta",
  "country": "Indonesia",
  "iata": "CGK",
  "icao": "WIII",
  "latitude": -6.1255698204,
  "longitude": 106.65599823,
  "altitude": 34,
  "timezone": 7,
  "dst": "N"
}
```

> The above request returns JSON structured like this:

```json
{
    "id": 5451,
    "name": "Soekarno-Hatta International Airport",
    "city": "Jakarta",
    "country": "Indonesia",
    "iata": "CGK",
    "icao": "WIII",
    "latitude": -6.1255698204,
    "longitude": 106.65599823,
    "altitude": 34,
    "timezone": 7,
    "dst": "N",
    "created_at": "2018-02-28T07:13:20.139Z",
    "updated_at": "2018-02-28T07:13:20.139Z"
}
```

This endpoint creates a airport entry.

### HTTP Request

`POST http://35.224.189.34:3000/airports`

