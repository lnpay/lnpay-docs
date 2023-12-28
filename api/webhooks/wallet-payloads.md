# Wallet Payloads

<details>

<summary>Wallet Receive (invoice)</summary>

```json
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
         "default_lnurlpay_id":"lnurlp_6Xh2hELFFqSlKEHCbF"
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

</details>

<details>

<summary>Wallet Receive (keysend)</summary>

```
{
   "wtx":{
      "id":"wtx_xPRRVALB3vdbNUuGO5VONlG",
      "wal":{
         "id":"wal_2MFYAIqBXDd0Z",
         "balance":458,
         "created_at":1642011549,
         "statusType":{
            "name":"active",
            "type":"wallet",
            "display_name":"Active"
         },
         "updated_at":1642107486,
         "user_label":"Keysend Wallet",
         "walletType":{
            "name":"generic_wallet",
            "display_name":"Generic Wallet"
         },
         "balance_msat":null,
         "default_lnurlpay_id":"lnurlp_6Xh2hELFFqSlKEHCbF"
      },
      "lnTx":{
         "id":"lntx_DJ9vcRuzNH4ijb4T7hIOurr9",
         "memo":"keysend/amp: custom record [] []",
         "expiry":432000,
         "is_amp":null,
         "settled":1,
         "fee_msat":0,
         "created_at":1642107486,
         "expires_at":null,
         "is_keysend":1,
         "ln_node_id":"lnod_2s4yfYA",
         "settled_at":1642107486,
         "dest_pubkey":"033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
         "num_satoshis":3,
         "payment_addr":"AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=",
         "custom_records":{
            "133773310":"{\"type\":28,\"message\":{\"content\":\"{\\\"feedID\\\":4058673,\\\"itemID\\\":5852901058,\\\"ts\\\":2953}\"}}d7nsak44syt7nibnb5n5ro684khie75yjpbyun5u46nye18di5zhe1epjegzt4acgtadb9zwg169tixtwbfao6ixne7wdncibrejgewc",
            "5482373484":"7477766d7469712f6e6d6749684e6a4478504d31667a76556f3652435846566c6d39673562304a6e5155733d"
         },
         "r_hash_decoded":"4339696a62316d353577352f522b453536325a7458562b543542376f56395a39714f4a345464434c336a343d",
         "payment_request":"keysend/amp",
         "description_hash":null,
         "payment_preimage":"b70be6b62abf9e680884d8c3c4f3357f3bd4a3a4425c55659bd8396f4267414b"
      },
      "wtxType":{
         "name":"ln_deposit",
         "layer":"ln",
         "display_name":"LN Deposit"
      },
      "passThru":{
         "wallet_id":"wal_2MFYAIqBXDd0Z",
         "custom_records":{
            "133773310":"{\"type\":28,\"message\":{\"content\":\"{\\\"feedID\\\":4058673,\\\"itemID\\\":5852901058,\\\"ts\\\":2953}\"}}d7nsak44syt7nibnb5n5ro684khie75yjpbyun5u46nye18di5zhe1epjegzt4acgtadb9zwg169tixtwbfao6ixne7wdncibrejgewc",
            "5482373484":"7477766d7469712f6e6d6749684e6a4478504d31667a76556f3652435846566c6d39673562304a6e5155733d"
         }
      },
      "created_at":1642107486,
      "user_label":"keysend/amp: custom record [] []",
      "num_satoshis":3
   }
}
```

</details>

<details>

<summary>Wallet Created</summary>

```
{
   "wal":{
      "id":"wal_q2hBv1c3RbR2ql",
      "balance":0,
      "created_at":1642107738,
      "statusType":{
         "name":"active",
         "type":"wallet",
         "display_name":"Active"
      },
      "updated_at":1642107738,
      "user_label":"Tester",
      "walletType":{
         "name":"generic_wallet",
         "display_name":"Generic Wallet"
      },
      "balance_msat":null,
      "default_lnurlpay_id":"lnurlp_6Xh2hELFFqSlKEHCbF"
   }
}
```

</details>

<details>

<summary>Wallet Send</summary>

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
         "default_lnurlpay_id":"lnurlp_6Xh2hELFFqSlKEHCbF"
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

</details>

<details>

<summary>Wallet Transfer OUT</summary>

* A wallet transfer triggers two events (OUT and IN)
* wtx\['num\_satoshis'] will be NEGATIVE always for a transfer OUT



```
{
   "wtx":{
      "id":"wtx_ICT3Sz4VRy43sbSgZOzXvtJw",
      "wal":{
         "id":"wal_q2hBv1c3RbR2ql",
         "balance":930,
         "created_at":1642107738,
         "statusType":{
            "name":"active",
            "type":"wallet",
            "display_name":"Active"
         },
         "updated_at":1642108138,
         "user_label":"Tester",
         "walletType":{
            "name":"generic_wallet",
            "display_name":"Generic Wallet"
         },
         "balance_msat":null,
         "default_lnurlpay_id":"lnurlp_6Xh2hELFFqSlKEHCbF"
      },
      "lnTx":null,
      "wtxType":{
         "name":"ln_transfer_out",
         "layer":"ln",
         "display_name":"Transfer Out"
      },
      "passThru":{
         "lnPayParams":null,
         "dest_wallet_id":"w_XVVXGvox1mqeS",
         "source_wallet_id":"wal_q2hBv1c3RbR2ql"
      },
      "created_at":1642108138,
      "user_label":"This is a test transfer",
      "num_satoshis":-69
   }
}
```

</details>

<details>

<summary>Wallet Transfer IN</summary>

* A wallet transfer triggers two events (OUT and IN)
* wtx\['num\_satoshis'] will be POSITIVE always for a transfer IN

```
{
   "wtx":{
      "id":"wtx_YBXUD1Cnjk3Rz0AVPzNTvq",
      "wal":{
         "id":"w_XVVXGvox1mqeS",
         "balance":135,
         "created_at":1580163964,
         "statusType":{
            "name":"active",
            "type":"wallet",
            "display_name":"Active"
         },
         "updated_at":1642108138,
         "user_label":"LN Torch",
         "walletType":{
            "name":"generic_wallet",
            "display_name":"Generic Wallet"
         },
         "balance_msat":null,
         "default_lnurlpay_id":"lnurlp_6Xh2hELFFqSlKEHCbF"
      },
      "lnTx":null,
      "wtxType":{
         "name":"ln_transfer_in",
         "layer":"ln",
         "display_name":"Transfer In"
      },
      "passThru":{
         "lnPayParams":null,
         "dest_wallet_id":"w_XVVXGvox1mqeS",
         "source_wallet_id":"wal_q2hBv1c3RbR2ql"
      },
      "created_at":1642108138,
      "user_label":"This is a test transfer",
      "num_satoshis":69
   }
}
```

</details>

<details>

<summary>Wallet Send Failure</summary>

```
{
  "wal": {
    "id": "wal_ZOBHtYmXdJzVTY",
    "balance": 93,
    "created_at": 1642003748,
    "statusType": {
      "name": "active",
      "type": "wallet",
      "display_name": "Active"
    },
    "updated_at": 1643039277,
    "user_label": "123",
    "walletType": {
      "name": "generic_wallet",
      "display_name": "Generic Wallet"
    },
    "balance_msat": null,
    "default_lnurlpay_id": "lnurlp_24zScIej6hbZv99xJB"
  },
  "passThru": {
    "ticketId": "23"
  },
  "spontaneous": 1,
  "failureReason": "Failure reason: FAILURE_REASON_NO_ROUTE",
  "node_request_parameters": {
    "amt_msat": 2000,
    "dest_pubkey": "033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
    "custom_records": {
      "696969": "test record"
    },
    "fee_limit_msat": 1000
  }
}
```

</details>
