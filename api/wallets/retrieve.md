---
description: Get the wallet object which includes current balance. See Access Keys
---

# Retrieve Wallet

{% swagger baseUrl="https://api.lnpay.co/" path="v1/wallet/:wallet_key" method="get" summary="GetWallet" %}
{% swagger-description %}
Returns info about the wallet, including balance.
{% endswagger-description %}

{% swagger-parameter in="path" name="wallet_key" type="string" %}
wal_ for server side

\


wakr_ for client side
{% endswagger-parameter %}

{% swagger-response status="200" description="Returns: Wallet" %}
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
    },
    "default_lnurlpay_id": "lnurlp_6Xh2hELFFqSlKEHCbF"
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
See the [Access Keys](../get-started/access-keys.md#permission-breakdown) section on how to define `wallet_key`
{% endhint %}

{% tabs %}
{% tab title="cURL" %}
```
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
