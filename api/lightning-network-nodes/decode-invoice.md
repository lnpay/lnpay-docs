--
description: Decode an invoice and get route hints. Uses LNPay.co node
--

# Decode Invoice

{% api-method method="get" host="https://api.lnpay.co" path="/v1/node/default/payments/decodeinvoice" %}
{% api-method-summary %}
DecodeInvoice
{% endapi-method-summary %}

{% api-method-description %}
Using an LND node
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="payment\_request" type="string" %}
Payment request lnbc...
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Decoded invoice
{% endapi-method-response-example-description %}

```
{
    "destination":"02c16cca44562b590dd279c942200bdccfd4f990c3a69fad620c10ef2f8228eaff",
    "payment_hash":"a202d6f9a67b0259be44fc18329a734167a1dcf9135e1b001cc8225d01be8f38",
    "num_satoshis":"69",
    "timestamp":"1581701421",
    "expiry":"86400",
    "description":"Demo Memo",
    "cltv_expiry":"144",
    "route_hints":[
        {
            "hop_hints":[
                {
                    "node_id":"03a503d8e30f2ff407096d235b5db63b4fcf3f89a653acb6f43d3fc492a7674019",
                    "chan_id":"676900040102838273",
                    "fee_proportional_millionths":98,
                    "cltv_expiry_delta":29
                }
            ]
        }
    ],
    "payment_addr":"yUu1+Yzh7/YvOyKTQrc822SRCRw1n62BfT+eKsZx73w=",
    "num_msat":"69000",
    "features":{
        "9":{
            "name":"tlv-onion",
            "is_known":true
        },
        "15":{
            "name":"payment-addr",
            "is_known":true
        },
        "17":{
            "name":"multi-path-payments",
            "is_known":true
        }
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="curl" %}
```text
curl -u sak_XXXX: \
https://api.lnpay.co/v1/node/default/payments/decodeinvoice?payment_request=lnbc690n1p0ydkfdpp55gpdd7dx0vp9n0jylsvpp0lj....
```
{% endtab %}
{% endtabs %}

