---
description: Get the wallet object which includes current balance
---

# Get Balance

{% api-method method="get" host="https://api.lnpay.co/v1/wallet/" path=":wallet\_access\_key" %}
{% api-method-summary %}
GetWallet
{% endapi-method-summary %}

{% api-method-description %}
Returns info about the wallet, including balance
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="wallet\_access\_key" type="string" required=true %}
Wallet Access Key \(WAK\)
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "id":"wal_czDztN5eJ4r5sJ",
    "created_at":1582461859,
    "updated_at":1618419816,
    "user_label":"My Postman Collection Wallet",
    "balance":74,
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
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="curl" %}
```text
$ curl -u sak_XXXXXXX: \
https://api.lnpay.co/v1/wallet/wakr_XXXXX

# We are using the "read" access key in this instance as denoted by the "wakr_"
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('sak_XXXXXXX');

let myWallet = new LNPayWallet('wr_XXXXXX');
myWallet.getInfo(function(result) {
      console.log('Balance:' + result.balance);
    }
);
```
{% endtab %}

{% tab title="Python" %}
```python
lnpay_py.initialize('sak_XXXXXXX')
my_wallet = LNPayWallet('wr_XXXXXXX')

info = my_wallet.get_info()
print(info)
```
{% endtab %}
{% endtabs %}



