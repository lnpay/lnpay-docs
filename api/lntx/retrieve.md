---
description: >-
  Retrieve a LN transaction (invoice). This is usually used to see if a
  transaction has been settled or not, and for how much
---

# Get Invoice Status

{% swagger baseUrl="https://api.lnpay.co" path="/v1/lntx/:lntx_id" method="get" summary="GetLnTxObject" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
e.g. lntx_82yveCX2Wn0EkkdyzvyBv
{% endswagger-parameter %}

{% swagger-response status="200" description="The LnTx Object" %}
```javascript
{
    "id":"lntx_82yveCX2Wn0EkkdyzvyBv",
    "created_at":1577657602,
    "ln_node_id":"lnod_2s4yfYA",
    "dest_pubkey":"02c16cca44562b590dd279c942200bdccfd4f990c3a69fad620c10ef2f8228eaff",
    "payment_request":"lnbc50n1p0qjf84pp5f70yqjjvu0z0esf7hksnca44d8j440mk5743qv70ku6jy9ewj8eqdpz23jhxapqd9h8vmmfvdjjqen0wgsxgmmrwvxqyz5vqcqzyssp583w0tugt4scyek2dat72p389lau0j8u9t5qnep29y0c32hyfn8rqrzjqt0pr36g7ke9elfvaqq3wmfey6laun0z8v0lg0nf9fdhdncxsp0y5zxkp5qqnsgqqqqqqquyqqqqqksqrc9qy9qsqzmvy83s8np7yrlqs98ge90tj3wwhfawjtq3cewv4vavmq0p5c4anhkm2aeyzjcvycttfgzwtak7nrrk6e3m3td8g4t8ha06uzzare4cqqne839",
    "r_hash_decoded":"4f9e404a4ce3c4fcc13ebda13c76b569e55abf76a7ab1033cfb73522172e91f2",
    "memo":"Test invoice for docs",
    "description_hash":null,
    "num_satoshis":5,
    "fee_msat":0,
    "expiry":86400,
    "expires_at":1577744002,
    "payment_preimage":"6631394e526f35325135563854574f316651513330527a6e4e47315630795147662f7066466e4276664a773d",
    "settled":1,
    "settled_at":1577657602,
    "is_keysend":null,
    "custom_records":null,
    "passThru":null
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="curl" %}
```
curl -u sak_XXX: \
https://api.lnpay.co/v1/lntx/lntx_82yveCX2Wn0EkkdyzvyBv
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_XXXXX');

let lntx_id = "lntx_82yveCX2Wn0EkkdyzvyBv";
let lntx = new LNPayLnTx(lntx_id);
lntx.getInfo(function(result) {
    console.log("Is Settled" + result.settled);
  }
);
```
{% endtab %}

{% tab title="Python" %}
```python
lnpay_py.initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp')
from lnpay_py.wallet import LNPayWallet

lntx_id = 'lntx_82yveCX2Wn0EkkdyzvyBv'
ln_tx = LNPayLnTx(lntx_id)
invoice_result = ln_tx.get_info()
print(invoice_result)
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
const lnpay = LNPay({
  secretKey: 'sak_XXXXX'
});

const getInvoice = await lnpay.getInvoice({
  id: 'lntx_82yveCX2Wn0EkkdyzvyBv',
});
```
{% endtab %}
{% endtabs %}

{% hint style="success" %}
Slim down the response size by appending the fields you want as query parameters

```
$ curl -u sak_XXXX: \
https://api.lnpay.co/v1/lntx/lntx_82yveCX2Wn0EkkdyzvyBv?fields=settled,num_satoshis
```
{% endhint %}

