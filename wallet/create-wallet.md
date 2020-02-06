# Create Wallet

{% api-method method="post" host="https://lnpay.co/v1/wallet" path="" %}
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
    "id":"w_Noii2dJQmJjXdq",
    "created_at":1577985279,
    "updated_at":1577985279,
    "user_label":"Tester API Wallet",
    "balance":0,
    "statusType": {
        "id": 200,
        "type": "wallet",
        "name": "active",
        "display_name": "Active"
    },
    "access_keys":{
        "Wallet Admin":[
            "wa_JEa9ZqCRT6oD4FsMgwWmqf1"
        ],
        "Wallet Invoice":[
            "wi_u7SjGDIG9a2EYTv4HyvXz3SW"
        ],
        "Wallet Read":[
            "wr_fWQd82MvofmBRrdT2x5YkGJ2"
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
https://lnpay.co/v1/wallet
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
{% endtabs %}

{% hint style="warning" %}
The access keys generated will NOT be available via the API again! You must save and store them
{% endhint %}

