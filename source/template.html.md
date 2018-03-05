# Models
## Get All Models

> returns JSON structured like this:

```json
```

This endpoint retrieves all models.

### HTTP Request

`GET http://35.224.189.34:3000/api/v1/models`

## Get a Specific Model

> returns JSON structured like this:

```json
```

This endpoint retrieves a specific model.

<aside class="notice">This includes the relations: [Model Relation].</aside>

### HTTP Request

`GET http://35.224.189.34:3000/models/<ID>`

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

`DELETE http://35.224.189.34:3000/models/<ID>`

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

`POST http://35.224.189.34:3000/models`
