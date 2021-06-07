# QueryRoutes

{% api-method method="get" host="https://api.lnpay.co" path="/v1/node/default/payments/queryroutes?pub\_key=&amt=" %}
{% api-method-summary %}
Get QueryRoutes
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to probe a route to see the fee and if the destination pubkey is reachable
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="pub\_key" type="string" required=true %}
destination pub key
{% endapi-method-parameter %}

{% api-method-parameter name="amt" type="number" required=true %}
amount in sats
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Route found! Here are the details
{% endapi-method-response-example-description %}

```
{
    "routes": [
        {
            "totalTimeLock": 679370,
            "totalAmt": "10",
            "hops": [
                {
                    "chanId": "730229652611137536",
                    "chanCapacity": "600000",
                    "amtToForward": "10",
                    "expiry": 679226,
                    "amtToForwardMsat": "10000",
                    "feeMsat": "11",
                    "pubKey": "0387cc9d4114aa5a4c9721c1837cdc133668a05a15dce5e3e99171b35dd65f7443",
                    "tlvPayload": true
                },
                {
                    "chanId": "730229652611137538",
                    "chanCapacity": "200000",
                    "amtToForward": "10",
                    "expiry": 679226,
                    "amtToForwardMsat": "10000",
                    "pubKey": "02c16cca44562b590dd279c942200bdccfd4f990c3a69fad620c10ef2f8228eaff",
                    "tlvPayload": true
                }
            ],
            "totalFeesMsat": "11",
            "totalAmtMsat": "10011"
        }
    ],
    "successProb": 0.9025
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
An error returned as to why the route was unavailable
{% endapi-method-response-example-description %}

```
{
    "name": "Bad Request",
    "message": "unable to find a path to destination",
    "code": 0,
    "status": 400
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="cURL" %}
```text
$ curl -u pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
"https://api.lnpay.co/v1/node/default/payments/queryroutes?pub_key=02c16cca44562b590dd279c942200bdccfd4f990c3a69fad620c10ef2f8228eaff&amt=10"
```
{% endtab %}
{% endtabs %}

