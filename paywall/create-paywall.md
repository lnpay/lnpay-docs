# Create Paywall

{% api-method method="post" host="https://lnpay.co" path="/v1/paywall" %}
{% api-method-summary %}
Create Paywall
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to create paywalls.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="destination\_url" type="string" required=true %}
The redirect destination URL
{% endapi-method-parameter %}

{% api-method-parameter name="short\_url" type="string" required=false %}
The paywall url \(e.g. paywall.link/to/short\_url\). A random 5 char string is generated if blank
{% endapi-method-parameter %}

{% api-method-parameter name="memo" type="string" required=false %}
Any memo for the invoice
{% endapi-method-parameter %}

{% api-method-parameter name="num\_satoshis" type="number" required=false %}
price in satoshis. defaults to any amount
{% endapi-method-parameter %}

{% api-method-parameter name="template\_id" type="string" required=false %}
template to attach if any. ID from Layouts section of dashboard. \(e.g. tmpl\_BUDfLYoRcviqV\)
{% endapi-method-parameter %}

{% api-method-parameter name="link\_rule\_exp\_id" type="string" required=false %}
See table below for values. defaults to pay every time
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Paywall created
{% endapi-method-response-example-description %}

```
{
    "id":"pywl_bI0OuKNxLtMHWs",
    "created_at":1586448191,
    "updated_at":1586448191,
    "destination_url":"https://bigsun.xyz",
    "memo":"This is my memo",
    "short_url":"bigsun",
    "paywall_link":"https://paywall.link/to/bigsun",
    "template":null,
    "num_satoshis":100,
    "passThru":{
        "extraAttributes":{
            "unlock_threshold":0,
            "identifier_in_memo":false,
            "send_partial_preimage_redirect":false
        }
    },
    "custyDomain":{
        "domain_name":"paywall.link"
    },
    "statusType":{
        "type":"link",
        "name":"active",
        "display_name":"Active"
    },
    "paywallType":{
        "name":"basic",
        "display_name":"Basic Paywall",
        "description":"User must pay everytime the paywall is hit"
    },
    "linkExpRule":{
        "type":"PAYMENT_EXPIRATION",
        "name":"IMMEDIATE",
        "display_name":"Pay every time",
        "time_minutes":0
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
curl -u pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
-H "Content-Type: application/json" \
-X POST \
-d '{"destination_url":"https://bigsun.xyz","memo":"This is my memo","short_url":"bigsun","num_satoshis":100}' \
https://lnpay.co/v1/paywall
```
{% endtab %}
{% endtabs %}

### Link Expiration Rules

These rules control the short link functionality. They work by using a cookie to keep track of the user. 

Example: if a user pays a paywall with 6\_HR, whenever they click on the paywall link - they are redirected to the destination automatically until after 6 Hours from original purchase time. At that point they are presented with the paywall again.

<table>
  <thead>
    <tr>
      <th style="text-align:left">link_exp_rule_id</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">IMMEDIATE</td>
      <td style="text-align:left">Payer must pay every time (default)</td>
    </tr>
    <tr>
      <td style="text-align:left">NO_EXP</td>
      <td style="text-align:left">Payer has unlimited access</td>
    </tr>
    <tr>
      <td style="text-align:left">6_HR</td>
      <td style="text-align:left">Payer has access for 6 hours</td>
    </tr>
    <tr>
      <td style="text-align:left">1_D</td>
      <td style="text-align:left">Payer has access for 1_D</td>
    </tr>
    <tr>
      <td style="text-align:left">30_D</td>
      <td style="text-align:left">Payer has access for 30_D</td>
    </tr>
    <tr>
      <td style="text-align:left">90_D</td>
      <td style="text-align:left">Payer has access for 90_D</td>
    </tr>
    <tr>
      <td style="text-align:left">ONE_TIME_USE</td>
      <td style="text-align:left">
        <p>Once the link is paid one time by anyone,</p>
        <p>it is no longer valid for anyone</p>
      </td>
    </tr>
  </tbody>
</table>

