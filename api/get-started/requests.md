---
description: This documentation uses a JSON body as the default.
---

# Sending Requests

## Request Formats

### Form Data

If no `Content-Type` is specified, the request will be interpreted as Form Data. Example invoice generation request.

{% tabs %}
{% tab title="curl" %}
```
$ curl -u sak_XXXXXXX: \
-X POST \
-d num_satoshis=20 \
-d memo="Test invoice from the docs" \
https://<yourdomain>/v1/user/wallet/wi_XXXXXXX/invoice
```
{% endtab %}
{% endtabs %}

### JSON

JSON requests **MUST** contain the `Content-Type: application/json` header. Example invoice generation request.&#x20;

{% tabs %}
{% tab title="curl" %}
```
$ curl -u sak_XXXXXXX: \
-H "Content-Type: application/json" \
-X POST \
-d '{"num_satoshis":20, "memo":"Test invoice from the docs"}' \
https://<yourdomain>/v1/user/wallet/wi_XXXXXXXX/invoice
```
{% endtab %}
{% endtabs %}

## Limit response sizes

By default the objects are returned with all fields. You can limit the response to only the fields you want. You may want to do this if you are dealing with a device that has limited memory or just for speed sake.

{% tabs %}
{% tab title="curl" %}
```
$ curl -u sak_XXXXXXX: \
https://<yourdomain>/v1/lntx/lntx_XXXXXXX?fields=num_satoshis,settled

//Response

{"num_satoshis":5,"settled":1}
```
{% endtab %}
{% endtabs %}

## Pagination

Most endpoints support pagination if it is a list-based GET request. `page` and `per-page` are supported

{% tabs %}
{% tab title="curl" %}
```
$ curl -u sak_XXXXXXX: \
https://<yourdomain>/v1/wallet/wakr_XXXXXX/transactions?page=2&per-page=100
```
{% endtab %}
{% endtabs %}
