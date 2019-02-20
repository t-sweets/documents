# Data Structures

## AccountData
+ id: 1af5b8de2eed4054b0f65910a67647f2 (required, string) - ユーザID
+ username: tagoken (required) - ユーザ名
+ display_name: たごけん - 表示名
+ balance: 3000 (number) - ユーザ残高

## AccountList (array)
+ (AccountData)

# Group Account
Account API

## Account Profile [/accounts/profile/]
### Get Profile [GET]
認証ユーザのアカウント情報を表示する

+ Request ()

    + Headers
        Authorization: Token eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9...

+ Response 200 (application/json)

    + Body
        {
            "username": "tagoken",
            "email": "tagoken@example.com",
            "display_name": "",
            "balance": "0"
        }

### Update Profile [PATCH]
認証ユーザのアカウント情報を更新する

+ Request with update display_name (application/json)

    + Headers
        Authorization: Token eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9...

    + Body

            {
                "display_name": "Tagotarou1"
            }

+ Response 200 (application/json)

    + Body
        {
            "username": "tagoken",
            "email": "tagoken@example.com",
            "display_name": "",
            "balance": "0"
        }

### Delete My Account [DELETE]
認証ユーザのアカウント情報を削除する

+ Request ()

    + Headers
        Authorization: Token eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9...

+ Response 204


## Account Login [/accounts/login/]
### Login [POST]
ログイン

+ Request (application/json)

    + Body

            {
                "username": "tagoken",
                "password": "password"
            }

+ Response 200 (application/json)

    + Body
        {
            "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ..."
        }

+ Response 400 (application/json)

    + Body
        {
            "non_field_errors": [
                "提供された認証情報でログインできません。"
            ]
        }

## Account Register [/accounts/register/]
### Register [POST]
新規登録を行う

+ Request (application/json)

    + Body

        {
            "username": "tagoken",
            "email": "tagoken@example.com",
            "display_name": "たごけん",
            "password": "password"
        }

+ Response 201

    + Body

        {
            "username": "tagoken",
            "email": "tagoken@example.com"
            "display_name": "たごけん",
            "balance": "0"
        }

## Register IDm [/accounts/register_idm/]
### Register IDm [POST]
IDMの登録

+ Request (application/json)

    + Headers
        Authorization: Token eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9...

    + Body

        {
            "idm": "0x00000000000000",
            "name": "Suica Card1"
        }

+ Response 201

    + Body

        {
            "name": "Suica Card1"
        }

## Account Chackouts [/accounts/checkouts/]
### Account Chackouts [GET]
認証ユーザの決済履歴の表示

+ Request (application/json)

    + Headers
        Authorization: Token eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9...

+ Response 200

    + Body

        [
            {
                "id": "01D45RYR8CSNRP5M4GGH5S84SR",
                "created_time": "2019-02-21T00:38:59.730069+09:00",
                "amount": 200,
                "merchant": "スイーツイチゴウテン"
            },
            {
                "id": "01D45TREPHVR01NMAK6CBE1G11",
                "created_time": "2019-02-21T01:10:30.486667+09:00",
                "amount": 455,
                "merchant": "Sweets1gouten"
            }
        ]
