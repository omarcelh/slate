# BookingStatusTypes
## Get All BookingStatusTypes

> returns JSON structured like this:

```json
[
    {
        "id": 1,
        "tag": "wait-payment",
        "name": "Waiting for payment",
        "description": "Init (normal booking): User books flights\nInit (WL-booking): After user confirms to pay, add 7 more minutes to the countdown ",
        "created_at": "2018-02-15T09:00:00.000Z",
        "updated_at": "2018-02-15T09:00:00.000Z"
    },
    {
        "id": 2,
        "tag": "val-payment",
        "name": "Validating payment",
        "description": "Init: User confirms that they have completed payment (and uploaded PoP)\nInit: Payment is not yet validated manually or automatically",
        "created_at": "2018-02-16T09:00:00.000Z",
        "updated_at": "2018-02-16T09:00:00.000Z"
    },
    {
        "id": 3,
        "tag": "pay-validated",
        "name": "Payment validated",
        "description": "Init: Payment validated either automatically or manually\nAction: System confirms payment to airline",
        "created_at": "2018-02-17T09:00:00.000Z",
        "updated_at": "2018-02-17T09:00:00.000Z"
    },
    {
        "id": 4,
        "tag": "eticket-issued",
        "name": "E-ticket issued",
        "description": "Init: e-ticket is received from airline and sent to customer via e-mail and app",
        "created_at": "2018-02-18T09:00:00.000Z",
        "updated_at": "2018-02-18T09:00:00.000Z"
    },
    {
        "id": 5,
        "tag": "pay-timeout",
        "name": "Payment timed-out",
        "description": "Initial state: customer hasn’t completed payment but runs out of time\nAction (WL-booking): cancel user’s booking (because payment time limit from airline might be longer)",
        "created_at": "2018-02-19T09:00:00.000Z",
        "updated_at": "2018-02-19T09:00:00.000Z"
    }
]
```

This endpoint retrieves all booking status types.

### HTTP Request

`GET http://example.com/api/v1/booking_status_types`

## Get a Specific BookingStatusType

> returns JSON structured like this:

```json
{
    "id": 1,
    "tag": "wait-payment",
    "name": "Waiting for payment",
    "description": "Init (normal booking): User books flights\nInit (WL-booking): After user confirms to pay, add 7 more minutes to the countdown ",
    "created_at": "2018-02-15T09:00:00.000Z",
    "updated_at": "2018-02-15T09:00:00.000Z"
}
```

This endpoint retrieves a specific booking status type.

<aside class="notice">This includes the relations: [BookingStatusType Relation].</aside>

### HTTP Request

`GET http://example.com/booking_status_types/<tag>`

### URL Parameters

Parameter | Description
--------- | -----------
tag | The tag of the booking status type to retrieve

## Delete a Specific BookingStatusType

> The above command returns JSON structured like this:

```json
{
    "tag": "new-bst",
    "message": "BookingStatusType is deleted"
}
```

This endpoint deletes a specific booking status type.

### HTTP Request

`DELETE http://example.com/booking_status_types/<tag>`

### URL Parameters

Parameter | Description
--------- | -----------
tag | The tag of the booking status type to delete

## Create a BookingStatusType

```json
{
  "tag": "new-bst",
  "name": "bst",
  "description": "description"
}
```

> The above request returns JSON structured like this:

```json
{
    "id": 6,
    "tag": "new-bst",
    "name": "bst",
    "description": "description",
    "created_at": "2018-03-01T07:08:59.447Z",
    "updated_at": "2018-03-01T07:08:59.447Z"
}
```

This endpoint creates a booking status type entry.

### HTTP Request

`POST http://example.com/booking_status_types`

