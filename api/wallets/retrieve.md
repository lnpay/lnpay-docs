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
    "defaultLnurlpay": {
        "id": "lnurlp_6Xh2hELFFqSlKEHCbF",
        "created_at": 1642013336,
        "updated_at": 1642013336,
        "user_label": "Base lnurl-pay link",
        "lnurl_encoded": "LNURL1DP68GUP69UHKCMNSV9UJUMR0VDSKCW3CXYCNZTMKXYHHWCTVD3JHGTMHV94KCUZLX3TXC7NYWF5KYN34VE2YZKR42E3KJ6E4V4XKCNP0D3H82UNVWQHKCMN4WFK8QHEKTP5RY6Z9F3RYVU2ND3952JZRVFRQWUZJNJ",
        "lnurl_decoded": "https://cloud.lnpay.co/v1/wallet/waklp_4VlzdribN5fTAXuVcik5eMlL/lnurlp/lnurlp_6Xh2hELFFqSlKEHCbF",
        "lnurlp_minSendable_msat": 1000,
        "lnurlp_maxSendable_msat": 10000000,
        "lnurlp_short_desc": "LNURL PAY (via LNPay.co)",
        "statusType": {
            "type": "lnurl",
            "name": "lnurl_active",
            "display_name": "LNURL Active"
        }
    }
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
