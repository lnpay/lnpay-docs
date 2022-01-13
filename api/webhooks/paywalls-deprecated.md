# Paywalls (deprecated)

### Paywalls

{% hint style="info" %}
The `paywall_conversion` event will fire on successful payment of a paywall, the `wallet_receive` event will also fire - because the wallet received money.
{% endhint %}

{% tabs %}
{% tab title="paywall_created" %}
```
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

{% tab title="paywall_conversion" %}
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
