---
description: Webhooks & Events
---

# Webhook Intro

Webhooks can be setup in the LNPay.co dashboard. You are subscribed to all events, and future events by default. Eventually, you will be able to choose. You can send test requests as well.

## Events

| Event Name | Event Display Name | Note |
| :--- | :--- | :--- |
| wallet\_created | Wallet Create |  |
| wallet\_send | Wallet Send |  |
| wallet\_receive | Wallet Receive |  |
| wallet\_transfer | Wallet Transfer | Transfer between LNPay wallets |
| paywall\_created | Paywall Created |  |
| paywall\_conversion | Paywall Conversion | Paywall paid |

## Payloads

Every payload will follow the same format. an Event ID is provided to identify the event, along with an object of the type details. The `data` section will always contain an array of relevant objects to the event. The key of each object in the data object will match the object id: `"wal":".."` matches `wal_czDztN5eJ4r5sJ` for now this seems the easiest way to plan for future changes and additions. 

{% hint style="info" %}
Pay careful attention to `passThru` value. This is where context data that you have set previously, will be available throughout the journey of the wallet transaction. 

NOTE: there are some server parameters that are passed through in this field as well, so it is a good idea to prefix your variables with something e.g. `xyz_ticketId`
{% endhint %}

### Wallets

{% tabs %}
{% tab title="wallet\_created" %}
```text
{
  "created_at": 1582461859,
  "id": "evt_XD6Gy21M8jRpplxI9YT3IpR9",
  "event": {
    "type": "wallet",
    "name": "wallet_created",
    "display_name": "Wallet Create"
  },
  "data": {
    "wal": {
      "user_label": "My Postman Collection Wallet",
      "created_at": 1582461859,
      "updated_at": 1582461859,
      "id": "wal_czDztN5eJ4r5sJ",
      "statusType": {
        "type": "wallet",
        "name": "active",
        "display_name": "Active"
      }
    }
  }
}
```
{% endtab %}

{% tab title="wallet\_send" %}
```text
{
  "created_at": 1582462278,
  "id": "evt_Ysjv7VYGtZttVkffUzm4jXf",
  "event": {
    "type": "wallet",
    "name": "wallet_send",
    "display_name": "Wallet Send"
  },
  "data": {
    "wtx": {
      "num_satoshis": -1,
      "user_label": "Test for DOCS",
      "created_at": 1582462278,
      "id": "wtx_dYeWXmMTrP1VH8XZMOhXdE1",
      "wal": {
        "id": "wal_czDztN5eJ4r5sJ",
        "created_at": 1582461859,
        "updated_at": 1582462278,
        "user_label": "My Postman Collection Wallet",
        "balance": 19,
        "statusType": {
          "type": "wallet",
          "name": "active",
          "display_name": "Active"
        }
      },
      "wtxType": {
        "layer": "ln",
        "name": "ln_withdrawal",
        "display_name": "LN Withdrawal"
      },
      "lnTx": {
        "id": "lntx_aB5lHY5ebFtei4SOByEQ8bnP",
        "created_at": 1582462278,
        "dest_pubkey": "02c16cca44562b590dd279c942200bdccfd4f990c3a69fad620c10ef2f8228eaff",
        "payment_request": "lnbc10n1p09yafzpp5ens55wl8pfm6n2222pyyxjhx9rwcj4zl8pcyhsr2qzlklke4qfvsdq423jhxapqvehhygzyfap4xxqyz5vqcqzyssp52vyh6djmjt644fygwr54cs9vv82d2zc67tmkeun3c40ypzrvqe4srzjqt0pr36g7ke9elfvaqq3wmfey6laun0z8v0lg0nf9fdhdncxsp0y5zxkp5qqnsgqqqqqqqqqqqqq05qqrc9qy9qsqq3a4p9tvmy3sf7h2mlfpd5rcdldsyaksf8e0rk09yxtzvhcyzjrsg2janexechmzaqmnz9c7de04et7jkhmvkkjdnzn3txnz2a204ucplr595s",
        "r_hash_decoded": "cce14a3be70a77a9a94a5048434ae628dd89545f38704bc06a00bf6fdb350259",
        "memo": "Test for DOCS",
        "description_hash": null,
        "num_satoshis": 1,
        "expiry": 86400,
        "expires_at": 1582548678,
        "payment_preimage": "6239646b2f326757664d37562b34383070347475665a4d65416c504f6f622b444933314c4e6246593554553d",
        "settled": 1,
        "settled_at": 1582462278,
        "is_keysend": null,
        "custom_records": null
      },
      "passThru": {
        "method": "api"
      }
    }
  }
}
```
{% endtab %}

{% tab title="wallet\_receive" %}
```text
{
  "created_at": 1582462225,
  "id": "evt_rIZawRf4qbaPn8ie6yFdPlU",
  "event": {
    "type": "wallet",
    "name": "wallet_receive",
    "display_name": "Wallet Receive"
  },
  "data": {
    "wtx": {
      "num_satoshis": 20,
      "user_label": "Test invoice from Postman Collection",
      "created_at": 1582462225,
      "id": "wtx_mJO06R6XzkZf2cf680gEOgQF",
      "wal": {
        "id": "wal_czDztN5eJ4r5sJ",
        "created_at": 1582461859,
        "updated_at": 1582462225,
        "user_label": "My Postman Collection Wallet",
        "balance": 20,
        "statusType": {
          "type": "wallet",
          "name": "active",
          "display_name": "Active"
        }
      },
      "wtxType": {
        "layer": "ln",
        "name": "ln_deposit",
        "display_name": "LN Deposit"
      },
      "lnTx": {
        "id": "lntx_ztkK7XxfqCq3ihmhJiUhnR",
        "created_at": 1582462172,
        "dest_pubkey": "033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
        "payment_request": "lnbc200n1p09yaxupp5r7ckx99n00d2a7g8xtr8wup57w82t827kkeujsdgjyn45cjmym7sdp623jhxapqd9h8vmmfvdjjqenjdakjq5r0wd6x6ctwyppk7mrvv43hg6t0dccqzpgxqyz5vqsp5gyfwnrqnkyvxxgpww0vwsl8tfe524ggr5kngr8n8fn4vt9xl5ggs9qy9qsq42vwx9dh2n3ggrlgwqqxqq77detywruhv2s558uk3vfrumgmjfhs3y8hwtgxe7cx6svg4pr87qzfg8mgawsveqe6wn0te9d3h02fm4spxtzy5s",
        "r_hash_decoded": "1fb16314b37bdaaef90732c6777034f38ea59d5eb5b3c941a891275a625b26fd",
        "memo": "Test invoice from Postman Collection",
        "description_hash": null,
        "num_satoshis": 20,
        "expiry": 86400,
        "expires_at": 1582548572,
        "payment_preimage": "fbf2e3e943991d7d3202d061fb1dbe7afedffb4d4f29a204c624a5366e7c5706",
        "settled": 1,
        "settled_at": 1582462225,
        "is_keysend": null,
        "custom_records": null
      },
      "passThru": {
        "myVariable":"special-id",
        "ticketId":"23"
      }
    }
  }
}
```
{% endtab %}

{% tab title="wallet\_transfer\_IN/OUT" %}
```text
# Same format for wallet_transfer_in and wallet_transfer_out
# Note: 2 separate webhooks / events are created for a Wallet Transfer request
# Note: the wtx['num_satoshis'] will be positive/negative depending on debit/credit

{
  "id": "evt_NotT4h3TTgo8vmw9LlZdjp",
  "created_at": 1582471973,
  "event": {
    "type": "wallet",
    "name": "wallet_transfer_out",
    "display_name": "Wallet Transfer OUT"
  },
  "data": {
    "wtx": {
      "num_satoshis": -1,
      "user_label": "Test transfer from Postman Collection",
      "created_at": 1582471973,
      "id": "wtx_2LZhCsmKUIDgcaJQOsBF80g",
      "wal": {
        "id": "wal_czDztN5eJ4r5sJ",
        "created_at": 1582461859,
        "updated_at": 1582471973,
        "user_label": "My Postman Collection Wallet",
        "balance": 18,
        "statusType": {
          "type": "wallet",
          "name": "active",
          "display_name": "Active"
        }
      },
      "wtxType": {
        "layer": "ln",
        "name": "ln_transfer_out",
        "display_name": "Transfer Out"
      },
      "lnTx": null,
      "passThru": {
        "lnPayParams": null,
        "source_wallet_id": "wal_czDztN5eJ4r5sJ",
        "dest_wallet_id": "w_hkjS9r6mTYeABc"
      }
    }
  }
}
```
{% endtab %}
{% endtabs %}

### Paywalls

{% hint style="info" %}
The `paywall_conversion` event will fire on successful payment of a paywall, the `wallet_receive` event will also fire - because the wallet received money.
{% endhint %}

{% tabs %}
{% tab title="paywall\_created" %}
```text
{
  "id": "evt_wFexxrj7HGFdlfrbvxs6wkN",
  "created_at": 1582541374,
  "event": {
    "type": "paywall",
    "name": "paywall_created",
    "display_name": "Paywall Create"
  },
  "data": {
    "pywl": {
      "destination_url": "https://www.github.com",
      "memo": "My First Tester Paywall",
      "lnd_value": "69",
      "short_url": "03ccb",
      "lnd_expiry": 86400,
      "created_at": 1582541374,
      "updated_at": 1582541374,
      "metadata": [],
      "id": "pywl_nwmA5Nq6oD9IuK",
      "paywall_link": "https://paywall.link/to/03ccb",
      "custyDomain": {
        "domain_name": "paywall.link"
      },
      "statusType": {
        "type": "link",
        "name": "active",
        "display_name": "Active"
      },
      "paywallType": {
        "name": "basic",
        "display_name": "Basic Paywall",
        "description": "User must pay everytime the paywall is hit"
      },
      "template": null
    }
  }
}
```
{% endtab %}

{% tab title="paywall\_conversion" %}
```
{
  "created_at": 1582638979,
  "id": "evt_am119vTFxDZRbOHMy3mxBU5",
  "event": {
    "type": "paywall",
    "name": "paywall_conversion",
    "display_name": "Paywall Conversion"
  },
  "data": {
    "pywl": {
      "id": "pywl_nwmA5Nq6oD9IuK",
      "created_at": 1582541374,
      "updated_at": 1582541374,
      "destination_url": "https://www.github.com",
      "memo": "My First Tester Paywall",
      "lnd_value": 69,
      "lnd_expiry": 86400,
      "short_url": "03ccb",
      "metadata": {
        "extraAttributes": {
          "unlock_threshold": 0,
          "identifier_in_memo": false,
          "send_partial_preimage_redirect": false
        }
      },
      "paywall_link": "https://paywall.link/to/03ccb",
      "custyDomain": {
        "domain_name": "paywall.link"
      },
      "statusType": {
        "type": "link",
        "name": "active",
        "display_name": "Active"
      },
      "paywallType": {
        "name": "basic",
        "display_name": "Basic Paywall",
        "description": "User must pay everytime the paywall is hit"
      },
      "template": null
    },
    "wtx": {
      "num_satoshis": 69,
      "user_label": "Paywall Payment: 03ccb",
      "created_at": 1582638978,
      "id": "wtx_es70fgXOn9CiJkVU4NG5TSB",
      "wal": {
        "id": "w_n743yizWqe43Oz",
        "created_at": 1579001314,
        "updated_at": 1582638978,
        "user_label": "Paywall Wallet",
        "balance": 625,
        "statusType": {
          "type": "wallet",
          "name": "active",
          "display_name": "Active"
        }
      },
      "wtxType": {
        "layer": "ln",
        "name": "ln_deposit",
        "display_name": "LN Deposit"
      },
      "lnTx": {
        "id": "lntx_mjgB1kvanfkwxII7O2KDa8J",
        "created_at": 1582638941,
        "dest_pubkey": "033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
        "payment_request": "lnbc690n1p092f6app508wdlqmphj94x0se8hzezndaqkk96q4hk0n5cfn62zzhyrmfky3qdp9f4ujq3nfwfehggz5v4ehgetjypgxz7thv9kxccqzpgxqyz5vqsp5yvezsgl6k9ftweec8a04w6szy5q95da64hhj7vhks2t0chkgapms9qy9qsqv4grtk7lhqlac877vpyzvhxncwfaelf7rsf9z4w8jutkwucsexm5nz8v3szf9cpf0khp9n7ssms2zy6njsmdslh2f4j3g4lnwtnyktqpd6w0fj",
        "r_hash_decoded": "79dcdf8361bc8b533e193dc5914dbd05ac5d02b7b3e74c267a5085720f69b122",
        "memo": "My First Tester Paywall",
        "description_hash": null,
        "num_satoshis": 69,
        "expiry": 86400,
        "expires_at": 1582725341,
        "payment_preimage": "c647b4ea73c64caadfcd2adb313c15c9c508252b9cb43dbfb16481a4c59eb592",
        "settled": 1,
        "settled_at": 1582638978,
        "is_keysend": null,
        "custom_records": null,
        "passThru": {
          "userDefined": {
            "id": "03ccb",
            "utm_source": "telegram",
            "myUrlParameter": "specialVar"
          }
        }
      },
      "passThru": {
        "pywl_id": "pywl_nwmA5Nq6oD9IuK",
        "userDefined": { 
          "id": "03ccb",
          "utm_source": "telegram", //from https://paywall.link/to/03ccb?utm_source=telegram&myUrlParameter=specialVar
          "myUrlParameter": "specialVar" //from https://paywall.link/to/03ccb?utm_source=telegram&myUrlParameter=specialVar
        },
        "secondary_type": 50
      }
    }
  }
}
```
{% endtab %}
{% endtabs %}

{% hint style="success" %}
Note the `wtx['passThru']['userDefined']` variable, you can pass query string / URL parameter in directly from the paywall link as such:`https://paywall.link/to/03ccb?utm_source=telegram&myUrlParameter=specialVar`
{% endhint %}

## Special Headers

| Header | Sample Format | Description |
| :--- | :--- | :--- |
| `X-LNPay-Event` | `wallet_send` | an event from above |
| `X-LNPay-HookId` | `iwhr_TBYsAgdgeOkhfA1cb5a33szZ` | a unique ID for this webhook request |
| `X-LNPay-Signature` | `aa46ae5d2d8367aef6693063e09...` | hmac\_sha256 signature of payload, if you provide a secret |
| `User-Agent` | `LNPay-HookBot` | standard user agent |

