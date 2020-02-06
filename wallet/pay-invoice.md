---
description: Generate an LN invoice from the specified wallet
---

# Pay Invoice

{% api-method method="post" host="https://lnpay.co/v1/wallet/" path=":access\_key/withdraw" %}
{% api-method-summary %}
PostWalletSend
{% endapi-method-summary %}

{% api-method-description %}
Pay an invoice from this wallet
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="wallet\_access\_key" type="string" required=true %}
access key
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="payment\_request" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="lnPayParams" type="array" required=false %}
JSON array of custom data to pass thru
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Payment successfully executed
{% endapi-method-response-example-description %}

```
{
    "id":"wtx_JOhQFFI826owtE51AfFC975c",
    "created_at":1577657602,
    "wallet_id":"w_hkjS9r6mTYeABc",
    "wtxType": {
        "id": 20,
        "layer": "ln",
        "name": "ln_withdrawal",
        "display_name": "LN Withdrawal"
    },
    "num_satoshis":-5,
    "user_label":"Test invoice for docs",
    "lnTx":{
        "id":"lntx_82yveCX2Wn0EkkdyzvyBv",
        "created_at":1577657602,
        "updated_at":1577657602,
        "dest_pubkey":"02c16cca44562b590dd279c942200bdccfd4f990c3a69fad620c10ef2f8228eaff",
        "payment_request":"lnbc50n1p0qjf84pp5f70yqjjvu0z0esf7hksnca44d8j440mk5743qv70ku6jy9ewj8eqdpz23jhxapqd9h8vmmfvdjjqen0wgsxgmmrwvxqyz5vqcqzyssp583w0tugt4scyek2dat72p389lau0j8u9t5qnep29y0c32hyfn8rqrzjqt0pr36g7ke9elfvaqq3wmfey6laun0z8v0lg0nf9fdhdncxsp0y5zxkp5qqnsgqqqqqqquyqqqqqksqrc9qy9qsqzmvy83s8np7yrlqs98ge90tj3wwhfawjtq3cewv4vavmq0p5c4anhkm2aeyzjcvycttfgzwtak7nrrk6e3m3td8g4t8ha06uzzare4cqqne839",
        "r_hash_decoded":"4f9e404a4ce3c4fcc13ebda13c76b569e55abf76a7ab1033cfb73522172e91f2",
        "memo":"Test invoice for docs",
        "num_satoshis":5,
        "expiry":86400,
        "expires_at":1577744002,
        "payment_preimage":"6631394e526f35325135563854574f316651513330527a6e4e47315630795147662f7066466e4276664a773d",
        "settled":1,
        "settled_at":1577657602
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Response directly from node if node error
{% endapi-method-response-example-description %}

```
{
    "name":"Bad Request",
    "message":"invoice is already paid",
    "code":0,
    "status":400
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
-d '{"payment_request":"lnbc50n1p0qjf84p..."}' \
https://lnpay.co/v1/wallet/wa_Opnn4kGOGBMnfCLFXtsDnjTb/withdraw

# Note we are using the "admin" access_key as denoted by "wa_"
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp');

let myWallet = new LNPayWallet(walletAccessKey);
let invoiceParams = {"payment_request":"lnbc1111..."};
myWallet.payInvoice(invoiceParams,
    function(result) {
      console.log(result);
    }
);
```
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
The `Content-Type: application/json` header is required for all `POST` request with a JSON body!
{% endhint %}

