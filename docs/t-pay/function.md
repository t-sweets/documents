## 機能一覧（仮）
- EndUserApp API
    - register
        - 新規登録
    - login
        - ログイン
    - getAccount
        - ユーザ名の表示
        - 残高の表示
    - getTransactionHistory
        - 決済・チャージ・送金履歴の表示
    - getDepositHistory
        - チャージ履歴の表示
    - getCheckoutHistory
        - 購入履歴の表示
    - getTransferHistory
        - 送金履歴の表示
    - checkoutByQR
        - QRコード決済
    - transfer
        - 個人間送金
    - getInvoice
        - 請求一覧の表示
    - registerCard
        - FeliCaカードの登録
    - modCards
        - 登録カードの管理

- Regi API
    - checkoutByCard
        - FeliCaカード決済
    - checkoutByQR
        - QRコード決済
    - Deposit
        - ユーザ残高のチャージ
    - cancelCheckoutRequest
        - 決済のキャンセル請求
        - ユーザの同意(カード情報又はQR)が必要

- BackOffice API
    - getAllCheckoutHistory
        - すべての決済履歴の表示

- AdminDashboard API
