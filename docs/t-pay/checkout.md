# Group Checkout
決済API

## Checkouts [/checkout/]
### Create Checkout [POST]
+ Request with FeliCaCard (application/json)

    + Headers

    + Body

        {
            "amount": 1000,
            "merchant_id": "01D45RXPW21ENE6MA8TPBCRC5C",
            "payment_method": 1,
            "idm": "0x00000000000000"
        }

+ Response 201 (application/json)

    + Headers

    + Body

        {
            "id": "01D4687JCYY3ES4XRS8NM1TTDW",
            "created_time": "2019-02-21T05:05:57.285111+09:00",
            "amount": 1000,
            "merchant": "Sweets１号店"
        }

+ Response 400 (application/json)
残高不足

    + Headers

    + Body

        {
            "detail": "Insufficient funds"
        }

+ Response 400 (application/json)
IDMに紐づくユーザが見つからなかった

    + Headers

    + Body

        {
            "detail": "User auth failed"
        }

+ Response 400 (application/json)
認証ユーザは指定された加盟店で決済を行う権限がない

    + Headers

    + Body

        {
            "detail": "Merchant not in auth user"
        }
