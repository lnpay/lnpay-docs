---
description: >-
  LNURL provides a standard for receiving sats over lightning WITHOUT having the
  user paste an invoice.
---

# How does LNURL-withdraw work?

Typically when a user wishes to receive sats, they generate an invoice, and that invoice is paid by the sender. In most user-facing b2c applications, it is pretty bad UX for the user to have to generate an invoice and then paste it into a service. 

[LNURL](https://github.com/fiatjaf/lnurl-rfc) is a grassroots protocol that set out to address some of these issues. There are other aspects of the protocol in addition to withdrawals, but we will talk about withdrawing sats from services here.

## LNURL-withdraw in Practice

Here is an example of an LNURL-withdraw link that is compatible with most lightning wallets. Typically these are shown in QR form and scanned. You can also prefix with `lightning:LNURLASD` to take advantage of deeplinking which some wallets support.

```
# Example of a LNURL that is recognized by lightning wallets (mostly used in QR form)

LNURL1DP68GURN8GHJ7CTSDYHXCMNSV9UJUCM09AMRZTMHV9KXCET59AMKZH60WPHXUDRTGA85WSJDDENYXNZXTP68X3RWDF2XYTMVDE6HYMPDWPEX7CM9WDEN7MM5WS7NYUZGG34N2SESFCUYS3PXDE6K6HMNV96X7UMGD9EN6VCY8TWN5

# decodes to 

https://api.lnpay.co/v1/wallet/wa_Opnn4kGOGBMnfCLFXtsDnjTb/lnurl-process?ott=2pHDk5C0N8HD&num_satoshis=3
```

{% hint style="info" %}
There is an easy encoder/decoder here: [https://lnurl.bigsun.xyz/codec/](https://lnurl.bigsun.xyz/codec/) 
{% endhint %}

### What the lightning wallet sees

The lightning wallet will make a GET request to the decoded LNURL endpoint and receive something like the JSON below:

```text
# GET https://api.lnpay.co/v1/wallet/wa_Opnn4kGOGBMnfCLFXtsDnjTb/lnurl-process?ott=2pHDk5C0N8HD&num_satoshis=3

{
    "callback": "https://api.lnpay.co/v1/user/wallet/wa_Opnn4kGOGBMnfCLFXtsDnjTb/lnurl-process?ott=2pHDk5C0N8HD",
    "k1": "k1",
    "maxWithdrawable": 2000, # wallet uses this to prefill amount. it is in msats
    "defaultDescription": "LNPay.co Wallet Withdraw", # wallet uses this to prefill memo
    "minWithdrawable": 0,
    "tag": "withdrawRequest",
    "balanceCheck": "https://api.lnpay.co/v1/wallet/wa_Opnn4kGOGBMnfCLFXtsDnjTb/lnurl-process?ott=QXoPMksjJeBq"
}
```

### The actual withdrawal

After the wallet receives this JSON it generates a payment request \(`pr`\) for an amount of sats equal to or below the `maxWithdrawable` - in this case 2 sats. The wallet then makes a GET request to the `callback` endpoint with the generated payment \(`pr`\) request appended on the end as a query string parameter \(`pr`\) 

```text
GET https://api.lnpay.co/v1/wallet/wa_Opnn4kGOGBMnfCLFXtsDnjTb/lnurl-process?
ott=2pHDk5C0N8HD
&num_satoshis=3
&pr=lnbc...

# LNPAY server pays this invoice
```



