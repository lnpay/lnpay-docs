---
description: >-
  The LnTx (Lightning Network Transaction) object is basically an object wrapper
  for an LN invoice. The LnTx endpoint will be called to check status of
  invoices (settled) and other details.
---

# LnTx \(Get Invoice Status\)

## The LnTx Object

```text
{
    "id":"lntx_82yveCX2Wn0EkkdyzvyBv",
    "created_at":1577657602,
    "ln_node_id":"lnod_2s4yfYA",
    "dest_pubkey":"02c16cca44562b590dd279c942200bdccfd4f990c3a69fad620c10ef2f8228eaff",
    "payment_request":"lnbc50n1p0qjf84pp5f70yqjjvu0z0esf7hksnca44d8j440mk5743qv70ku6jy9ewj8eqdpz23jhxapqd9h8vmmfvdjjqen0wgsxgmmrwvxqyz5vqcqzyssp583w0tugt4scyek2dat72p389lau0j8u9t5qnep29y0c32hyfn8rqrzjqt0pr36g7ke9elfvaqq3wmfey6laun0z8v0lg0nf9fdhdncxsp0y5zxkp5qqnsgqqqqqqquyqqqqqksqrc9qy9qsqzmvy83s8np7yrlqs98ge90tj3wwhfawjtq3cewv4vavmq0p5c4anhkm2aeyzjcvycttfgzwtak7nrrk6e3m3td8g4t8ha06uzzare4cqqne839",
    "r_hash_decoded":"4f9e404a4ce3c4fcc13ebda13c76b569e55abf76a7ab1033cfb73522172e91f2",
    "memo":"Test invoice for docs",
    "description_hash":null,
    "num_satoshis":5,
    "fee_msat":0,
    "expiry":86400,
    "expires_at":1577744002,
    "payment_preimage":"6631394e526f35325135563854574f316651513330527a6e4e47315630795147662f7066466e4276664a773d",
    "settled":1,
    "settled_at":1577657602,
    "is_keysend":null,
    "custom_records":null,
    "passThru":null
}
```

