# List Wallets

{% hint style="info" %}
This endpoint is only available to the **Secret Access Key \(`sak_`\)**
{% endhint %}

{% api-method method="get" host="https://api.lnpay.co/" path="v1/wallets" %}
{% api-method-summary %}
ListWallets
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Array of wallets
{% endapi-method-response-example-description %}

```
[
    {
        "id":"wal_czDztN5eJ4r5sJ",
        "created_at":1582461859,
        "updated_at":1618419816,
        "user_label":"My Postman Collection Wallet",
        "balance":74, #Sats
        "balance_msat":null,
        "statusType":{
            "type":"wallet",
            "name":"active",
            "display_name":"Active"
        },
        "walletType":{
            "name":"generic_wallet",
            "display_name":"Generic Wallet"
        }
    },
    {
        "id":"wal_czDztN5eJ4r5sJ",
        "created_at":1582461859,
        "updated_at":1618419816,
        "user_label":"My Postman Collection Wallet",
        "balance":74, #Sats
        "balance_msat":null,
        "statusType":{
            "type":"wallet",
            "name":"active",
            "display_name":"Active"
        },
        "walletType":{
            "name":"generic_wallet",
            "display_name":"Generic Wallet"
        }
    }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

