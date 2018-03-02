# Wlpsqueues
## Get All Wlpsqueues

> returns JSON structured like this:

```json
[
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
```

This endpoint retrieves all wlpsqueues.

### HTTP Request

`GET http://example.com/api/v1/wlpsqueues`

## Get a Specific Wlpsqueue

> returns JSON structured like this:

```json
{
    "id": 1,
    "number": 1,
    "contact_person_id": 1,
    "itinerary_id": 1,
    "total_price": 100,
    "created_at": "2018-03-01T07:04:27.589Z",
    "updated_at": "2018-03-01T07:04:27.589Z",
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
            "id": 9,
            "tag": "switched-to-booking",
            "name": "Switched",
            "description": "User chooses to buy ticket now with normal price (contact and passenger information from this queue is used by default)",
            "created_at": "2018-02-23T09:00:00.000Z",
            "updated_at": "2018-02-23T09:00:00.000Z"
        },
        {
            "id": 8,
            "tag": "left-queue",
            "name": "Left queue",
            "description": "Before/during WL-sales period\nInit: User chooses to leave waiting list",
            "created_at": "2018-02-22T09:00:00.000Z",
            "updated_at": "2018-02-22T09:00:00.000Z"
        },
        {
            "id": 7,
            "tag": "seat-not-found",
            "name": "Seat not found",
            "description": "After WL-sales period\nInit: User didn’t get seat confirmation within the whole WL sales period\nAction: show something",
            "created_at": "2018-02-21T09:00:00.000Z",
            "updated_at": "2018-02-21T09:00:00.000Z"
        },
        {
            "id": 6,
            "tag": "cannot-checkin",
            "name": "Cannot check-in",
            "description": "Init: Automatic check-in failed\nInit: Automatic check-in not supported by the airport/airline",
            "created_at": "2018-02-20T09:00:00.000Z",
            "updated_at": "2018-02-20T09:00:00.000Z"
        },
        {
            "id": 5,
            "tag": "epass-issued",
            "name": "E-boarding pass issued",
            "description": "Init: Automatic check-in is performed, e-boarding pass issued by airline and sent to User",
            "created_at": "2018-02-19T09:00:00.000Z",
            "updated_at": "2018-02-19T09:00:00.000Z"
        },
        {
            "id": 4,
            "tag": "seat-rejected",
            "name": "Seat rejected",
            "description": "During (and after) WL sales period\nInit: User choose not to buy after the system give seat offer\nAction: Cancel booking in airline CRS\nAction: Seat is offered to the next person in the queue",
            "created_at": "2018-02-18T09:00:00.000Z",
            "updated_at": "2018-02-18T09:00:00.000Z"
        },
        {
            "id": 3,
            "tag": "seat-found",
            "name": "Seat found",
            "description": "During WL sales period\nInit: Seat is available for the user\nAction: System gives 3 minutes for User to confirm that he wants to take it and is ready to pay\nAction: Seat is booked under his name in airline CRS",
            "created_at": "2018-02-17T09:00:00.000Z",
            "updated_at": "2018-02-17T09:00:00.000Z"
        },
        {
            "id": 2,
            "tag": "search-seat",
            "name": "Searching for seats",
            "description": "During WL sales period\nInit: User hasn’t received seat offer\nInit: User missed the previous seat offer (doesn’t give confirmation or payment time-out)",
            "created_at": "2018-02-16T09:00:00.000Z",
            "updated_at": "2018-02-16T09:00:00.000Z"
        },
        {
            "id": 1,
            "tag": "queue",
            "name": "Queueing",
            "description": "Before WL sales period starts\nInit: User enrolled in waiting list",
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

This endpoint retrieves a specific wlpsqueue.

<aside class="notice">This includes the relations: contact_person, itinerary, statuses, and passengers.</aside>

### HTTP Request

`GET http://example.com/wlpsqueues/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the wlpsqueue to retrieve

<!-- ## Delete a Specific Wlpsqueue

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "message": "Wlpsqueue is deleted"
}
```

This endpoint deletes a specific wlpsqueue.

### HTTP Request

`DELETE http://example.com/wlpsqueues/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the wlpsqueue to delete

## Create a Wlpsqueue

```json
```

> The above request returns JSON structured like this:

```json
```

This endpoint creates a wlpsqueue entry.

### HTTP Request

`POST http://example.com/wlpsqueues`
 -->