---
description: >-
  Retrieve a LN transaction (invoice). This is usually used to see if a
  transaction has been settled or not, and for how much
---

# Get Invoice Status

{% api-method method="get" host="https://api.lnpay.co" path="/v1/lntx/:lntx\_id" %}
{% api-method-summary %}
GetLnTxObject
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
e.g. lntx\_82yveCX2Wn0EkkdyzvyBv
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
The LnTx Object
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="curl" %}
```text
$ curl -u pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
https://api.lnpay.co/v1/lntx/lntx_82yveCX2Wn0EkkdyzvyBv
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp');

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
{% endtabs %}

{% hint style="success" %}
Slim down the response size by appending the fields you want as query parameters

```text
$ curl -u pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
https://api.lnpay.co/v1/lntx/lntx_82yveCX2Wn0EkkdyzvyBv?fields=settled,num_satoshis
```
{% endhint %}



