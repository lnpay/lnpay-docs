# Create Wallet

{% swagger baseUrl="https://api.lnpay.co/" path="v1/wallet" method="post" summary="PostCreateWallet" %}
{% swagger-description %}
Create a new wallet and corresponding access keys
{% endswagger-description %}

{% swagger-parameter in="body" name="user_label" type="string" %}
An internal identifier for this wallet
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ln_node_id" type="string" %}
The LN node that this wallet will send/receive from

\




**Default:**

 LNPay custodial
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
    "default_lnurlpay_id": "lnurlp_6Xh2hELFFqSlKEHCbF",
    "access_keys": {
        "Wallet Admin": [
            "waka_UggociEGwiYpdRu2ijPGvpZU"
        ],
        "Wallet Invoice": [
            "waki_bAOtEllC5NDChqE6OZTUvoW"
        ],
        "Wallet Read": [
            "wakr_RuhD3xePPNNhmYG0KIvWxphO"
        ],
        "Wallet LNURL Withdraw": [
            "waklw_hG2hQhNiaib1calX6r2gOYX0"
        ]
    }
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
-d '{"user_label":"Tester API Wallet"}' \
https://api.lnpay.co/v1/wallet
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
const lnpay = LNPay({
  secretKey: 'sak_XXXXX'
});

const wallet = await lnpay.createWallet({
  user_label: 'My Wallet',
});
```
{% endtab %}

{% tab title="Python" %}
```python
lnpay_py.initialize('sak_XXXXX')

wallet_params = {
    'user_label': 'My wallet'
}
new_wallet = lnpay_py.create_wallet(wallet_params)
```
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
The access keys generated will NOT be available via the API again! You must save and store them
{% endhint %}

