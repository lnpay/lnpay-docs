---
description: Initiate a keysend payment from your wallet to a destination pubkey
---

# Keysend

{% swagger baseUrl="https://<yourdomain>" path="/v1/wallet/:wallet_key/keysend" method="post" summary="PostWalletKeysend Synchronous" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="wallet_key" type="string" %}
wal\_ for server side\
waka\_ for client side
{% endswagger-parameter %}

{% swagger-parameter in="body" name="num_satoshis" type="integer" %}
satoshis
{% endswagger-parameter %}

{% swagger-parameter in="body" name="dest_pubkey" type="string" %}
Pubkey of destination node
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fee_limit_msat" type="integer" %}
max fee e.g. 1000 (1 sat) LNPay default is 5% of payment amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="custom_records" type="object" %}
key:value pairs for the onion.



ex. {"7629169":{"app\_name":"Podcast Player"\}}
{% endswagger-parameter %}

{% swagger-parameter in="body" name="passThru" type="object" %}
data to pass along with this invoice for webhooks (e.g. ticketId, etc)
{% endswagger-parameter %}

{% swagger-response status="201" description="Keysend Sent!" %}
```
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
{% endswagger-response %}

{% swagger-response status="400" description="Some error" %}
```
{
    "name": "Bad Request",
    "message": "Failure reason: FAILURE_REASON_NO_ROUTE",
    "code": 0,
    "status": 400
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://<yourdomain>" path="/v1/wallet/:wallet_key/keysend" method="post" summary="PostWalletKeysend Asynchronous" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="wallet_key" type="string" %}
wal\_ for server side\
waka\_ for client side
{% endswagger-parameter %}

{% swagger-parameter in="body" name="num_satoshis" type="integer" %}
satoshis
{% endswagger-parameter %}

{% swagger-parameter in="body" name="dest_pubkey" type="string" %}
Pubkey of destination node
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fee_limit_msat" type="integer" %}
max fee e.g. 1000 (1 sat) LNPay default is 5% of payment amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="custom_records" type="object" %}
key:value pairs for the onion.



ex. {"7629169":{"app\_name":"Podcast Player"\}}
{% endswagger-parameter %}

{% swagger-parameter in="body" name="passThru" type="object" %}
data to pass along with this invoice for webhooks (e.g. ticketId, etc)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-LNPAY-ASYNC" type="boolean" %}
If set to 1, the keysend request will be asynchronously processed. An immediate response will returned&#x20;
{% endswagger-parameter %}

{% swagger-response status="201" description="Keysend Sent!" %}
```
{
   "id":"382883",
   "success":"1"
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Some error" %}
```
{
    "name": "Bad Request",
    "message": "Failure reason: FAILURE_REASON_NO_ROUTE",
    "code": 0,
    "status": 400
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```
curl -u sak_XXXXXXX: \
-H "Content-Type: application/json" \
-X POST \
-d '{"dest_pubkey":"033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500","num_satoshis":2}' \
https://<yourdomain>/v1/wallet/waka_XXXXXXX/keysend

# Note we are using the "admin" access_key as denoted by "wa_"
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
const lnpay = LNPay({
  secretKey: 'sak_XXXXX',
  walletAccessKey: 'wal_XXXXX',
});

const keysend = await lnpay.keysend({
  passTru: {
    order_id: '100',
  },
  dest_pubkey: '033868c219bdb51a3...',
  num_satoshis: 1,
});
```
{% endtab %}
{% endtabs %}
