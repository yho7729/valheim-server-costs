# valheim dedicated server host: what it really costs, which setup fits your crew, and how to get a persistent world running without the usual headaches

Searching for a valheim dedicated server host usually means one of three things: your friend group outgrew the "host on my PC" option, your world keeps dying when the host logs off, or you want something that stays online around the clock without eating your own electricity. All three point to the same fork in the road — self-host for free, rent a game-panel server by the slot, or lease an actual dedicated machine. This guide walks through what each route costs in practice, where the hidden annoyances are, and why a bare-metal provider like Sharktech is worth considering for the third option — including their full current plan list, from a $129/mo Los Angeles dedicated box to a $3.98/mo VPS.

> **Quick picks**
> - Just want a persistent world for 3–5 friends and don't want to touch a terminal? A game-panel host is the easy route (verified prices in the comparison below).
> - Comfortable with basic Linux/Windows admin and want a machine that's yours alone, with DDoS protection included? A Sharktech dedicated server starts at **$219/mo** on current listings, with an LA config listed at **$129/mo** at the time of writing — [👉 check Sharktech's current bare-metal lineup](https://bit.ly/SharKtech)
> - Purely broke and patient? Self-hosting on your own hardware is free. The trade-offs are below.

## What a Valheim server actually needs (spoiler: less than you think)

Valheim is light on hardware but heavier on network than most people expect. Iron Gate never published official dedicated server requirements, so the honest answer comes from real examples: the Eurogamer setup guide ran fine with 3 players on a Ryzen 5 3600, 16 GB RAM, and a 50 Mbps down / 10 Mbps up connection. Reddit players have reported running servers on old dual-core boxes. The game caps co-op at 10 players, and the developer recommends 3–5 for the intended experience.

Three things matter more than raw CPU:

1. **Stable upload bandwidth.** One player with a bad connection drags down the whole group's latency.
2. **A machine that stays on.** The whole point of a dedicated server is persistence — the world runs whether or not anyone's online, and in-game time pauses when nobody is connected, so your base doesn't get raided while everyone sleeps.
3. **Ports that actually work.** Steam backend uses 2456–2457 by default (the game uses the specified port *and* port+1), and both need forwarding or an alternative backend (more on crossplay below).

Because the requirements are modest, almost any modern VPS can technically run Valheim. What separates providers is uptime, network quality, protection, and how much control you get.

## Your three options, compared

Every serious answer to "where should I host my Valheim server" lands on one of these. Here's the honest breakdown, with verified numbers wherever they exist.

**1. Self-host on your own PC or an old machine — free.** Install the "Valheim Dedicated Server" tool from Steam (every owner of the game has it), edit the startup script, forward your ports. It works, it's free, and a 3–5 player group can run fine on modest hardware. The costs are indirect: the host machine has to stay powered on (electricity and bandwidth caps apply), and performance can suffer if you play and host on the same box. Iron Gate itself points players who don't want to deal with any of this toward paid rental hosts, naming G-Portal on the game's store page.

**2. Game-panel hosting — monthly flat rate, one-click setup.** Companies like Apex Hosting (a sponsor of the most-watched Valheim 1.0 server tutorial) and G-Portal (officially recommended by Iron Gate) give you a web panel, instant deployment, automatic backups, and support staff who know what a `.fwl` file is. As of the October 2026 snapshot of Apex's Valheim page, their memory-based plans renewed at **$7.99/mo (2 GB), $14.99/mo (4 GB), and $27.99/mo (8 GB)**, with a 25% discount advertised on first orders; a German host, Agrar Chaoten, listed a Valheim plan at **$9.12/mo**. Apex offers a 7-day money-back window and a 99.99% uptime SLA — consumer-friendly terms a bare-metal provider won't match. This is the right choice if you've never administered a server and don't want to learn.

**3. A dedicated server or beefy VPS — monthly flat rate, total control.** This is where Sharktech lives. Nobody hands you a Valheim panel; you get bare hardware with a fat network pipe and set the game up yourself. The payoff: the machine is yours alone (no noisy neighbors), you can run other things on it alongside the game server, and the DDoS protection is built into the network rather than bolted on. If a 10-player Valheim world is all you'll ever run, option 2 is cheaper and easier. If you're the group's resident tech person — or you want to host a modded setup, multiple game servers, or a community's worth of services on one box — option 3 makes sense.

## Sharktech's full plan list (snapshot: pricing pages current as of January 2026)

Every bare-metal server includes a **10Gbps network port, 300TB of monthly bandwidth, 2TB NVMe M.2 storage, and free setup**, backed by a **99.99% uptime guarantee**. Sharktech protects all servers against DDoS attacks up to 60 Gbps automatically, with a cloud-based upgrade option up to 100 Gbps. Five data center locations are available: Los Angeles, Las Vegas, Denver, Chicago, and Amsterdam.

One honest caveat before the table: Sharktech's published pricing has some spread depending on which page you land on. Their current product pages list configurations "from $219/month before upgrades," while their legacy pricing page (updated January 31, 2026) showed the lineup below, and a Los Angeles special was listed at $129/mo on their regional page. **Treat everything in this table as a snapshot and confirm the live price before ordering.**

| Plan / Configuration | CPU | RAM | Storage | Price (monthly) | Order |
| --- | --- | --- | --- | --- | --- |
| LA Special — Dual Xeon E5-2670v2 | Dual Xeon E5-2670v2 | 64 GB | 1TB NVMe | $129 | [ Order the LA config](https://bit.ly/SharKtech) |
| Bare-metal 48-core | 48 × 2.5 GHz | configurable | 2TB NVMe + bays | $189 | [ Order the $189 config](https://bit.ly/SharKtech) |
| Bare-metal 80-core | 80 × 2.40 GHz | configurable | 2TB NVMe + bays | $209 | [ Order the $209 config](https://bit.ly/SharKtech) |
| Bare-metal 80-core expanded | 80 × 2.40 GHz | configurable | 2TB NVMe + 8× M.2 / 4× U.2 bays | $249 | [ Order the $249 config](https://bit.ly/SharKtech) |
| Bare-metal 128-core | 128 × 2.0 GHz | configurable | 2TB NVMe + 14× U.2 bays | $449 | [ Order the $449 config](https://bit.ly/SharKtech) |
| High-density tier | configuration not listed | configurable | 14× U.2 bays | $599 | [ Order the $599 tier](https://bit.ly/SharKtech) |

If a whole dedicated box is more machine than you need, their VPS line runs from a 2-core/4GB plan at **$3.98/mo** up to 32 cores/64GB at $48.98/mo — the entry tiers are plenty for a Valheim world with a handful of players, and the VPS rides the same DDoS-protected network. [👉 See Sharktech's VPS pricing and locations](https://bit.ly/SharKtech)

A few things to know about how Sharktech handles custom builds: in-stock systems ship within 24 hours as a target, custom-specified hardware takes longer depending on component availability, and the team confirms timelines before you commit. Every server also comes with a /29 IPv4 block (5 usable IPs), free IPv6 allocation, and 24/7/365 human support. HostAdvice's 2026 review scored them 9.3 overall, with their test environment (2TB NVMe, 10G shared unmetered port) completing CPU stress benchmarks with no crashes or throttling.

## The costs and fine print nobody puts on the pricing page

Most "best Valheim hosting" lists stop at the monthly number. Here's what actually determines your total cost of ownership, verified against Sharktech's terms and the alternatives.

**Sharktech has no refund guarantee.** Their policy is explicit: all payments are nonrefundable, including setup fees and monthly charges (setup is currently free on listed configs, which softens the blow). Billing disputes must be raised within 30 days, and successful ones come back as account credit. That's a real difference from consumer-friendly game hosts — Apex, for instance, offers a 7-day money-back guarantee — so with Sharktech you're committing to the month. Payment options are broad: credit card, PayPal, wire transfer, Western Union, and Alipay.

**Run the annual math against your actual group size.** That $129 LA server is $1,548 a year. Compare that with the verified renewal prices from the panel-hosting side: Agrar Chaoten's Valheim plan at $9.12/mo works out to roughly $109 a year, and Apex's 8 GB plan renews at $27.99/mo, or about $336 a year. Even Apex's top-shelf EX series (16 GB DDR4, 4 dedicated vCores on a Ryzen 9 5900X) renews at $71.99/mo — around $864 a year. The dedicated box only wins when you divide its cost across a bigger group, run multiple services, or value having hardware that's entirely yours. If Valheim is the only thing the server will ever do and your group is small, be honest with yourself about that math.

**Watch the renewal price, not the teaser.** Apex's own numbers show the pattern: a 4 GB plan starts at $8.99/mo and renews at $14.99 — a 67% jump, putting the three-year total at $534. First-order discounts are great for month one; budget for month thirteen.

**Self-hosting isn't actually free either.** A machine running 24/7 draws power around the clock, and if your home connection has a data cap, 300TB-of-bandwidth-class traffic will find it fast. Eurogamer's guide flags both costs directly. Free still usually beats $10 a month for casual groups, but "free" deserves an asterisk.

**One structural advantage worth noting:** Sharktech doesn't charge hourly, and there's no per-slot fee — the box is yours to load up. A 10-player Valheim server uses a fraction of even the smallest dedicated machine, which is exactly why the community trick of "one server, many uses" (game server plus a file backup target plus a Discord bot host) exists.

## Setting up Valheim on a rented server: the steps and the traps

If you go the Sharktech route, deployment takes an evening at most. The official Iron Gate guide covers the essentials; here's the workflow with the traps highlighted, because these are the things that eat people's weekends:

1. Install the game server tool. On Windows, grab "Valheim Dedicated Server" from Steam under Tools; on a headless Linux box, use SteamCMD. Linux additionally needs the `libpulse-dev` package, and very old distros need Docker (the server requires GLIBC_2.29+).
2. Edit the startup script — `start_headless_server.bat` on Windows, `start_server.sh` on Linux. The parameters live on line 7: `-name`, `-port` (default 2456), `-world`, `-password`. Back up the script first: **Steam updates reset the original file**, but the Steam shortcut only launches the original filename, so keep a copy and know which one you're editing.
3. Password rules: it must differ from the server name and world name. Removing the password line entirely runs an open server — for a public box, use something strong.
4. Port handling. Steam backend needs 2456–2457 open and forwarded; a rented server skips the router part but you'll still open firewall rules. **If you add the `-crossplay` argument (PlayFab backend), no port forwarding is needed at all** — traffic goes through relay servers, and console players can join too. That single flag solves the most common "my friends can't connect" complaint.
5. Start it and watch for "Game server connected." Then stop it properly with CTRL+C — closing the window with the X can leave the server running in the background, which will confuse you later when the port seems occupied.
6. Manage players through the files in the save directory: `adminlist.txt`, `bannedlist.txt`, and `permittedlist.txt`. Fair warning on the last one: adding anyone to the permitted list bans everyone *not* on it. It's a whitelist, and people trip over it constantly. In-game, F5 opens the console for kick/ban commands and F2 shows player IDs.

Backups: the server keeps short and long backups you can configure, which is your rollback path if a world update goes sideways. Existing worlds migrate by copying the `.db` and `.fwl` files from your local `IronGate\Valheim\worlds` folder to the same path on the server. One extra warning if you're moving a world created before Valheim 1.0: the save conversion that happens on first load is irreversible, so keep an untouched copy of the original files before uploading anything.

## Why built-in DDoS protection matters for a persistent server

A Valheim server that's listed publicly and runs 24/7 is findable, and findable game servers eventually get hit — whether it's a disgruntled ex-member or random port-scanning script kiddies. This is Sharktech's home turf: their entire network is built around DDoS mitigation, every server gets automatic protection against attacks up to **60 Gbps**, and there's a cloud-based upgrade path to 100 Gbps for serious cases. Game-panel hosts do advertise protection too — Apex claims coverage up to 300 Gbps on its plans — so treat this as table stakes and weigh it alongside the other network factors below.

The network side generally is the strongest argument here. Every bare-metal box gets a 10Gbps port and 300TB of monthly bandwidth as standard, the company operates five data centers on a multi-homed redundant network (Las Vegas alone peers with Comcast, GTT, NTT, China Telecom, and several other carriers — a detail that matters if any of your players connect from Asia), and HostAdvice's review noted sub-millisecond network latency in their testing. There's a public looking glass on their site if you want to check latency from your own connection before committing — worth doing, since ping to the server is what your whole group will feel.

## Who should skip Sharktech

To be straight about it: if you've never edited a config file or opened a firewall port, a bare-metal box will feel like being handed an engine block when you wanted a bicycle. One-click game-panel hosts exist precisely for that audience — G-Portal is Iron Gate's own recommendation, Apex handles deployment, updates, and backups from a web panel with 24/7 chat support across 13 available Valheim locations worldwide, and Agrar Chaoten's $9.12/mo plan covers the basics at a lower renewal than either. Paying for convenience there is money well spent.

Sharktech also won't fit if you want hourly billing or a short commitment you can walk away from — no refund means each month is a real commitment. And if your group is 3–5 people with no modding ambitions, the entry VPS or a game host covers you; the $449+ multi-core beasts on this page are for people running communities, not a longhouse.

## FAQ

**How many players can a Valheim dedicated server hold?** Ten is the hard co-op cap, and Iron Gate recommends 3–5 for the intended experience. Any Sharktech plan, including the $3.98 VPS, clears the hardware bar for 10 players easily.

**Do I need port forwarding?** Only on the Steam backend (ports 2456–2457 by default). The `-crossplay` backend uses relays and needs no forwarding, and a rented server eliminates the home-router side of the problem entirely.

**What ports and settings do I edit first?** Line 7 of the startup script: name, port, world, password. Everything else — raid frequency, resource rates, backups, hiding from the public list — is documented in the PDF manual that ships alongside the server files.

**Does Sharktech offer a trial or refund?** No. Payments are nonrefundable per their terms, so use their public looking glass and network tests to sanity-check latency to your region before you pay.

**How much RAM does a Valheim server need?** For a 10-player vanilla world, panel hosts consider 8 GB the comfortable tier and 2–4 GB the minimum; Sharktech's cheapest VPS ships 4 GB, and every dedicated plan starts far above that. Heavy modpacks are where the bigger allocations earn their keep.

## The bottom line, by situation

- Never administered a server, 3–5 friends, want it working tonight → use a game-panel host. Verified renewal prices run from $9.12/mo (Agrar Chaoten) to $27.99/mo for Apex's 8 GB tier, both with money-back windows Sharktech can't match.
- Tech-comfortable, want a box you fully control, run mods or other services, or tired of your home machine humming 24/7 → a dedicated server is the play. The LA Dual Xeon config at $129/mo is the value pick for a Valheim-centered box; the 48-core $189 tier makes sense if the server will do double duty. Start here: [👉 browse Sharktech's bare-metal servers and current pricing](https://bit.ly/SharKtech)
- Tightest possible budget → self-host for free and accept the electricity, the port forwarding, and the fact that your world lives on a machine you also use for other things.

Before you click order on any of these, confirm two things: the live price (Sharktech's listed configs have shifted between pages, and the snapshot here dates to early 2026) and your ping to the data center you're choosing — five minutes with their looking glass beats a month of explaining lag to six Vikings.
