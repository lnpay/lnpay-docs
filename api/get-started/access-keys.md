# API Keys & Access Keys

## API Keys: Secret Acess Key vs Public Access Key

The _Secret Access Key_ or `sak_`and the _Public Access Key_ or `pak_`have distinct permission roles to accommodate many Lightning Network use cases client side and server side.&#x20;

**Secret Access Key:** The `sak_` is intended to be used SERVER SIDE only, and is meant to be as secret as secret keys can get. This key has permission to perform ALL requests across the API.&#x20;

{% hint style="info" %}
If you intend to use the LNPay API only server side, you can disregard the Wallet Access Keys section below.
{% endhint %}

**Public Access Key:** The `pak_` is intended to be used CLIENT SIDE only, and is intended to be paired with a Wallet Access Key (`wak`) The `pak_` is essentially serves as an account identifier, while the Wallet Access Keys provide a level of control over wallets. This dynamic is helpful for when you want to have wallets perform certain functions client side, but do not want to expose your entire LNPay account.

The Public Access Key cannot perform any LIST functions (list wallets, list transactions).

## Wallet Access Keys

Each wallet has role-based permissioned access keys associated with it. The keys are generated on wallet create via the API or dashboard. They are only available via the API in the response from wallet create‌, and cannot be retrieved later via the API.

The purpose of these keys are to restrict use with client side applications. Browser side, in mobile apps, consumer hardware, etc.&#x20;

{% hint style="info" %}
**These keys ARE intended to be exposed client side!**&#x20;

**These keys should be used with the `pak_` Public Access Key**
{% endhint %}

| Role                  | Prefix  | Permissions                                                                                                       | Example            | Notes                                                   |
| --------------------- | ------- | ----------------------------------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------- |
| Wallet Admin          | waka\_  | <p>wallet_deposit</p><p>wallet_read</p><p>wallet_transfer</p><p>wallet_<em>tx</em>_read</p><p>wallet_withdraw</p> | waka\_OkdGALaQ.... |                                                         |
| Wallet Invoice        | waki\_  | <p>wallet_deposit</p><p>wallet_<em>tx</em>_read</p>                                                               | waki\_oSjzkjVR...  |                                                         |
| Wallet Read           | wakr\_  | <p>wallet_read</p><p>wallet_<em>tx</em>_read</p>                                                                  | wakr\_h1JTla...    |                                                         |
| Wallet LNURL Withdraw | waklw\_ | <p>wallet_<em>public</em>_withdraw</p><p>wallet_read</p><p>wallet_withdraw</p>                                    | waklw\_1Lldqo...   | This key does not need an API key in order to withdraw! |

## Permission Breakdown

{% tabs %}
{% tab title="Server Side " %}
This table breaks down when it is appropriate to use the API Key and Wallet Key combo

```
https://api.lnpay.co/v1/<Wallet Key>?access-token=<API Key>
```

| Function                                                       | API Key |    Wallet Key   |
| -------------------------------------------------------------- | :-----: | :-------------: |
| [Create Wallet](../wallets/create.md)                          |  `sak_` |       N/A       |
| [Retrieve Wallet](../wallets/retrieve.md)                      |  `sak_` |      `wal_`     |
| [Generate Invoice](../wallet-transactions/generate-invoice.md) |  `sak_` |      `wal_`     |
| [Pay Invoice](../wallet-transactions/pay-invoice.md)           |  `sak_` |      `wal_`     |
| [Keysend](../wallet-streaming-payments/keysend.md)             |  `sak_` |      `wal_`     |
| [Transfer](../wallet-transactions/transfers.md)                |  `sak_` |      `wal_`     |
| [Transactions](../wallet-transactions/)                        |  `sak_` | `wal_` optional |
{% endtab %}

{% tab title="Client Side" %}
This table breaks down when it is appropriate to use the API Key and Wallet Key combo

```
https://api.lnpay.co/v1/<Wallet Key>?access-token=<API Key>
```

| Function                                                       | API Key |     Wallet Key    |
| -------------------------------------------------------------- | :-----: | :---------------: |
| [Create Wallet](../wallets/create.md)                          |   N/A   |        N/A        |
| [Retrieve Wallet](../wallets/retrieve.md)                      |  `pak_` | `waka_`or `wakr_` |
| [Generate Invoice](../wallet-transactions/generate-invoice.md) |  `pak_` | `waka_`or `waki_` |
| [Pay Invoice](../wallet-transactions/pay-invoice.md)           |  `pak_` |      `waka_`      |
| [Keysend](../wallet-streaming-payments/keysend.md)             |  `pak_` |      `waka_`      |
| [Transfer](../wallet-transactions/transfers.md)                |  `pak_` |      `waka_`      |
| [Wallet Transactions](../wallet-transactions/)                 |  `pak_` | `waka_`or `wakr_` |
{% endtab %}
{% endtabs %}

