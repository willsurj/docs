---
title: Distributed Exchange
---


In addition to supporting the issuing and movement of [assets](./assets.md), the DigitalBits network also acts as a decentralized **distributed exchange**
of any type of asset that people have added to the network. Its ledger stores both balances held by user accounts and offers that user accounts make to buy or sell assets.

## Offers
An account can make offers to buy or sell assets using the [Manage Offer](./list-of-operations.md#manage-offer) operation.
In order to make an offer, the account must hold the asset it wants to sell. Similarly, the account must trust the issuer of the asset it's trying to buy.

When an account makes an offer, the offer is checked against the existing orderbook for that asset pair. If the offer crosses
an existing offer, it is filled at the price of the existing offer. Let's say that you make an offer to buy 10 XDB for 2 BTC. If an offer already
exists to sell 10 XDB for 2 BTC, your offer will take that offer--you'll be 2 BTC poorer but 10 XDB richer.

If the offer doesn't cross an existing offer, the offer is saved in the orderbook until it is either taken by another offer,
taken by a payment, canceled by the account that created the offer, or invalidated because the account making the offer no longer has the asset for sale.

Offers in DigitalBits behave like limit orders in traditional markets. 

For offers placed at the same price, the older offer is filled before the newer one.  

## Orderbook
An **orderbook** is a record of outstanding orders on the DigitalBits network. This record sits between any two assets--in this case,
let's say the assets are sheep and wheat. The orderbook records every account wanting to buy sheep for wheat on one side and every account wanting to sell sheep for wheat on the other side.

Some assets will have a very thin or nonexistent orderbook between them. That's fine: as discussed in greater detail below, paths of orders can facilitate exchange between two thinly traded assets.


## Passive offers
**Passive offers** allow markets to have zero spread. If you want to offer USD from anchor A for USD from anchor B at a 1:1 price, you can create two passive offers so the two offers don't fill each other.

A passive offer is an offer that does not take a counteroffer of equal price. It will only fill if the prices are not equal.
For example, if the best offer to buy BTC for XDB has a price of 100XDB/BTC, and you make a passive offer to sell BTC at 100XDB/BTC, your passive offer *does not* take that existing offer.
If you instead make a passive offer to sell BTC at 99XDB/BTC it would cross the existing offer and fill at 100XDB/BTC.


## Cross-asset payments
Suppose you are holding PointsA and want to buy something from a store that only accepts PointsB. You can create a payment in
DigitalBits that will automatically convert your PointsA into PointsB. It goes through the PointsA/PointsB orderbook and converts your PointsA at the best available rate.

You can also make more complicated paths of asset conversion. Imagine that the PointsA/PointsB orderbook has a very large spread
or is nonexistent. In this case, you might get a better rate if you first trade your PointsA for PointsC and then sell that PointsC for PointsB.
So a potential path would be 2 hops: PointsA->PointsC->PointsB. This path would take you through the PointsA/PointsC orderbook and then the PointsC/PointsB orderbook.

These paths of asset conversion can contain up to 6 hops, but the whole payment is atomic--it will either succeed or fail. The payment sender will never be left holding an unwanted asset.

This process of finding the best path of a payment is called **pathfinding**. Pathfinding involves looking at the current
orderbooks and finding which series of conversions gives you the best rate. It is handled outside of DigitalBits Core by something like Frontier.


## Preferred currency
Because cross-asset payments are so simple with DigitalBits, users can keep their money in whatever asset they prefer to hold. **Preferred currency** creates a very flexible, open system. 

Imagine a world where, anytime you travel, you never have to exchange currency except at the point of sale. A world where
you can choose to keep all your assets in, for example, Apple stock, cashing out small amounts as you need to pay for things. Cross-asset payments make this world possible.



