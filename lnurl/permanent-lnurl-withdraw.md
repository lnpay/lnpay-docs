---
description: >-
  Static LNURL-withdraw provides an LNURL tied to a wallet that will always be
  active. This will allow direct withdraw access to the wallet at all times.
---

# Permanent LNURL-withdraw

{% api-method method="get" host="https://api.lnpay.co/v1/wallet" path="/:wallet\_access\_key/lnurl/withdraw-static" %}
{% api-method-summary %}
GetLnurlWalletWithdrawStatic
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="wallet\_access\_key" type="string" required=true %}
access\_key with admin permission
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="memo" type="string" required=false %}
default memo to always show
{% endapi-method-parameter %}

{% api-method-parameter name="num\_satoshis" type="number" required=false %}
default withdrawal amount
{% endapi-method-parameter %}

{% api-method-parameter name="passThru" type="string" required=false %}
base64 encoded json data to pass along
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Permanent LNURL generated
{% endapi-method-response-example-description %}

```
{
    "lnurl" : "LNURL1DP68GUP69UHKCMNSV9UJUMR0VDSKCW3CXYCNZTMKXYHHWCTVD3JHGTMHV94KCA6L23XX27JCDAA82M2R0F8XKV6FF9HXVVMTX9F8XU30D3H82UNV94C8YMMRV4EHX0MWW4K47UMPW3HHX6RFWV7NYFNDV4KK702EDAXX7DJTWCJ"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="danger" %}
These LNURLs allow unlimited access to withdrawing from the wallet!
{% endhint %}

{% tabs %}
{% tab title="cURL" %}
```text
curl -u pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
"https://api.lnpay.co/v1/wallet/wa_Opnn4kGOGBMnfCLFXtsDnjTb/lnurl/withdraw-static?num_satoshis=3"

#
```
{% endtab %}
{% endtabs %}

