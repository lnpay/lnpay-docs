# Sending Requests

## Request Formats

### Form Data

If no `Content-Type` is specified, the request will be interpreted as Form Data. Example invoice generation request.

{% tabs %}
{% tab title="curl" %}
```text
$ curl -u yg20O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
-X POST \
-d num_satoshis=20 \
-d memo="Test invoice from the docs" \
https://lnpay.co/v1/user/wallet/wi_skllxCQI7yurKi0NCCTc0wwO/invoice
```
{% endtab %}
{% endtabs %}

### JSON

JSON requests **MUST** contain the `Content-Type: application/json` header. Example invoice generation request. 

{% tabs %}
{% tab title="curl" %}
```text
$ curl -u yg20O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
-H "Content-Type: application/json" \
-X POST \
-d '{"num_satoshis":20, "memo":"Test invoice from the docs"}' \
https://lnpay.co/v1/user/wallet/wi_skllxCQI7yurKi0NCCTc0wwO/invoice
```
{% endtab %}
{% endtabs %}

## Limit response sizes

By default the objects are returned with all fields. You can limit the response to only the fields you want. You may want to do this if you are dealing with a device that has limited memory or just for speed sake.

{% tabs %}
{% tab title="curl" %}
```text
$ curl -u yg20O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
https://lnpay.co/v1/user/lntx/lntx_82yveCX2Wn0EkkdyzvyBv?fields=num_satoshis,settled

//Response

{"num_satoshis":5,"settled":1}
```
{% endtab %}
{% endtabs %}

