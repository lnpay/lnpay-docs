# The Wallet Object

Wallets can be created freely within LNPay.co. Different wallets provide for both organization and security.

{% code title="Wallet Object Response" %}
```text
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
}
```
{% endcode %}

### Wallet Access Keys \(WAK\)

LNPay.co implements a role-based access control system. Each wallet has keys associated with it that can be used to do access certain functions. These keys are used in most wallet functions. The keys are generated on wallet create via the API or dashboard. They are only available via the API in the response from wallet create

You should see a table similar to the one below in your wallet dashboard. Note the `wa` `wi` `wr` prefixes

| Permission | Wallet Access Key \(WAK\) |
| :--- | :--- |
| Wallet Admin | waka\_kqvaiFFl4Tjq4rgAXlwsu6 |
| Wallet Invoice | waki\_Q2XHBIfEAN33mLlwdYvusN6Q |
| Wallet Read | wakr\_wIdkxqZqkRJd6MhWlsoH1yi |
| Wallet LNURL Withdraw |  |

{% hint style="danger" %}
They key prefixes were changed 2020/23/02 to better describe them. 

Example:  `wi` to `waki` Wallet ID: `w_` to `wal_`
{% endhint %}



