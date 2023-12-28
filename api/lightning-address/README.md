# Lightning Address

## Pay to Lightning Address Flow

1. Check the lightning address with the[ probe endpoint ](probe.md)to make sure it fits with your expectations
2. Execute [Pay to Lightning Address](pay-to-lightning-address.md) endpoint to actually initiate a send payment



## Receive to Lightning Address Flow

1. Create a domain in the UI that has the hostname (e.g. sats.me)&#x20;
2. [Create Lightning Address](create-lightning-address.md) using the `identifier` (e.g. tommy) as the username
   1. Specify `custy_domain_id` from 1 (above)
3. Lightning Address tommy@sats.me has been created!

