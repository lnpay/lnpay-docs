# Create Lightning Address

Lightning Addresses are created via `lnurlpay` objects&#x20;

The same `/lnurlp` endpoint is used, but with addition of `lnurlp_identifier` and `custy_domain_id`

{% hint style="info" %}
`In order to use YOUR domain, you must implement the following redirect:`&#x20;

`<yourdomain>/.well-known/lnurlp/*` -> `api.lnpay.co/.well-known/<custy_domain_id>/lnurlp/*`
{% endhint %}

{% swagger method="post" path="/v1/wallet/:wallet_key/lnurlp" baseUrl="https://<yourdomain>" summary="Create Lightning Address" %}
{% swagger-description %}
A Lightning Address is basically a wrapper around the LNURL-pay functionality.
{% endswagger-description %}

{% swagger-parameter in="path" name="wallet_key" type="String" required="true" %}
e.g. waka\_XXX
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lnurlp_identifier" type="String" required="true" %}
e.g. myuser

do not include domain name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="custy_domain_id" type="String" required="true" %}
Domain ID e.g. cdom\_xxx
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lnurlp_minSendable_msat" type="Integer" %}
e.g. 1000
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lnurlp_maxSendable_msat" type="Integer" %}
e.g. 100000
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lnurlp_short_desc" type="String" %}
Description for invoices
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "id": "lnurlp_MV3guVwAjuFIgf9v3Z",
    "created_at": 1641914620,
    "updated_at": 1641914620,
    "user_label": "Base lnurl-pay link",
    "lnurl_encoded": "LNURL1DP68GUP69UHKCMNSV9UJUMR0VDSKCW3CXYCNZTMKXYHHWCTVD3JHGTMHV94KCUZLVEFNYUZ2FPHK5VZR0Q68SU26XDP5XNM2V355XTMVDE6HYMRS9AKXUATJD3C97N2KXDNH24NHG94823JFVANRJA3NTGMJA6YY",
    "lnurl_decoded": "http://lnpay.local:8111/v1/wallet/waklp_fS2pJHoj0Cx4xqZ3CCOjdiC/lnurlp/lnurlp_MV3guVwAjuFIgf9v3Z",
    "lnurlp_minSendable_msat": 1000,
    "lnurlp_maxSendable_msat": 10000000,
    "lnurlp_short_desc": "LNURL PAY (via LNPay.co)",
    "identifier": "username",
    "statusType": {
        "type": "lnurl",
        "name": "lnurl_active",
        "display_name": "LNURL Active"
    },
    "custyDomain": {
        "domain_name": "sats.me",
        "display_name": "My LN Address Domain"
    }
}
```
{% endswagger-response %}
{% endswagger %}
