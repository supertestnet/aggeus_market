# Aggeus market
Bitcoin prediction markets with non-interactive contract trading

# What is this?

Aggeus is an open protocol for building permissionless prediction markets on bitcoin. Combining ideas from DLCs, lightning, and PSBT auctions, Aggeus lets anyone build market infrastructure similar to popular platforms like Fanduel or Polymarket. The methods outlined here use bitcoin as the only asset, do not require any other blockchains, authentication systems, or custodians (unless you count addresses encumbered by DLC-like constraints as semi-custodial), and they allow anyone to create markets and trade contracts in them pseudonymously.

The main tradeoffs are: (1) the Oracle Problem -- oracles can do shenanigans like becoming an active participant in the market and only announcing results that make themselves win, or they can shut down without warning, leaving users stuck with no way to unilaterally recover their funds (2) there is a non-custodial coordinator who cosigns every trade, and if he shuts down, all trading halts (though users can still exit from their positions if the oracle sticks around) (3) the Free Option Problem -- if the Coordinator decides to become an active participant in the market, he can do shenanigans like holding someone's trade offer in a pending state til he learns more about where the market seems headed, then accept or decline their offer with the knowledge gained in the interim
