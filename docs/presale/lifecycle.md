# Presale Lifecycle

Every presale event on DEXRise follows the same clear path — from the moment a project lists its sale to the moment the event settles. This page walks through each stage in order.

## Stage 1 — Listing and setup

The project lists its presale on DEXRise:

* The project provides the **quantity of tokens allocated for sale**.
* The presale runs on one of the two [contract types](contract-types.md) — immediate or pending delivery.
* Listing fees and requirements are covered in [Presale Listing](../listing/presale-listing.md).

## Stage 2 — The sale window

The presale is live, and investors can buy through the [Buy Panel](overview.md#the-buy-panel):

* Every purchase executes **directly on-chain**.
* On **immediate delivery** contracts, purchased tokens are delivered at the moment of purchase.
* On **pending delivery** contracts, purchases are recorded and tokens are delivered after the event ends.

## Stage 3 — How the event ends

The presale ends when **whichever of these comes first** occurs:

| End condition | Meaning |
| --- | --- |
| **The period expires** | The event reaches its scheduled end date with quantity still available |
| **The quantity sells out** | Every allocated token is sold before the end date is reached |

There is no in-between state: the event ends on time with tokens remaining, or it ends early because it sold out.

## Stage 4 — Settlement

Once the presale has fully ended, three settlement rules apply:

| Item | Settlement rule |
| --- | --- |
| **Raised funding** | Delivered to the project team **after the presale period has fully ended** — never earlier |
| **Unsold tokens** | Delivered to the project team |
| **Pending deliveries** | Investors on pending-delivery contracts receive their tokens |

## The full picture

```text
Listing & setup ──► Sale window ──► Event end ──► Settlement
(project lists       (on-chain        (period ends      (funding and unsold
 its sale quantity)   purchases)       OR sellout)       tokens go to the team)
```

{% hint style="info" %}
Want to see these stages applied to a real event? The [DXR Presale Event](../dxr-token/presale-event.md) page documents dates, pricing, allocation and the end conditions for DEXRise's own presale.
{% endhint %}
