# Generate Invoice

{% api-method method="post" host="https://lnpay.co/v1/user/wallet/" path=":access\_key/invoice" %}
{% api-method-summary %}
PostWalletInvoice
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="access\_key" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
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

{% code title="LnTx Object" %}
```
{
    "id":"lntx_RFbu0YosFoIuJc7S6qMg0L9",
    "created_at":1577655829,
    "updated_at":1577655829,
    "dest_pubkey":"033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
    "payment_request":"lnbc200n1p0qj8s4pp525lkfynvsxlyl5vys8v4xv840swspylfk3v5l95gne3ms77vc9tsdp223jhxapqd9h8vmmfvdjjqenjdakjqargv5sxgmmrwvcqzpgxqyz5vq48ud7ha9rnsnadkhcsv38aadh3yrvuvv3kl9xv7wp0w3hqqyllvjkdzm2awcsdw9l5zkkkqu2hy0shunjdrdg4r8h8f59e2720885jgqwrqyt8",
    "r_hash_decoded":"553f64926c81be4fd18481d95330f57c1d0093e9b4594f96889e63b87bccc157",
    "memo":"Test invoice from the docs",
    "num_satoshis":20,
    "expiry":86400,
    "expires_at":1577742229,
    "payment_preimage":null,
    "settled":0,
    "settled_at":null
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
$ curl -u yg20O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
-H "Content-Type: application/json" \
-X POST \
-d '{"num_satoshis":20, "memo":"Test invoice from the docs"}' \
https://lnpay.co/v1/user/wallet/wi_skllxCQI7yurKi0NCCTc0wwO/invoice

# Note we are using the "invoice" access_key as denoted by "wi_"
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
The `Content-Type: application/json` header is required for all `POST` request with a body!
{% endhint %}

