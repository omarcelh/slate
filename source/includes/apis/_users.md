# Users
## Get All Users

> returns JSON structured like this:

```json
[
    {
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
    }
]
```

This endpoint retrieves all users.

### HTTP Request

`GET http://35.224.189.34:3000/api/v1/users`

## Get a Specific User

> returns JSON structured like this:

```json
{
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
    "birth_date": "1995-10-07T00:00:00.000Z",
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
    ]
}
```

This endpoint retrieves a specific user.

<aside class="notice">This includes the relations: bookings and wlpsqueues.</aside>

### HTTP Request

`GET http://35.224.189.34:3000/users/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user to retrieve

## Delete a Specific User

> The above command returns JSON structured like this:

```json
{
  "id": "1",
  "message": "User is deleted"
}
```

This endpoint deletes a specific user.

### HTTP Request

`DELETE http://35.224.189.34:3000/users/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user to delete

## Create a User

```json
{
  "name": "Octavianus Marcel Harjono",
  "username": "octavianus",
  "email": "octavianus@gmail.com",
  "phone": "087812345678",
  "birth_date": "1995-10-07",
  "password": "12345678",
  "password_confirmation": "12345678"
}
```

> The above request returns JSON structured like this:

```json
{
    "id": 1,
    "name": "Octavianus Marcel Harjono",
    "username": "octavianus",
    "email": "octavianus@gmail.com",
    "phone": "087812345678",
    "api_token": null,
    "created_at": "2018-03-02T07:26:57.516Z",
    "updated_at": "2018-03-02T07:26:57.516Z",
    "password_digest": "$2a$10$8exotsdcY//4lge7f0QibuaywwQfEEhu/SMRCc8/wOem0ksLIU3NO",
    "remember_digest": null,
    "reset_digest": null,
    "reset_sent_at": null,
    "birth_date": "1995-10-07T00:00:00.000Z"
}
```

This endpoint creates a user entry.

### HTTP Request

`POST http://35.224.189.34:3000/users`
