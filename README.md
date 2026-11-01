# iaas hosting: DDoS Protection Built In, Pooled Cloud Pricing, and How to Pick the Right Plan

IaaS hosting means renting raw compute, storage, and network capacity instead of whole managed servers — you get virtual machines or bare metal you configure yourself, and the provider handles the hardware, the network, and the building it all sits in. Most people searching for it are comparing two things: what the resources actually cost, and what happens when something attacks their server. Those two questions are exactly where Sharktech differs from the usual options, so that's where this article focuses: its three product lines (SmartVPS, OpenStack-based cloud, and bare-metal servers), current prices, the billing quirks that don't show up in the headline numbers, and the situations where you'd be better served elsewhere.

> **Quick pick:** If you want DDoS protection included rather than sold as an add-on, with a price you can predict, Sharktech is worth a close look — its OpenStack cloud starts at $39/month, the SmartVPS pool starts at $7.95/month, and annual billing cuts either by half. 👉 [Check Sharktech's current cloud, VPS and server pricing](https://bit.ly/SharKtech)

## What you're actually choosing when you pick an IaaS host

The provider owns the hardware and the network; you own everything you put on it. That's the shared responsibility model, and misreading it is how most cloud incidents start. It also explains why IaaS pricing varies so wildly: you're comparing port speeds, storage tiers, traffic allowances, and — the part most comparison posts skip — what happens when your server gets attacked.

That last point matters more than it sounds. A capable volumetric attack typically lands in the 5–20 Gbps range, which is enough to knock over most budget hosts that offer little or no mitigation. The big clouds mitigate well but charge separately for serious protection. This is the specific gap Sharktech built its business around since 2003: it operates its own network (AS46844, peering at major internet exchanges) and includes 60 Gbps of DDoS mitigation per IP address on every plan, from the cheapest VPS up. Enterprise deployments can scale that to 1 Tbps. Nothing about it is an upsell; it's baked into the base price, and attacks don't generate extra mitigation charges.

## Sharktech's three IaaS product lines, and the full plan list

Sharktech splits its IaaS hosting into three lines, all available in the same five data center locations: Los Angeles, Las Vegas, Denver, Chicago, and Amsterdam.

**Public Cloud** (OpenStack-based, pay-as-you-go) is the core cloud offering. Every plan includes a fixed resource allocation; usage beyond it bills hourly at published rates:

| Plan | CPU | RAM | SSD Storage | Bandwidth | Starting Price | Order |
| --- | --- | --- | --- | --- | --- | --- |
| Small | 4–16 cores | 8–32 GB | 100 GB+ | 5 TB | from $39/mo | [ Check current price](https://bit.ly/SharKtech) |
| Medium | 16–32 cores | 32–64 GB | 500 GB+ | 10 TB | from $99/mo* | [ Check current price](https://bit.ly/SharKtech) |
| Large | 32–64 cores | 64–128 GB | 1,000 GB+ | 15 TB | from $249/mo* | [ Check current price](https://bit.ly/SharKtech) |
| Enterprise | 64+ cores | 128+ GB | 5,000 GB | 20 TB | from $499/mo* | [ Check current price](https://bit.ly/SharKtech) |
| Custom | You decide | You decide | You decide | You decide | Quoted | [ Request a quote](https://bit.ly/SharKtech) |

\* The $39 Small price is confirmed on the current official cloud page; the higher-tier starting prices come from third-party reviews, so treat them as ballpark until the configurator shows your exact quote. Because it's a resource pool rather than fixed VM shapes, an allocation like 8 vCPU / 8 GB RAM / 300 GB SSD can be split across multiple virtual machines however you like. Public Cloud is also available hourly, so short-term projects don't lock you into a month.

**Dedicated Cloud** runs on the same OpenStack platform with fixed billing: you prepay a flat monthly price for a set allocation, and nothing overages automatically. The company's own framing: "If you pay for 8 cores, you get 8 cores. No more, no less." If your workload is steady and you want a predictable invoice, this is the sane choice over Public Cloud's metered model.

**Bare-metal servers** all ship with a 10 Gbps port, 300 TB of monthly bandwidth, and 2 TB of NVMe M.2 storage, with listed configurations starting at **$219/month** before upgrades. Stock machines ship within about 24 hours; fully custom builds (your CPU, memory, drive layout, network interfaces, even OS deployment) take one to two weeks. Entry-level DDoS-protected dedicated servers go lower on the company's regional order page — a Los Angeles Dual Xeon E5-2670v2 with 64 GB RAM and 1 TB NVMe has been listed at $129/month, and some configurations in that same catalog carry free setup. If you need GPUs, the entry bare-metal platform advertises scaling up to 8 GPUs on Dual EPYC hardware with 256 GB RAM standard.

## SmartVPS: one pool, many VMs, and a 50% annual discount

SmartVPS is Sharktech's pooled VPS product, and the official page is clear about the starting allocation: **$7.95/month for 2 vCPU + 4 GB RAM**, which includes 40 GiB of NVMe storage, 4 TB of monthly transfer, and one IPv4 address. The pool scales up to 128 vCPU / 256 GB RAM, and you can carve it into as many virtual machines as the resources allow, each deployable in a different city. IPv6 addresses are free; extra IPv4s (1–65, or up to 128 on request), storage at $0.01 per GiB per month, and up to 300 TB of additional traffic are all added from the order form.

The pricing lever worth knowing about is billing cycle. Discounts apply automatically and are prepaid:

| Billing cycle | Discount |
| --- | --- |
| Monthly | list price |
| Quarterly | 25% off |
| Semi-annually | 35% off |
| Annually | 50% off |

Applied to the starting pool, the annual rate works out to roughly **$3.98 per month-equivalent** — about $47.76 for a full year of a Xeon Gold-backed environment with NVMe storage, a 10 Gbps port, and 60 Gbps DDoS protection per IP included. One caution before committing to a year: Sharktech has a strict no-refund policy. HostAdvice's review notes that all payments — including renewals — are non-refundable, with no free trial; genuine billing errors can be disputed within 30 days of the invoice and, if accepted, are credited to the account rather than refunded. If you're unsure whether the platform suits you, start monthly. 👉 [See SmartVPS pricing with the annual discount applied](https://bit.ly/SharKtech)

## The DDoS math: why "included" changes the comparison

This is the part most IaaS comparisons gloss over, so here's the concrete version. On Sharktech, every IPv4 address on every plan carries 60 Gbps of mitigation at no extra cost, with filtering happening in-network near the source thanks to its exchange-point peering — the company's own pages are explicit that its infrastructure was built around DDoS protection rather than having it bolted on later. Capacity attacks (UDP floods and amplification), protocol attacks like SYN floods, and application-layer attacks are all covered, and there's no per-attack or per-GB scrubbing fee.

Compare that to the hyperscaler route: AWS Shield Standard is free but shallow, and AWS Shield Advanced starts at around $3,000 per month. Mid-market VPS providers commonly cap protection at 10–20 Gbps and charge $5–15/month extra for it. Whether Sharktech's approach is right for you depends on your threat profile, but for game servers, public APIs, and anything else that attracts attacks as a routine cost of being online, the included mitigation is the single biggest pricing differentiator in this comparison.

## Hidden limits and billing details to check before ordering

A few things only surface in the FAQ pages and reviews, and each one can change your decision:

- **Resource ceilings are not spending caps.** On Public Cloud, Small, Medium, and Large plans have resource ceilings (for example, hourly usage can top out at 4 extra CPU cores at $0.0025/hr, 4 GB of RAM at $0.0035/hr, and storage up to 1,200 GB NVMe / 2,400 GB SSD / 4,800 GB HDD), but Sharktech's own page states plainly that these ceilings are not monetary spending caps. Traffic is the sharp edge: it's billed at $0.002/GB with no ceiling at all. Inbound traffic is free, but a runaway outbound transfer will still bill.
- **Windows licensing is bring-your-own.** You supply your own Windows key or buy one from Sharktech; there's no pre-licensed Windows image hand-holding. Standard Linux and FreeBSD images are supported too, and each VM in a pool can run a different OS.
- **API access is IP-restricted.** OpenStack API access is limited to approved source IPs by default — good security, but worth knowing if your CI pipeline rotates egress addresses.
- **No refunds, no trial.** Covered above, but it belongs in every ordering decision.
- **cPanel is an optional add-on** if you want it, not bundled.
- **Payment is flexible.** Visa, Mastercard, Discover, PayPal, Alipay, Apple Pay, Google Pay, bank transfer, SEPA, ACH — even checks and money orders if you're feeling nostalgic.

## How this stacks up against the hyperscalers

Here's the honest version of that comparison, with the company's own claims labeled as claims:

- **Price:** Sharktech advertises 50–80% savings versus AWS, Azure, and GCP for comparable resources, and guarantees at least 20% less. That's a vendor claim, but the components are verifiable — officially published egress at $0.002/GB, free ingress, and flat monthly VPS pricing with no overage charges on the VPS line. Third-party reviews also report a generous included egress allowance (5,000 GB) before that rate kicks in, though the official pages don't spell out the number.
- **Lock-in:** the cloud platform is OpenStack, so there are no proprietary APIs; you get RESTful endpoints for compute (Nova), block and object storage (Cinder and Swift), networking (Neutron), and identity (Keystone), and you can upload and download VM images freely. Leaving a hyperscaler's proprietary ecosystem is usually the expensive part; leaving OpenStack is just a migration.
- **Scale and ecosystem:** if you need serverless, managed Kubernetes add-ons, or a hundred ancillary managed services, AWS or Azure will fit better — Sharktech gives you VMs, storage, networking, and bare metal, and expects you to run the rest.
- **Resilience:** the platform advertises 99.999% uptime with automatic failover across triple-redundant NVMe storage, and nodes are interconnected with multiple 40G/100G links. It's a vendor claim without published SLA credit terms in the material reviewed, so weight it accordingly.

For a specific data point: one user review published on Sharktech's site describes a 15-year IT veteran moving workloads from AWS and Azure to Sharktech's Dedicated Cloud and calling the price "shockingly reasonable." It's a brand-published testimonial, so take it with the appropriate grain of salt — but the direction of the complaint it solves (unpredictable egress-heavy bills) matches what the published rates actually show. 👉 [Compare Sharktech's cloud plans against your current bill](https://bit.ly/SharKtech)

## Who Sharktech fits — and who should look elsewhere

The strongest matches, based on verified specs and third-party testing:

- **Game server operators.** Minecraft, CS:GO, ARK and the like attract attacks as a matter of course. LowEndTalk users running game servers for a year have reported absorbing 3–8 Gbps attacks without interruption, and the IXP-based filtering keeps latency low for players.
- **Teams escaping hyperscaler billing.** If your monthly bill is dominated by egress fees and DDoS add-ons, the flat-rate model with $0.002/GB egress is materially cheaper.
- **Experienced sysadmins who want control.** HostAdvice scored the VPS line 9.3/10 overall, with 9.6 for features and 9.5 for performance — genuine Xeon Gold CPUs, 6,000+ random IOPS, and 5+ Gbps network speeds in independent testing, plus a 12-minute average ticket response.

The poor matches are just as clear. There's no managed tier, so if you don't want to administer your own servers, a managed host will serve you better even at a higher price. The interface assumes real server experience — HostAdvice flags it as potentially overwhelming for beginners. And the no-refund policy means experimentation isn't free. Developers who just need a $5 sandbox to break things occasionally should also look at cheaper commodity VPS offers elsewhere, since they're unlikely to use the DDoS protection that justifies the price difference.

## FAQ

**Does the 60 Gbps DDoS protection cost extra?** No. Every plan, including the cheapest SmartVPS allocation, includes 60 Gbps of mitigation per IPv4 address in the base price, with no per-attack fees. It can be upgraded for larger deployments.

**Can I deploy IaaS resources hourly instead of monthly?** Yes, on Public Cloud. It supports hourly billing for testing and short-term projects; Dedicated Cloud is prepaid monthly by design.

**What happens if I exceed my Public Cloud allocation?** Usage above the included resources bills hourly at published rates (for example, $0.0025/hr per extra CPU core), and traffic bills at $0.002/GB. Remember the ceilings limit resources, not spending.

**Do I need to bring my own Windows license?** Yes. Windows VMs require either your own license key or one purchased from Sharktech. Linux and FreeBSD images carry no such requirement.

**Is there a free trial or money-back period?** No. Payments are non-refundable, and there's no free trial — a billing-error dispute within 30 days of an invoice, if accepted, results in account credit.

## The short version for your situation

Running something that gets attacked regularly — game servers, public APIs, a community with enemies — the included 60 Gbps mitigation alone justifies the price, and annual SmartVPS billing brings the entry pool down to about $3.98 per month-equivalent. Steady production workloads where you want a predictable invoice: Dedicated Cloud. Need raw hardware, GPUs, or a 10 Gbps port with 300 TB of bandwidth: bare metal from $219/month, or the $129 entry config if your workload fits it. Purely experimenting or learning: start with Public Cloud by the hour so a mistake costs cents, and move to a committed plan once you know your real resource usage. 👉 [Pick your plan and deploy from Sharktech's order page](https://bit.ly/SharKtech)
