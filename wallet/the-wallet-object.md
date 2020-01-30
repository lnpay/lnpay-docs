# The Wallet Object

Wallets can be created freely within LNPay.co. Different wallets provide for both organization and security.

{% code title="Wallet Object Response" %}
```text
{
  "id": "w_hkjS9r6mTYeABc",
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
| Wallet Admin | wa\_Opnn4kGOGBMnfCLFXtsDnjTb |
| Wallet Invoice | wi\_skllxCQI7yurKi0NCCTc0wwO |
| Wallet Read | wr\_3YgsKHplFSyhzBKNVr8tohO |

