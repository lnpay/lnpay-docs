# Probe

The LNURL-pay ingestion endpoint enables you to "probe" an lnurlpay paylink / lightning address to see its parameters. You can then use this information to determine if you will pay this link.

{% swagger method="get" path="/v1/lnurlp/probe/:lnurlpay_encoded | :ln_address" baseUrl="https://<yourdomain>" summary="Probe the lnurlpay link / lightning address to get its parameters" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="ln_address" %}
e.g. fiatjaf@lntxbot.com
{% endswagger-parameter %}

{% swagger-parameter in="path" name="lnurlpay_encoded" required="false" %}
e.g. LNURL1DP68GUP69UHKCMNSV9UJUMR0VDSKCW3CXYCNZT....
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="lnurlpay retrieved details" %}
```javascript
{
    "minSendable": 1000, //msat
    "maxSendable": 10000000, //msat
    "commentAllowed": 0, //number of characters allowed in a comment when payment is sent
    "tag": "payRequest",
    "metadata": [
        [
            "text/plain",
            "LNURL PAY (via LNPay.co)"
        ]
    ],
    "callback": "http://some-service.com/v1/wallet/waklp_jW7vCpByJu1jKuFXT3UiRzB6/lnurlp/lnurlp_s9kmV724XtZvfxciXF"
}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="why the lnurl is invalid" %}
```javascript
{
    "name": "Exception",
    "message": "Invalid bech32 checksum",
    "code": 0,
    "type": "lnpay\\wallet\\exceptions\\InvalidLnurlpayLinkException",
}
```
{% endswagger-response %}
{% endswagger %}
