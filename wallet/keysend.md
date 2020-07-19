---
description: Initiate a keysend payment from your wallet to a destination pubkey
---

# Keysend

{% api-method method="post" host="https://lnpay.co" path="/v1/wallet/:access\_key/keysend" %}
{% api-method-summary %}
PostWalletKeysend
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="wallet\_access\_key" type="string" %}
Access key with withdraw permission \(e.g. waka\_ or waki\_\)
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="dest\_pubkey" type="string" required=true %}
Pubkey of destination node
{% endapi-method-parameter %}

{% api-method-parameter name="num\_satoshis" type="integer" required=true %}
satoshis
{% endapi-method-parameter %}

{% api-method-parameter name="custom\_records" type="object" required=false %}
key:value pairs to be sent in the onion. key must be an integer greater than 65536. Too many values here will break things.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{    "name": "Cake's name",    "recipe": "Cake's recipe name",    "cake": "Binary cake"}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{    "message": "Ain't no cake like that."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
See this LND release for more information about keysend: [https://github.com/lightningnetwork/lnd/releases/tag/v0.9.0-beta](https://github.com/lightningnetwork/lnd/releases/tag/v0.9.0-beta)
{% endhint %}

{% tabs %}
{% tab title="curl" %}
```text
$ curl -u pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
-H "Content-Type: application/json" \
-X POST \
-d '{"dest_pubkey":"033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500","num_satoshis":2}' \
https://lnpay.co/v1/wallet/waka_kqvaiFFl4Tjq4rgAXlwsu6/keysend

# Note we are using the "admin" access_key as denoted by "wa_"
```
{% endtab %}
{% endtabs %}

