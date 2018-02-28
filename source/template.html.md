# Models
## Get All Models

> returns JSON structured like this:

```json
```

This endpoint retrieves all models.

### HTTP Request

`GET http://example.com/api/v1/models`

## Get a Specific Model

> returns JSON structured like this:

```json
```

This endpoint retrieves a specific model.

<aside class="notice">This includes the relations: [Model Relation].</aside>

### HTTP Request

`GET http://example.com/models/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the model to retrieve

## Delete a Specific Model

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "message": "Model is deleted"
}
```

This endpoint deletes a specific model.

### HTTP Request

`DELETE http://example.com/models/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the model to delete

## Create a Model

```json
```

> The above request returns JSON structured like this:

```json
```

This endpoint creates a model entry.

### HTTP Request

`POST http://example.com/models`
