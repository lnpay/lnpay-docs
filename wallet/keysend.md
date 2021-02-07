---
description: Initiate a keysend payment from your wallet to a destination pubkey
---

# Keysend \(New!\)

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
{% api-method-parameter name="passThru" type="object" required=false %}
data to pass along with this invoice for webhooks \(e.g. ticketId, etc\)
{% endapi-method-parameter %}

{% api-method-parameter name="dest\_pubkey" type="string" required=true %}
Pubkey of destination node
{% endapi-method-parameter %}

{% api-method-parameter name="num\_satoshis" type="integer" required=true %}
satoshis
{% endapi-method-parameter %}

{% api-method-parameter name="custom\_records" type="object" required=false %}
key:value pairs to be sent in the onion. key must be an integer greater than 65536. value must be a string, encoded binary data is not supported. Too many values here will break things.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Keysend Sent!
{% endapi-method-response-example-description %}

```text
{
    "id": "wtx_s1xa5yZFlCegcgtXkaeo34",
    "created_at": 1595165573,
    "num_satoshis": -2,
    "user_label": "2 keysend to 033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
    "wal": {
        "id": "wal_czDztN5eJ4r5sJ",
        "created_at": 1582461859,
        "updated_at": 1595165573,
        "user_label": "My Postman Collection Wallet",
        "balance": 211,
        "statusType": {
            "type": "wallet",
            "name": "active",
            "display_name": "Active"
        }
    },
    "wtxType": {
        "layer": "ln",
        "name": "ln_withdrawal",
        "display_name": "LN Withdrawal"
    },
    "lnTx": {
        "id": "lntx_gTMCJKFywtc2ZMWFwge0vpcE",
        "created_at": 1595165573,
        "ln_node_id": "lnod_2s4yfYA",
        "dest_pubkey": "033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
        "payment_request": "033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500:2",
        "r_hash_decoded": "efa5d7a28c26566dbc854dce4b4c15c16afa4488e0130b393a88c2d255ae6599",
        "memo": "2 keysend to 033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
        "description_hash": null,
        "num_satoshis": 2,
        "expiry": 432000,
        "expires_at": null,
        "payment_preimage": "6e5a9be8db789bdd6c4d603b8a357561c0dd1be0fe278a4ecdbfd8e228a8fc11",
        "settled": 1,
        "settled_at": 1595165573,
        "is_keysend": 1,
        "custom_records": {
            "5482373484": "6e5a9be8db789bdd6c4d603b8a357561c0dd1be0fe278a4ecdbfd8e228a8fc11"
        }
    },
    "passThru": {
        "method": "api",
        "ticketId": "23"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Some error
{% endapi-method-response-example-description %}

```text
{
    "name": "Bad Request",
    "message": "Failure reason: FAILURE_REASON_NO_ROUTE",
    "code": 0,
    "status": 400
}
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

