# Aggeus market
Bitcoin prediction markets with non-interactive contract trading

# What is this?

Aggeus is an open protocol for building permissionless prediction markets on bitcoin. Combining ideas from DLCs, lightning, and PSBT auctions, Aggeus uses bitcoin as the only asset, does not require any other blockchains, authentication systems, or custodians (unless you count addresses encumbered by DLC-like constraints as semi-custodial), and allows anyone to create prediction markets and trade contracts in them pseudonymously.

# How does it work?

There are three explainers:

- [Protocol description](https://gist.github.com/supertestnet/be601c4fc50d0f1d9a5c7079cf3363df) - some say this one is confusing, I wrote it to help me implement it
- [Explainer](https://gist.github.com/supertestnet/7456c01f0333581794eb153f990a153d) - this one is longer but has more examples, and I think it's easier to understand
- [Diagram](https://supertestnet.github.io/aggeus_market/diagram.html) - I think it's helpful to have this open while reviewing the Explainer document

# What are the tradeoffs?

The main tradeoffs are:
1. the Oracle Problem -- oracles can do shenanigans like become an active participant in the market and only announce results where they win, or they can shut down without warning, leaving users stuck with no way to unilaterally recover their funds
2. the Liveness problem -- the coordinator cosigns every trade, so if he shuts down or has a temporary internet outage, all trading halts til he returns (though even if he disappears permanently, users can still exit from their positions if the oracle still announces a result)
3. the Free Option Problem -- if the coordinator decides to become an active participant in the market, he can do shenanigans like hold someone's trade offer in a pending state til he learns more about where the market seems headed, then accept or decline their offer with the knowledge he gained in the interim
