# WlpsqueueStatusTypes
## Get All WlpsqueueStatusTypes

> returns JSON structured like this:

```json
[
    {
        "id": 1,
        "tag": "queue",
        "name": "Queueing",
        "description": "Before WL sales period starts\nInit: User enrolled in waiting list",
        "created_at": "2018-02-15T09:00:00.000Z",
        "updated_at": "2018-02-15T09:00:00.000Z"
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
        "id": 3,
        "tag": "seat-found",
        "name": "Seat found",
        "description": "During WL sales period\nInit: Seat is available for the user\nAction: System gives 3 minutes for User to confirm that he wants to take it and is ready to pay\nAction: Seat is booked under his name in airline CRS",
        "created_at": "2018-02-17T09:00:00.000Z",
        "updated_at": "2018-02-17T09:00:00.000Z"
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
        "id": 5,
        "tag": "epass-issued",
        "name": "E-boarding pass issued",
        "description": "Init: Automatic check-in is performed, e-boarding pass issued by airline and sent to User",
        "created_at": "2018-02-19T09:00:00.000Z",
        "updated_at": "2018-02-19T09:00:00.000Z"
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
        "id": 7,
        "tag": "seat-not-found",
        "name": "Seat not found",
        "description": "After WL-sales period\nInit: User didn’t get seat confirmation within the whole WL sales period\nAction: show something",
        "created_at": "2018-02-21T09:00:00.000Z",
        "updated_at": "2018-02-21T09:00:00.000Z"
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
        "id": 9,
        "tag": "switched-to-booking",
        "name": "Switched",
        "description": "User chooses to buy ticket now with normal price (contact and passenger information from this queue is used by default)",
        "created_at": "2018-02-23T09:00:00.000Z",
        "updated_at": "2018-02-23T09:00:00.000Z"
    }
]
```

This endpoint retrieves all wlpsqueue status types.

### HTTP Request

`GET http://35.224.189.34:3000/api/v1/wlpsqueue_status_types`

## Get a Specific WlpsqueueStatusType

> returns JSON structured like this:

```json
{
    "id": 1,
    "tag": "queue",
    "name": "Queueing",
    "description": "Before WL sales period starts\nInit: User enrolled in waiting list",
    "created_at": "2018-02-15T09:00:00.000Z",
    "updated_at": "2018-02-15T09:00:00.000Z"
}
```

This endpoint retrieves a specific wlpsqueue status type.

<aside class="notice">This includes the relations: [WlpsqueueStatusType Relation].</aside>

### HTTP Request

`GET http://35.224.189.34:3000/wlpsqueue_status_types/<tag>`

### URL Parameters

Parameter | Description
--------- | -----------
tag | The tag of the wlpsqueue status type to retrieve

## Delete a Specific WlpsqueueStatusType

> The above command returns JSON structured like this:

```json
{
    "tag": "new-wst",
    "message": "WlpsqueueStatusType is deleted"
}
```

This endpoint deletes a specific wlpsqueue status type.

### HTTP Request

`DELETE http://35.224.189.34:3000/wlpsqueue_status_types/<tag>`

### URL Parameters

Parameter | Description
--------- | -----------
tag | The tag of the wlpsqueue status type to delete

## Create a WlpsqueueStatusType

```json
{
    "tag": "new-wst",
    "name": "wst",
    "description": "description"
}
```

> The above request returns JSON structured like this:

```json
{
    "id": 10,
    "tag": "new-wst",
    "name": "wst",
    "description": "description",
    "created_at": "2018-03-02T08:00:06.845Z",
    "updated_at": "2018-03-02T08:00:06.845Z"
}
```

This endpoint creates a wlpsqueue status type entry.

### HTTP Request

`POST http://35.224.189.34:3000/wlpsqueue_status_types`

