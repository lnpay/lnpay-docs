---
description: >-
  Static LNURL-withdraw provides an LNURL tied to a wallet that will always be
  active. This will allow direct withdraw access to the wallet at all times.
---

# Permanent LNURL-withdraw

{% swagger baseUrl="https://<yourdomain>/v1/wallet" path="/:wallet_key/lnurl/withdraw-static" method="get" summary="GetLnurlWalletWithdrawStatic" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="wallet_key" type="string" %}
wal\_ for server side\
waka\_ for client side
{% endswagger-parameter %}

{% swagger-parameter in="query" name="memo" type="string" %}
default memo to always show
{% endswagger-parameter %}

{% swagger-parameter in="query" name="num_satoshis" type="number" %}
default withdrawal amount
{% endswagger-parameter %}

{% swagger-parameter in="query" name="passThru" type="string" %}
base64 encoded json data to pass along
{% endswagger-parameter %}

{% swagger-response status="200" description="Permanent LNURL generated" %}
```
{
    "lnurl" : "LNURL1DP68GUP69UHKCMNSV9UJUMR0VDSKCW3CXYCNZTMKXYHHWCTVD3JHGTMHV94KCA6L23XX27JCDAA82M2R0F8XKV6FF9HXVVMTX9F8XU30D3H82UNV94C8YMMRV4EHX0MWW4K47UMPW3HHX6RFWV7NYFNDV4KK702EDAXX7DJTWCJ"
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="danger" %}
These LNURLs allow unlimited access to withdrawing from the wallet!
{% endhint %}

{% tabs %}
{% tab title="cURL" %}
```
curl -u sak_XXXXXXX: \
"https://<yourdomain>/v1/wallet/waka_XXXXXXXXX/lnurl/withdraw-static?num_satoshis=3"
```
{% endtab %}
{% endtabs %}
