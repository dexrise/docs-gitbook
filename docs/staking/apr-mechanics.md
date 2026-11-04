# APR Mechanics

Staking rewards on DEXRise are calculated using the **APR model** — the Annual Percentage Rate. Understanding two rules about how DEXRise applies APR will let you predict your rewards precisely:

1. The APR is annualized over a **full 365-day year** — not limited to the staking pool's duration.
2. Rewards are **simple interest** — they are **not compounded**.

## Rule 1 — APR over a full year

APR expresses the yearly reward rate. On DEXRise, the stated APR is defined across **365 full days**, regardless of how long the staking pool itself runs. A pool that operates for 90 days does not compress the yearly rate into those 90 days — your rewards accrue at the pro-rated daily rate for the time your tokens are actually staked.

**The daily reward rate:**

```text
Daily reward rate = APR ÷ 365
```

## Rule 2 — simple interest, not compounded

DEXRise staking uses **simple interest**: rewards are always calculated **on the amount you originally deposited** — not on your deposit plus previously earned rewards.

This means your reward rate stays constant and predictable: it does not accelerate over time, because earned rewards do not feed back into the reward base. If you want your rewards to earn rewards, you can [claim them and re-deposit them yourself](staking-types.md).

## Worked example

You deposit **1,000 tokens** into a pool with an APR of **100%**, and leave them staked for **30 days**:

```text
Daily reward rate = 100% ÷ 365 ≈ 0.274% per day
Daily reward      = 1,000 × 0.274% ≈ 2.74 tokens
Reward after 30 days = 1,000 × 100% × 30/365 ≈ 82.19 tokens
```

The deposit itself remains 1,000 tokens, and the reward base stays 1,000 tokens for the whole period — no compounding applies.

{% hint style="info" %}
This example uses hypothetical numbers for illustration. The actual APR of a pool is shown in the [Staking Panel](overview.md#the-staking-panel) — for example, the first DXR staking round runs at **100% APR** (see the [DXR Staking Event](../dxr-token/staking-event.md)).
{% endhint %}

## Claiming rewards

Regardless of contract type, rewards are claimable at any time through the [Staking Panel](overview.md#the-staking-panel):

* **[Flexible](staking-types.md#flexible-staking)** — claim rewards anytime; your deposit is also withdrawable anytime.
* **[Locked](staking-types.md#locked-staking)** — claim rewards anytime while your deposit stays committed until the term ends; claimed rewards can also be re-deposited.
