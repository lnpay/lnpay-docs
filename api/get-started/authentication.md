# How to Authenticate

You can authenticate via the LNPay.co API in multiple methods. This is provided so you can implement in whatever way is easiest for the device/platform you are working on. No particular method is preferred over the other at this point.

The docs use the `HTTP Basic Authentication` method

## Get API Key

Login to [https://lnpay.co](https://lnpay.co) and your API Key can be found here: [https://lnpay.co/developers/dashboard](https://lnpay.co/developers/dashboard)

## HTTP Header Authentication

`X-Api-Key` header can be used to authenticate

{% tabs %}
{% tab title="curl" %}
```text
$ curl -H "X-Api-Key: sak_XXXXXXX" \
https://api.lnpay.co/v1/wallets
```
{% endtab %}
{% endtabs %}

## Query String Authentication

You can authenticate by passing the parameter `access-token` in the URL as a query string parameter.

{% tabs %}
{% tab title="curl" %}
```text
$ curl https://lnpay.co/v1/wallets?access-token=sak_XXXXXXX
```
{% endtab %}
{% endtabs %}

## HTTP Basic Authentication

Basic authentication is also supported

{% tabs %}
{% tab title="curl" %}
```text
# NOTE: the colon below prevents curl from asking for password

$ curl -u sak_XXXXXXX: \
https://lnpay.co/v1/wallets


# NOTE: you must base64 encode sak_XXXXXXX: when using raw authentication header

$ curl -H 'Authorization: Basic cGFrX08waVVNeGs4a0tfcVV6a1Q0WUtGdnAxWnNVdHA6' \
https://lnpay.co/v1/wallets
```
{% endtab %}
{% endtabs %}



