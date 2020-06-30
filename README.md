# aa-dex
Simplified odex AA (https://github.com/byteball/odex-wallet) to allow onchain cheap exchange

https://explorer.obyte.org/#shkss2TAIsClVM91aYvrwgvwDp3FZSDm8Orq9ieqnFY=

## Usage
Default case is order creation, fields `buy_asset`,`price` must be filled. `address` is optional, will receive bounce fees and be able to cancel order.

A `lock` to avoid order cancelation could be added at creation. Add param with `lock` = timestamp where the lock should begin.

To match an existing order, send `trade` = 1 and `id` = id of the order you want to match.

To see opened orders, check state vars.

To cancel an order, send `cancel` = 1 along with the id.

## Fees
Each operation costs 2 KB. When AA is filled to 10 MB, it changes the fee to 0,2 KB until their balance falls to 50KB.

## Limitations
Multi signature units are not allowed.
