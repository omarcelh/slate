# Payments
## Make pending payment

```json
{
	"name": "test",
	"amount": 400000,
	"invoice": "AVIZD4XBLG",
	"payment_method": "vabni",
	"email": "regtest.dhezign@gmail.com",
	"user_id": "5",
	"phone_number": 6212346578,
	"pay_date": "20180102210044"
}
```

> The above request returns JSON structured like this:

```json
{
    "status_code": "00",
    "status_desc": "Success with the existing payment code",
    "payment_code": "8029000000000541",
    "redirect_url": ""
}
```

This endpoint makes pending payment.

### HTTP Request

`POST http://35.224.189.34:3000/payments/make_pending_payment`

## Check pending payment

```json
{
	"name": "test",
	"amount": 400000,
	"invoice": "AVIZD4XBLG",
	"payment_method": "vabni",
	"email": "regtest.dhezign@gmail.com",
	"user_id": "5",
	"phone_number": 6212346578,
	"pay_date": "20180102210044"
}
```

> The above request returns JSON structured like this:

```json
{
    "status_code": "205",
    "status_desc": "Order Unpaid",
    "payment_code": "8029000000000541",
    "redirect_url": ""
}
```

This endpoint checks pending payment.

### HTTP Request

`POST http://35.224.189.34:3000/payments/checks_pending_payment`

## Make direct payment

```json
{
	"name": "test",
	"amount": 400000,
	"invoice": "AVIZD7XBLG",
	"payment_method": "mandiriclickpay",
	"email": "regtest.dhezign@gmail.com",
	"user_id": "6",
	"phone_number": 6212346578,
	"debit_card": 4616999900000028,
	"token": "000000"
}
```

> The above request returns JSON structured like this:

```json
{
    "status_code": "00",
    "status_desc": "Success",
    "payment_code": "184DE4813001"
}
```

This endpoint makes direct payment.

### HTTP Request

`POST http://35.224.189.34:3000/payments/make_direct_payment`

## Make payment page

```json
{
	"name": "test",
	"amount": 400000,
	"invoice": "AVIZD6XBLG",
	"payment_method": "cc",
	"email": "regtest.dhezign@gmail.com",
	"user_id": "6",
	"phone_number": 6212346578
}
```

> The above request returns JSON structured like this:

```json
{
    "status_code": "00",
    "status_desc": "Success",
    "redirect_url": "https://sandbox.finpay.co.id/servicescode/api/redirect.php?access=265d7384b62e34a2f8e136742f49f6c83b6ea6878c3a4e1129fdb81a92d6f946"
}
```

This endpoint makes payment page.

### HTTP Request

`POST http://35.224.189.34:3000/payments/make_payment_page`