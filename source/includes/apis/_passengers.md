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

`GET http://35.224.189.34:3000/api/v1/passengers`

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

`GET http://35.224.189.34:3000/passengers/<ID>`

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

`DELETE http://35.224.189.34:3000/passengers/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the passenger to delete
