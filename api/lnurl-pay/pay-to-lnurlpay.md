---
description: Pay an lnurlpay bech32 encoded paylink
---

# Pay to lnurlpay

{% hint style="danger" %}
Not Live Yet - Coming Soon!
{% endhint %}

{% swagger method="post" path="/v1/wallet/:wallet_key/pay-lnurlpay" baseUrl="https://api.lnpay.co" summary="Send payment to an lnurlpay paylink" %}
{% swagger-description %}
Should be used in conjunction with the lnurlpay 

[probe](probe.md)

 endpoint
{% endswagger-description %}

{% swagger-parameter in="body" name="amount_msat" type="Integer" required="true" %}
e.g. 1000 which would equal 1 sat
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="wtx object" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}
