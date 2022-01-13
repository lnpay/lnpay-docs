---
description: All WalletTransaction objects are prefixed with wtx_
---

# Wallet Send / Receive

## The Wallet Transaction Object

Any Wallet interaction with the Lightning Network that results in a _**settled**_ transaction creates a WalletTransaction object. Here are some examples of them below

{% tabs %}
{% tab title="Wallet Pay Invoice" %}
```
{
   "wtx":{
      "id":"wtx_YQs4Uu0JPBI8jxQhdWUstbKs",
      "wal":{
         "id":"wal_q2hBv1c3RbR2ql",
         "balance":0,
         "created_at":1642107738,
         "statusType":{
            "name":"active",
            "type":"wallet",
            "display_name":"Active"
         },
         "updated_at":1642107996,
         "user_label":"Tester",
         "walletType":{
            "name":"generic_wallet",
            "display_name":"Generic Wallet"
         },
         "balance_msat":null,
         "defaultLnurlpay":{
            "id":"lnurlp_QYmSeHiSev5PDqa2RY",
            "created_at":1642107738,
            "statusType":{
               "name":"lnurl_active",
               "type":"lnurl",
               "display_name":"LNURL Active"
            },
            "updated_at":1642107738,
            "user_label":"Base lnurl-pay link",
            "lnurl_decoded":"https://cloud.lnpay.co/v1/wallet/waklp_0C9ezQHHMQ0z77VU5dpIfB/lnurlp/lnurlp_QYmSeHiSev5PDqa2RY",
            "lnurl_encoded":"LNURL1DP68GURN8GHJ7CMVDA6KGTNVDECXZ7FWVDHJ7A339AMKZMRVV46Z7AMPDDK8QHESGVUK27J3FPYY65FS0GMNW4J4X4J8QJTXGGHKCMN4WFK8QTMVDE6HYMRSTAG4JM2NV4YXJ5M9WC64Q3R3VYE9YKGHJXE2D",
            "lnurlp_short_desc":"LNURL PAY (via LNPay.co)",
            "lnurlp_maxSendable_msat":100000000,
            "lnurlp_minSendable_msat":1000
         }
      },
      "lnTx":{
         "id":"lntx_xd102sPOytDpUr2WadQALB",
         "memo":"Test",
         "expiry":432000,
         "is_amp":null,
         "settled":1,
         "fee_msat":2,
         "created_at":1642107996,
         "expires_at":1642194396,
         "is_keysend":null,
         "ln_node_id":"lnod_2s4yfYA",
         "settled_at":1642107996,
         "dest_pubkey":"037cc5f9f1da20ac0d60e83989729a204a33cc2d8e80438969fadf35c1c5f1233b",
         "num_satoshis":10,
         "payment_addr":null,
         "custom_records":null,
         "r_hash_decoded":"0dd3ec96995c799c97dd32f0c2877f7600d299c50fd784909e0e7f833ead7779",
         "payment_request":"lnbc100n1ps7p9p2pp5phf7e95et3uee97axtcv9pmlwcqd9xw9pltcfyy7pelcx04dwausdq823jhxaqcqzpgxqyz5vqsp54we36e25q9da2sn4slvmynl3jmlufz3nlxn4r9lrqv9luwd87gps9qyyssq8pk9cm9hwa3sl3ll3nfq6cpayehft0xtlksryr3895yhpmavchx56v7gfh3kgr98xqee754lun5k9zpmu22p38xvf6x5yjvlcggzksgpwwnft4",
         "description_hash":null,
         "payment_preimage":"05e2e0e76b9184d413baa6f0b0611f2abcde0d29eb0c8c192c1b2b5d0fbcafd4"
      },
      "wtxType":{
         "name":"ln_withdrawal",
         "layer":"ln",
         "display_name":"LN Withdrawal"
      },
      "passThru":{
         "outgoingChannelId":"677787345915674625"
      },
      "created_at":1642107996,
      "user_label":"Test",
      "num_satoshis":-10
   }
}
```
{% endtab %}

{% tab title="Wallet Receive" %}
```
{
   "wtx":{
      "id":"wtx_vwEZVTkBzGdhDXExI8d3ofGn",
      "wal":{
         "id":"wal_q2hBv1c3RbR2ql",
         "balance":10,
         "created_at":1642107738,
         "statusType":{
            "name":"active",
            "type":"wallet",
            "display_name":"Active"
         },
         "updated_at":1642107857,
         "user_label":"Tester",
         "walletType":{
            "name":"generic_wallet",
            "display_name":"Generic Wallet"
         },
         "balance_msat":null,
         "defaultLnurlpay":{
            "id":"lnurlp_QYmSeHiSev5PDqa2RY",
            "created_at":1642107738,
            "statusType":{
               "name":"lnurl_active",
               "type":"lnurl",
               "display_name":"LNURL Active"
            },
            "updated_at":1642107738,
            "user_label":"Base lnurl-pay link",
            "lnurl_decoded":"https://cloud.lnpay.co/v1/wallet/waklp_0C9ezQHHMQ0z77VU5dpIfB/lnurlp/lnurlp_QYmSeHiSev5PDqa2RY",
            "lnurl_encoded":"LNURL1DP68GURN8GHJ7CMVDA6KGTNVDECXZ7FWVDHJ7A339AMKZMRVV46Z7AMPDDK8QHESGVUK27J3FPYY65FS0GMNW4J4X4J8QJTXGGHKCMN4WFK8QTMVDE6HYMRSTAG4JM2NV4YXJ5M9WC64Q3R3VYE9YKGHJXE2D",
            "lnurlp_short_desc":"LNURL PAY (via LNPay.co)",
            "lnurlp_maxSendable_msat":100000000,
            "lnurlp_minSendable_msat":1000
         }
      },
      "lnTx":{
         "id":"lntx_TXRORc6kW2rBT0hqJlkoQw",
         "memo":"",
         "expiry":86400,
         "is_amp":null,
         "settled":1,
         "fee_msat":0,
         "created_at":1642107841,
         "expires_at":1642194241,
         "is_keysend":null,
         "ln_node_id":"lnod_2s4yfYA",
         "settled_at":1642107857,
         "dest_pubkey":"033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
         "num_satoshis":10,
         "payment_addr":null,
         "custom_records":null,
         "r_hash_decoded":"8d8c540d053e5cabb014a48af8c145305ac06189b39acd9c07518b599505b358",
         "payment_request":"lnbc100n1ps7py7ppp53kx9grg98ew2hvq55j903s29xpdvqcvfkwdvm8q82x94n9g9kdvqdqqcqzpgxqyz5vqsp5cn4uxne445v6udyu2v4ntqwccx4f0dusdq898c2alxqzgqq0thcq9qyyssqny3ck4je9fv4kgpjgesdjwvhhkklxw6ykjtc67zxjvcr9hw5vntpm37wpm36sqwsrf57ka5tm9up6hnjzrlkzr2887ylxxwdawl8c8sp5x06q5",
         "description_hash":null,
         "payment_preimage":"00f910ea5baf99ba919ebb5f37ce6e08f2b1951ad6b198356dcda1eae8f91c4f"
      },
      "wtxType":{
         "name":"ln_deposit",
         "layer":"ln",
         "display_name":"LN Deposit"
      },
      "passThru":{
         "htlc":{
            "state":"SETTLED",
            "chanId":"783597747941277697",
            "amtMsat":"10000",
            "htlcIndex":"16826",
            "acceptTime":"1642107857",
            "resolveTime":"1642107857",
            "acceptHeight":718528,
            "expiryHeight":718570,
            "mppTotalAmtMsat":"10000"
         },
         "wallet_id":"wal_q2hBv1c3RbR2ql"
      },
      "created_at":1642107857,
      "user_label":"",
      "num_satoshis":10
   }
}
```
{% endtab %}
{% endtabs %}
