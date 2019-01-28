# Group Checkout
決済API

## Checkouts [/checkout/]
### List Checkout [GET]
+ Response 200 (application/json)

    + Headers

    + Body

        [
            {
                "id": "1af5b8de2eed4054b0f65910a67647f2",
                "to": "Sweets",
                "from": "tagoken",
                "amount": 1000,
                "payment_method": 1,
                "new_balance": 3000
                "status": "confirm"
            },
            {
                "id": "saf5b8de2ded4054b0f65910f67647f2",
                "to": "Sweets",
                "from": "tagoken",
                "amount": 1000,
                "payment_method": 1,
                "new_balance": 3000
                "status": "pending"
            },
            {
                "id": "daf5b8de2ded4054b0f65910a67647f2",
                "to": "Sweets",
                "from": "tagoken",
                "amount": 1000,
                "payment_method": 1,
                "new_balance": 3000
                "status": "canceled"
            },
        ]

### Create Checkout [POST]
+ Request with FeliCaCard (application/json)

    + Headers

    + Body

            {
                "to": "Sweets",
                "amount": 1000,
                "payment_method": 1,
                "idm": "0x00000000000000000"
            }

+ Response 201 (application/json)

    + Headers

    + Body

            {
                "id": "daf5b8de2ded4054b0f65910a67647f2",
                "to": "Sweets",
                "amount": 1000,
                "payment_method": 1,
                "status": "confirm"
            },

+ Response 400 (application/json)
残高不足

    + Headers

    + Body

            {
                "message": "Insufficient funds"
            },

## Checkout [/checkout/{id}/]
+ Parameters

    + id: `1af5b8de2eed4054b0f65910a67647f2` (required, string) - Checkout ID

### Get Checkout [GET]
取引詳細の表示
### Delete Checkout [DELETE]
取引のキャンセル請求
