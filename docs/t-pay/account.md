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

## Account List [/accounts/]
### Get Accounts [GET]
Account一覧を取得する

+ Response 200 (application/json)

    + Headers

    + Body
        [
            {
                "id": "1af5b8de2eed4054b0f65910a67647f2",
                "username": "tagoken",
                "display_name": "たごけん",
                "balance": 3000
            },
            {
                "id": "1af5b8de2eed4054b0f65910a67647f3",
                "username": "hideo",
                "display_name": "ひでお",
                "balance": 5000
            },
            {
                "id": "1af5b8de2eed4054b0s65910a6d647f3",
                "username": "kena",
                "display_name": "けんえー",
                "balance": 10000
            },
        ]

## Account [/accounts/{id}/]

+ Parameters

    + id: `1af5b8de2eed4054b0f65910a67647f2` (required, string) - The Account ID

### Get Account [GET]
Account情報を取得する

+ Response 200 (application/json)

    + Headers

    + Attributes (AccountData)

+ Response 404 (application/json)

    + Headers

    + Body

            {
                "error": "Account not found"
            }

### Update Account [PUT]
Accountの更新

+ Request update display_name (application/json)

    + Body

            {
                "display_name": "へんたいまじん１号"
            }

+ Response 200 (application/json)

    + Headers

    + Attributes (AccountData)

+ Response 404 (application/json)

    + Headers

    + Body

            {
                "error": "Account not found"
            }

### Delete Account [DELETE]
Accountの削除

+ Response 204

+ Response 404 (application/json)

    + Headers

    + Body

            {
                "error": "Account not found"
            }

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

    + Headers
        token: "550e8400e29b41d4a716446655440000"

    + Attributes (AccountData)

+ Response 404 (application/json)

    + Headers

    + Body

            {
                "error": "Account not found"
            }

## Account Register [/accounts/register/]
### Register [POST]
新規登録を行う

+ Request (application/json)

    + Body

            {
                "username": "tagoken",
                "display_name": "たごけん",
                "password": "password",
                "confirm_password": "password"
            }

+ Response 201

    + Attributes (AccountData)
