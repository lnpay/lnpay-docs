---
description: Get the wallet object which includes current balance. See Access Keys
---

# Retrieve Wallet

{% api-method method="get" host="https://api.lnpay.co/" path="v1/wallet/:wallet\_key" %}
{% api-method-summary %}
GetWallet
{% endapi-method-summary %}

{% api-method-description %}
Returns info about the wallet, including balance.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="wallet\_key" type="string" required=true %}
wal\_ for server side  
wakr\_ for client side
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns: `Wallet`
{% endapi-method-response-example-description %}

```
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
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
See the [Access Keys](../get-started/access-keys.md#permission-breakdown) section on how to define `wallet_key`
{% endhint %}

{% tabs %}
{% tab title="cURL" %}
```text
curl -u sak_XXXXXXX: \
https://api.lnpay.co/v1/wallet/wal_XXXXXX
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
const lnpay = LNPay({
  secretKey: 'sak_XXXXX'
});

const balance = await lnpay.getBalance();
console.log(balance);
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

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_XXXXXXX');

let myWallet = new LNPayWallet('wakr_XXXXXX');
myWallet.getInfo(function(result) {
      console.log('Balance:' + result.balance);
    }
);
```
{% endtab %}
{% endtabs %}

