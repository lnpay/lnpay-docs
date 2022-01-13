# List Wallets

{% hint style="info" %}
This endpoint is only available to the **Secret Access Key (`sak_`)**
{% endhint %}

{% swagger baseUrl="https://api.lnpay.co/" path="v1/wallets" method="get" summary="ListWallets" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-response status="200" description="Array of wallets" %}
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
        },
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
{% endswagger-response %}
{% endswagger %}
