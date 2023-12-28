# Update lnurlpay link

{% swagger method="post" path="/v1/lnurlp/:wallet_lnurlpay_id" baseUrl="https://<yourdomain>" summary="Update a lnurlpay link attached to wallet" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="wallet_lnurlpay_id" type="Integer" required="true" %}
e.g. lnurlp\_XXX
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lnurlp_minSendable_msat" type="Integer" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="lnurlp_maxSendable_msat" type="Integer" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="lnurlp_short_desc" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="identifier" type="String" %}
(for lightning address)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="custy_domain_id" type="String" %}
(for lightning address)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="lnurlpay updated!" %}
```javascript
{
    "wallet_id": "wal_M726iS8tzX6okv",
    "user_label": "Tester",
    "lnurlp_minSendable_msat": 10220,
    "lnurlp_maxSendable_msat": 10000000,
    "lnurlp_short_desc": "LNURL PAY (via LNPay.co)",
    "lnurlp_identifier": null,
    "created_at": 1646148494,
    "updated_at": 1646148494,
    "lnurl_decoded": "http://lnpay.local:8111/v1/wallet/waklp_ReYBOCMidvmfl5opePGlOr/lnurlp/lnurlp_PmSFQpdgrwCRiC16UT",
    "lnurl_encoded": "LNURL1DP68GUP69UHKCMNSV9UJUMR0VDSKCW3CXYCNZTMKXYHHWCTVD3JHGTMHV94KCUZL2FJ4JSJ0GDXKJERKD4NXCDT0WPJ4Q3MVFAEZ7MRWW4EXCUP0D3H82UNVWP04QM2NGEGHQER8WFM5X5NFGVCNV4254H9EVG",
    "id": "lnurlp_PmSFQpdgrwCRiC16UT",
    "statusType": {
        "type": "lnurl",
        "name": "lnurl_active",
        "display_name": "LNURL Active"
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
    "name": "Bad Request",
    "message": "Lnurlp Min Sendable Msat must be greater than or equal to \"1000\".",
    "code": 0,
    "status": 400
}
```
{% endswagger-response %}
{% endswagger %}
