---
description: >-
  This endpoint allows generation of disposable ONE-TIME use LNURLs. This is
  good for controlling how often and when users can withdraw from a wallet. Upon
  successful withdrawal, the LNURL is invalid
---

# Disposable LNURL-withdraw

{% swagger baseUrl="https://<yourdomain>/v1/wallet" path="/:wallet_key/lnurl/withdraw" method="get" summary="GetWalletLnurlWithdraw" %}
{% swagger-description %}
Generate a disposable LNURL-withdraw link.&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="wallet_key" type="string" %}
wal\_ for server side\
waka\_ for client side
{% endswagger-parameter %}

{% swagger-parameter in="query" name="passThru" type="string" %}
base64 encoded json of data to use in webhooks, etc
{% endswagger-parameter %}

{% swagger-parameter in="query" name="memo" type="string" %}
memo for the invoice
{% endswagger-parameter %}

{% swagger-parameter in="query" name="num_satoshis" type="integer" %}
Max number of satoshis this LNURL is good for. \
\
If blank max wallet balance is used
{% endswagger-parameter %}

{% swagger-response status="200" description="LNURL generated" %}
```
{
    "lnurl":"LNURL1DP68GURN8GHJ7MRWWPSHJTNRDUHHVVF0W4EK2U30WASKCMR9WSHHWC2LFACXUM35DDR5736ZF4HXVS6VGEV8GU6YDE49GC30D3H82UNV94C8YMMRV4EHX0M0W36R66MGD95KS4JGFADRS4ZRFEXK2SN2FFUXUSMHFA98XDZ8D3T9SDECWVHR43"
    "ott":"Y4J9"
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
Note: These LNURLs are ONE-TIME use. This is to prevent repeated access to the wallet.

the `ott` is a One-Time-Token that is encoded in the LNURL and saved by the wallet to verify
{% endhint %}

{% tabs %}
{% tab title="curl" %}
```bash
curl -u sak_XXXXXXX: \
"https://<yourdomain>/v1/wallet/wal_XXXXXXX/lnurl/withdraw?num_satoshis=3"
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp');

let lnurlParams = {"num_satoshis":12,"memo":"SatsBack!"};
let myWallet = new LNPayWallet('wa_Opnn4kGOGBMnfCLFXtsDnjTb');
myWallet.getLnurl(lnurlParams,
    function(result) {
      console.log(result);
    }
);
```
{% endtab %}

{% tab title="Python" %}
```python
lnpay_py.initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp')
from lnpay_py.wallet import LNPayWallet

my_wallet = LNPayWallet('wa_Opnn4kGOGBMnfCLFXtsDnjTb')
lnurl_params = {
    'num_satoshis': 1,
    'memo': 'SatsBack!'
}
lnurl_link = my_wallet.get_lnurl(lnurl_params)
print(lnurl_link)
```
{% endtab %}
{% endtabs %}
