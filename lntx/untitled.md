---
description: >-
  The LnTx object is basically an object wrapper for an LN invoice. The LnTx
  endpoint will be called to check status of invoices (settled) and other
  details.
---

# LnTx \(Lightning Invoice\) Object

#### Response

```text
{
    "id": "lntx_UlXwgqNd2tl41ZrnWPlx7s6w",
    "created_at": 1582297054,
    "dest_pubkey": "033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
    "payment_request": "lnbc200n1p0ylm77pp5384pxkzd5m536nluwf2364r2qmsnh7kzyj0wrv3urze5vllmfmxqdp623jhxapqd9h8vmmfvdjjqenjdakjq5r0wd6x6ctwyppk7mrvv43hg6t0dccqzpgxqyz5vqsp56f338cr57djg5zsagrnxd80krpnqny0k3wldk5ctruwgftk9stnq9qy9qsqju8kfgplphd0jum5z8xs4fdjrv2wfrgang2pr5zvan3psfu0ff7krqgwfmp4sywyz97lp0lrlezyvqxhjtvy0gjz0ld5g4ha2udjurqqy2eny5",
    "r_hash_decoded": "89ea13584da6e91d4ffc72551d546a06e13bfac2249ee1b23c18b3467ffb4ecc",
    "memo": "Test invoice from Postman Collection",
    "description_hash": null,
    "num_satoshis": 20,
    "expiry": 86400,
    "expires_at": 1582383454,
    "payment_preimage": null,
    "settled": 0,
    "settled_at": null,
    "is_keysend": null,
    "custom_records": null
}
```

