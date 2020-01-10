# How to Authenticate

You can authenticate via the LNPay.co API in multiple methods. This is provided so you can implement in whatever way is easiest for the device/platform you are working on. No particular method is preferred over the other at this point.

The docs use the `HTTP Basic Authentication` method

## Get API Key

Login to [https://lnpay.co](https://lnpay.co) and your API Key can be found here: [https://lnpay.co/dashboard/integrations](https://lnpay.co/dashboard/integrations)

A **LIVE** test key `yg20O0iUMxk8kK_qUzkT4YKFvp1ZsUtp`is provided in the docs for you to play around with!

## HTTP Header Authentication

`X-Api-Key` header can be used to authenticate

{% tabs %}
{% tab title="curl" %}
```text
$ curl -H "X-Api-Key: yg20O0iUMxk8kK_qUzkT4YKFvp1ZsUtp" \
https://lnpay.co/v1/user/wallets
```
{% endtab %}
{% endtabs %}

## Query String Authentication

You can authenticate by passing the parameter `access-token` in the URL as a query string parameter.

{% tabs %}
{% tab title="curl" %}
```text
$ curl https://lnpay.co/v1/user/wallets?access-token=yg20O0iUMxk8kK_qUzkT4YKFvp1ZsUtp
```
{% endtab %}
{% endtabs %}

## HTTP Basic Authentication

Basic authentication is also supported

{% tabs %}
{% tab title="curl" %}
```text
$ curl -u yg20O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
https://lnpay.co/v1/user/wallets

# The colon prevents curl from asking for a password.
```
{% endtab %}
{% endtabs %}



