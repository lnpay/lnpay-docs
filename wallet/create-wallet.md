# Create Wallet

{% api-method method="post" host="https://api.lnpay.co/v1/wallet" path="" %}
{% api-method-summary %}
PostCreateWallet
{% endapi-method-summary %}

{% api-method-description %}
Create a new wallet and corresponding access keys
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="user\_label" type="string" required=true %}
An internal identifier for this wallet
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Wallet Created
{% endapi-method-response-example-description %}

```
{
    "id": "wal_czDztN5eJ4r5sJ",
    "created_at": 1582461859,
    "updated_at": 1582461859,
    "user_label": "My Postman Collection Wallet",
    "balance": 0,
    "statusType": {
        "type": "wallet",
        "name": "active",
        "display_name": "Active"
    },
    "access_keys": {
        "Wallet Admin": [
            "waka_kqvaiFFl4Tjq4rgAXlwsu6"
        ],
        "Wallet Invoice": [
            "waki_Q2XHBIfEAN33mLlwdYvusN6Q"
        ],
        "Wallet Read": [
            "wakr_wIdkxqZqkRJd6MhWlsoH1yi"
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="curl" %}
```text
$ curl -u pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
-H "Content-Type: application/json" \
-X POST \
-d '{"user_label":"Tester API Wallet"}' \
https://api.lnpay.co/v1/wallet
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp');

let walletParams = {"user_label":"My wallet"};
LNPay.createWallet(walletParams,
    function(result) {
      console.log(result);
    }
);
```
{% endtab %}

{% tab title="Python" %}
```python
lnpay_py.initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp')

wallet_params = {
    'user_label': 'My wallet'
}
new_wallet = lnpay_py.create_wallet(wallet_params)
print(new_wallet)
```
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
The access keys generated will NOT be available via the API again! You must save and store them
{% endhint %}



