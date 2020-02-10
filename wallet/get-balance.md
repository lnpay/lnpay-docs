---
description: Get the wallet object which includes current balance
---

# Get Balance

{% api-method method="get" host="https://lnpay.co/v1/wallet/" path=":wallet\_access\_key" %}
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
  "id": "w_pXHvKoKeKfrv",
  "created_at": 1577600922,
  "updated_at": 1577600922,
  "user_label": "Wallet for ATM",
  "balance": 1000,
  "statusType": {
        "id": 200,
        "type": "wallet",
        "name": "active",
        "display_name": "Active"
    },
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
https://lnpay.co/v1/wallet/wr_3YgsKHplFSyhzBKNVr8tohO

# We are using the "read" access key in this instance as denoted by the "wr_"
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp');

let myWallet = new LNPayWallet('wr_3YgsKHplFSyhzBKNVr8tohO');
myWallet.getInfo(function(result) {
      console.log('Balance:' + result.balance);
    }
);
```
{% endtab %}

{% tab title="Python" %}
```python
lnpay_py.initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp')
my_wallet = LNPayWallet('wr_3YgsKHplFSyhzBKNVr8tohO')

info = my_wallet.get_info()
print(info)
```
{% endtab %}
{% endtabs %}



