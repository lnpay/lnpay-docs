---
description: >-
  This tutorial will show you how to connect a Voltage node to LNPay and connect
  your existing wallets to it
---

# Connecting Voltage Node

## Voltage node connection info

![](../.gitbook/assets/nodes.voltage.cloud\_node\_c3246b21-4ae3-4fa8-8333-4c7959e0952dN\_lnd\_connect.png)![](<../.gitbook/assets/Add Your Node to get started! 2022-06-02 12-35-05.png>)

## Listeners

The listeners connect to the streaming gRPC endpoint of the node in order to know when payments have been received AND sent in order to update wallet balances and things. Make sure these are checked.

If they are not checked - try Stop / Start listener

{% hint style="warning" %}
Check this often! If your node is down for a while, you must reconnect these!
{% endhint %}

![](<../.gitbook/assets/RPC Listeners 2022-06-02 12-36-41.png>)

## Moving wallets to new node

![](<../.gitbook/assets/LN Node Wallet 1 2022-06-02 12-39-32.png>)

Use this form in order to change the wallet that the node uses.

* The sats will be transferred to the new node via keysend. If keysend fails, everything will fail and you can try again
