# Retrieve lnurlpay

Every wallet has a default lnurlpay link associated with it [as specified](../wallets/retrieve.md) - `default_lnurlpay_id`

Retrieving the `WalletLnurlpay` Object returns the lnurl info and other parameters

{% swagger method="get" path="/v1/lnurlp/:wallet_lnurlpay_id" baseUrl="https://<yourdomain>" summary="Retrieve WalletLnurlpay object" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="wallet_lnurlpay_id" type="String" required="true" %}
e.g. lnurlp\_0YM18Nt3po8SUmIOKE
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "id": "lnurlp_MV3guVwAjuFIgf9v3Z",
    "created_at": 1641914620,
    "updated_at": 1641914620,
    "user_label": "Base lnurl-pay link",
    "lnurlp_identifier": "username", //this translates to username@domain.com
    "lnurl_encoded": "LNURL1DP68GUP69UHKCMNSV9UJUMR0VDSKCW3CXYCNZTMKXYHHWCTVD3JHGTMHV94KCUZLVEFNYUZ2FPHK5VZR0Q68SU26XDP5XNM2V355XTMVDE6HYMRS9AKXUATJD3C97N2KXDNH24NHG94823JFVANRJA3NTGMJA6YY",
    "lnurl_decoded": "http://lnpay.local:8111/v1/wallet/waklp_fS2pJHoj0Cx4xqZ3CCOjdiC/lnurlp/lnurlp_MV3guVwAjuFIgf9v3Z",
    "lnurlp_minSendable_msat": 1000,
    "lnurlp_maxSendable_msat": 10000000,
    "lnurlp_short_desc": "LNURL PAY (via LNPay.co)",
    "statusType": {
        "type": "lnurl",
        "name": "lnurl_active",
        "display_name": "LNURL Active"
    }
}
```
{% endswagger-response %}
{% endswagger %}
