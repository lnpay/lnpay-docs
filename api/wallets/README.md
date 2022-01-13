---
description: All wallet objects are prefixed with wal_
---

# Wallets

Wallets can be created freely within LNPay.co. Different wallets provide for both organization and security.

{% code title="Wallet Object Response" %}
```
{
  "id": "wal_czDztN5eJ4r5sJ",
  "created_at": 1577600922,
  "updated_at": 1577600922,
  "user_label": "DEFAULT WALLET",
  "balance": 1000,
  "statusType": {
        "id": 200,
        "type": "wallet",
        "name": "active",
        "display_name": "Active"
    },
    "defaultLnurlpay": {
        "id": "lnurlp_6Xh2hELFFqSlKEHCbF",
        "created_at": 1642013336,
        "updated_at": 1642013336,
        "user_label": "Base lnurl-pay link",
        "lnurl_encoded": "LNURL1DP68GUP69UHKCMNSV9UJUMR0VDSKCW3CXYCNZTMKXYHHWCTVD3JHGTMHV94KCUZLX3TXC7NYWF5KYN34VE2YZKR42E3KJ6E4V4XKCNP0D3H82UNVWQHKCMN4WFK8QHEKTP5RY6Z9F3RYVU2ND3952JZRVFRQWUZJNJ",
        "lnurl_decoded": "https://cloud.lnpay.co/v1/wallet/waklp_4VlzdribN5fTAXuVcik5eMlL/lnurlp/lnurlp_6Xh2hELFFqSlKEHCbF",
        "lnurlp_minSendable_msat": 1000,
        "lnurlp_maxSendable_msat": 10000000,
        "lnurlp_short_desc": "LNURL PAY (via LNPay.co)",
        "statusType": {
            "type": "lnurl",
            "name": "lnurl_active",
            "display_name": "LNURL Active"
        }
    },
}
```
{% endcode %}

