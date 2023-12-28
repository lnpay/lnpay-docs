# List Nodes

{% swagger method="get" path="v1/nodes" baseUrl="https://<yourdomain>/" summary="List Lightning Nodes tied to this account" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```javascript
[{
    "id": "lnod_bkdaitqin2l54cbuvq",
    "created_at": 1640704004,
    "alias": "alice",
    "onchain_confirmed_sats": 992363,
    "onchain_unconfirmed_sats": 0,
    "onchain_total_sats": 992363,
    "onchain_nextaddr": "bcrt1qh47g9j0rw2uawzdel5pcmyp5yx60np0v6u6uue",
    "network": "regtest",
    "default_pubkey": "028e74f2598db804d8ae1319a5140679bd1df10811a33cbb82a183035110343760",
    "uri": "028e74f2598db804d8ae1319a5140679bd1df10811a33cbb82a183035110343760@192.168.69.1:9735",
    "host": "192.168.69.1",
    "rpc_port": 10001,
    "rest_port": 8081,
    "ln_port": 9735,
    "fee_wallet_id": "wal_CJrX2fy3d4JcwB",
    "keysend_wallet_id": "wal_L0ZqpDG4Nl5jp",
    "passThru": {
        "rest_last_check": 1640707773
    }
}]
```
{% endswagger-response %}
{% endswagger %}

