# QueryRoutes

{% swagger baseUrl="https://api.lnpay.co" path="/v1/node/default/payments/queryroutes" method="get" summary="Get QueryRoutes" %}
{% swagger-description %}
This endpoint allows you to probe a route to see the fee and if the destination pubkey is reachable
{% endswagger-description %}

{% swagger-parameter in="query" name="pub_key" type="string" %}
destination pub key
{% endswagger-parameter %}

{% swagger-parameter in="query" name="amt" type="number" %}
amount in sats
{% endswagger-parameter %}

{% swagger-response status="200" description="Route found! Here are the details" %}
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
{% endswagger-response %}

{% swagger-response status="400" description="An error returned as to why the route was unavailable" %}
```
{
    "name": "Bad Request",
    "message": "unable to find a path to destination",
    "code": 0,
    "status": 400
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```
curl -u sak_XXXX: \
"https://api.lnpay.co/v1/node/default/payments/queryroutes?pub_key=02c16cca44562b590dd279c942200bdccfd4f990c3a69fad620c10ef2f8228eaff&amt=10"
```
{% endtab %}
{% endtabs %}
