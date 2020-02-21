# Generate Invoice

{% api-method method="post" host="https://lnpay.co/v1/wallet/" path=":wallet\_access\_key/invoice" %}
{% api-method-summary %}
PostWalletInvoice
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="wallet\_access\_key" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="description\_hash" type="string" required=false %}
base64 encoded hash of payment. If this is provided, memo will be ignored.
{% endapi-method-parameter %}

{% api-method-parameter name="memo" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="expiry" type="integer" required=false %}
seconds, defaults to 86400 \(1 day\)
{% endapi-method-parameter %}

{% api-method-parameter name="num\_satoshis" type="integer" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
This returns an LnTx object 
{% endapi-method-response-example-description %}

{% code title="\# LnTx Object" %}
```
{
    "id": "lntx_UlXwgqNd2tl41ZrnWPlx7s6w",
    "created_at": 1582297054,
    "dest_pubkey": "033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
    "payment_request": "lnbc200n1p0ylm77pp5384pxkzd5m536nluwf2364r2qmsnh7kzyj0wrv3urze5vllmfmxqdp623jhxapqd9h8vmmfvdjjqenjdakjq5r0wd6x6ctwyppk7mrvv43hg6t0dccqzpgxqyz5vqsp56f338cr57djg5zsagrnxd80krpnqny0k3wldk5ctruwgftk9stnq9qy9qsqju8kfgplphd0jum5z8xs4fdjrv2wfrgang2pr5zvan3psfu0ff7krqgwfmp4sywyz97lp0lrlezyvqxhjtvy0gjz0ld5g4ha2udjurqqy2eny5",
    "r_hash_decoded": "89ea13584da6e91d4ffc72551d546a06e13bfac2249ee1b23c18b3467ffb4ecc",
    "memo": "Test invoice from Postman Collection",
    "description_hash": null,
    "num_satoshis": 20,
    "expiry": 86400,
    "expires_at": 1582383454,
    "payment_preimage": null,
    "settled": 0,
    "settled_at": null,
    "is_keysend": null,
    "custom_records": null
}
```
{% endcode %}
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
-d '{"num_satoshis":20, "memo":"Test invoice from the docs"}' \
https://lnpay.co/v1/wallet/wi_skllxCQI7yurKi0NCCTc0wwO/invoice

# Note we are using the "invoice" access_key as denoted by "wi_"
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp');

let myWallet = new LNPayWallet('wi_skllxCQI7yurKi0NCCTc0wwO');
let invoiceParams = {"num_satoshis":2,"memo":"Tester"};
myWallet.createInvoice(invoiceParams,
    function(result) {
      console.log(result);
    }
);
```
{% endtab %}

{% tab title="Python" %}
```python
lnpay_py.initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp')
from lnpay_py.wallet import LNPayWallet

my_wallet = LNPayWallet('wi_skllxCQI7yurKi0NCCTc0wwO')
invoice_params = {
    'num_satoshis': 2,
    'memo': 'Tester'
}
invoice = my_wallet.create_invoice(invoice_params)
print(invoice)
```
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
The `Content-Type: application/json` header is required for all `POST` request with a JSON body!
{% endhint %}

