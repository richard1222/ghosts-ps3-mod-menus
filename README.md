# Call of Duty: Ghosts — PS3 Mod Menus & Modding Tools: The Complete Guide

*Every publicly released Call of Duty: Ghosts (2013) SPRX mod menu, RTM tool, modded EBOOT and unlock tool for PlayStation 3 — with creators credited, compatibility notes, and source links.*

Ghosts is the odd one out in this guide series. World at War and MW2 had huge GSC `patch_mp.ff` scenes; MW3 and Black Ops 2 went SPRX. Ghosts went SPRX too — but it never grew the same free-menu ecosystem. Read any NextGenUpdate thread from 2016 and the same answer repeats: the good Ghosts non-host menus were **paid**, the free SPRX selection was thin, and a lot of the scene's energy went into **RTM tools, anti-ban EBOOTs, and paid recovery services** instead. This guide catalogs everything that actually existed, flags what could not be verified, and explains how to run it on a modern DEX setup.

> ⚠️ **Ban warning, in the scene's own words:** multiple NGU posters from the era warn that SPRX menus on Ghosts got accounts banned *fast*, even with an anti-ban EBOOT ("you will still get banned really fast with a SPRX menu"). Treat anything in this guide as offline/private-match tooling unless you accept the risk. Nothing here has been re-tested on real hardware for this guide.

---

## Quick Facts

| | |
|---|---|
| **Game** | Call of Duty: Ghosts (Infinity Ward, released November 5, 2013) |
| **Final title update** | **1.16** — verified three ways: the RPCS3 wiki's netplay table lists game version 1.16, PS3 update-PKG listings offer "Update 1.16" for both regions, and every late-era NGU Ghosts menu/EBOOT thread targets 1.16. (An early guess of 1.15 is wrong.) |
| **US disc** | BLUS31270 |
| **US PSN** | NPUB31301 · NPUB50021 (Digital Hardened Edition) |
| **EU/AU disc** | BLES01945 · BLES01948 (two IRD-listed pressings) |
| **EU PSN** | NPEB01832 · NPEB01835 |
| **JP** | BLJM61125 · BLJM61126 (disc) · NPJB00528 (PSN) |
| **Demos** | NPEB90534 · NPUB91004 |
| **Title IDs that do NOT check out** | BLES01946 and BLES01947 appear in *no* game-ID listing found (RPCS3 wiki, IRD lists, retailer data). They look unused — if a download claims them, be suspicious. |
| **Modding shape** | SPRX menus + modded/debug EBOOTs + RTM/RPC tools + recovery services. **No GSC `patch_mp.ff` scene.** |
| **Era** | Most releases target TU 1.16 and date from 2014–2017. Early tools (1.04–1.07 era) are historical only. One genuinely new menu (Vortex) appeared in **2025**. |
| **Best-positioned setup** | DEX CFW (e.g. Rebug D-REX). The classic Ghosts scene was DEX-first; several key releases are DEX-only. |

---

## How Ghosts Modding Works (and Why There's No GSC Scene)

WaW and MW2 modding revolved around swapping a `patch_mp.ff` fastfile full of GSC scripts. That never happened for Ghosts on PS3, for practical reasons:

- Ghosts runs on a newer iteration of the IW engine, and its PS3 patch data is signed/encrypted in a way that killed the casual fastfile-swap workflow the older games allowed. Nobody built a public `patch_mp.ff` editing scene around it.
- What the console *could* do was run **debug (DEX) EBOOTs** and load **SPRX plugins** — native C++ modules injected into the game process. So Ghosts modding became: a modded EBOOT that loads an SPRX from `/dev_hdd0/tmp/`, or an external PC tool talking to the console.
- Host functions that GSC used to provide were instead reached through **RPC (remote procedure calls)** from RTM tools over CCAPI (CEX) or TMAPI (DEX) — RatchetBooty's tool added RPC host functions in its 2.5.0 update, for example.
- Ghosts was even picky about *how* an SPRX gets loaded: seb5594's **SPRX Elf Builder v1.02** changelog notes it bundles Therifboy's newer `ingame_loader` specifically because it "fixes some Games like CoD Ghosts." If a generic loader EBOOT black-screens on Ghosts, that loader quirk is the historical reason why.

### The four things that actually existed

1. **SPRX menus** — host menus (SSM, Sapphire) and non-host/off-host menus (Frost Engine, Desire Engine, Paradox). The non-host aimbot tier was mostly **paid**.
2. **RTM/RPC tools** — PC programs (CCAPI/TMAPI) editing memory live: stats, unlock all, name/clan changers, class editors, ESP/no-recoil toggles, Extinction editing. This category is *bigger* than the SPRX category for Ghosts.
3. **Modded EBOOTs** — anti-ban debug EBOOTs with built-in non-host mods and an SPRX plugin slot (Luckeyy's were the standard).
4. **Recovery/unlock services & tools** — paid lobbies and recovery tools (GamerChoice, xKtF) that set stats, prestige, squad points and Extinction progress for you — a real chunk of the Ghosts "scene" was commercial.

### Host vs non-host, in one paragraph

A **host** menu only works when you are the match host (or in a private match) — it runs game-world commands. A **non-host / off-host** menu works in any lobby because it only touches your own client (aimbot, ESP/red boxes, no recoil, UAV). Ghosts' prestige items were the paid non-host menus; the free releases skew host-side or buggy, which era threads complain about constantly.

### Firmware compatibility at a glance

| Setup | What works |
|---|---|
| **DEX CFW (Rebug D-REX etc.)** | Everything in this guide, including the DEX-only EBOOTs and DEX SPRX builds. This was the scene's home platform. |
| **CEX CFW** | Menus/tools explicitly marked CEX or CEX/DEX (SSM menu, RatchetBooty, FMT Eternity). DEX-only EBOOTs will **not** work. |
| **HEN (HFW)** | Very little classic-era support — those menus predate HEN. Known HEN evidence: **Vortex (2025)**, showcased on HEN 3.3.4 / HFW 4.92, and Brazilian **Destiny SPRX** install tutorials aimed at HEN users. Assume a 2014–2016 DEX/CEX SPRX does **not** load on HEN unless its own page says so. |

---

## SPRX Menu Catalog

### Host SPRX menus

#### SSM Ghosts Menu
- **Creator:** Credits listed on the release thread: **StankyModz**, **Mango_Knife**, **SouthSideModderᴼᴳ / ImSSM**. (The NGU poster, martin_sari, explicitly states he did *not* make it — he reposted it.)
- **What it does:** Host SPRX mod menu for multiplayer. Per the thread, it works online only when you are host. Controls: open **R3**, scroll **R1/L1**, select **X**, back/exit **Square**.
- **Compatibility:** TU **1.16**, **CEX/DEX**. SPRX goes to `/dev_hdd0/tmp/`, EBOOT to `/dev_hdd0/game/<REGION>/USRDIR/`.
- **Source:** [NGU release thread](https://nextgenupdate.com/forums/ghosts-mods-cheats-glitches/838311-call-duty-ghosts-116-cexdex-sprx-mod-menu.html) · Showcase: https://www.youtube.com/embed/9G-6McpOewY
- **Download:** Behind the NGU thread (login-gated) and inside the Se7enSins mega-pack (below).
- **Status:** The best-documented *free* Ghosts SPRX menu. Thread posters repeat the warning that SPRX menus on Ghosts ban quickly even with anti-ban; the recommended pairing was Luckeyy's EBOOT (below).

#### Sapphire V1
- **Creator:** **MegaMister** (credited on the NGU thread that repackaged it with an anti-ban EBOOT).
- **What it does:** Host SPRX menu — posters note it must be opened in a private match or while host.
- **Compatibility:** TU **1.16**. The repackaged release is **DEX only** because of the converted EBOOT it ships with.
- **Source:** [NGU thread (Sapphire + Luckeyy anti-ban EBOOT combo)](https://nextgenupdate.com/forums/ghosts-mods-cheats-glitches/856660-116-ghost-sprx-menu-anti-ban-eboot-2.html)
- **Download:** NGU thread (login-gated); also in the Se7enSins mega-pack as `Sapphire_V1`.
- **Status:** One video listing from the era tags Sapphire V1 with "(Instant ban !)" — treat as offline-only.

### Non-host / off-host SPRX menus

#### Frost Engine (v4.9)
- **Creator:** **Unconfirmed.** A 2015 showcase description carries a credit line naming OLDSCHOOLMODZ, but in context that reads as the showcaser's credit block, not authorship. Do not treat it as verified.
- **What it does:** Non-host SPRX menu with **aimbot**. Version **4.9** is the one in the widely mirrored 2015 showcase title ("[PS3/Ghosts/1.16] SPRX Frost Engine Non-Host 4.9").
- **Compatibility:** TU **1.16**. Loaded via a plugin EBOOT (Luckeyy's EBOOT thread names Frost Engine as a supported example).
- **Source / showcase:** https://www.youtube.com/watch?v=vJh4TigFZbs
- **Download:** Originally via NGU per the video description (link not retrievable now); also in the Se7enSins mega-pack as `Ghost Frost Engine`.
- **Status:** Era users reported it worked but was **buggy** ("it doesn't function properly but its still usable" — NGU, Jan 2016).

#### Desire Engine
- **Creator:** **Unclear** — no authorship could be verified from a primary source.
- **What it does:** **Paid** non-host SPRX menu. In January 2016, NGU regulars described it as the *only* released non-host SPRX menu for Ghosts they knew of — and it was not free.
- **Compatibility:** TU **1.16** era; loaded via plugin EBOOTs (Luckeyy names it alongside Frost Engine).
- **Source:** Discussion in [NGU "Best free .sprx non-host menu for Ghost 1.16" thread](https://nextgenupdate.com/forums/ghosts-modding-questions/865899-best-free-sprx-non-host-menu-ghost-116-mp.html/search) and Luckeyy's EBOOT thread (below).
- **Download:** Was sold privately; no public download verified. **Not** in the Se7enSins pack under this name.
- **Status:** Paid/private — listed here because any honest catalog of Ghosts non-host menus has to start with it.

#### Paradox (Ghosts build)
- **Creator:** The **Paradox** menu brand; a Ghosts-specific author credit could not be verified from its own release page.
- **What it does:** **Paid** non-host aimbot menu. In January 2017 Luckeyy named exactly two purchasable non-host aimbot options for Ghosts: "Purchase Paradox or FMT Eternity."
- **Compatibility:** TU **1.16** era.
- **Source:** Luckeyy's posts in the NGU Eternity/non-host discussion threads (see Sources).
- **Download:** A file named `paradox_crack_ghosts` circulates in the Se7enSins mega-pack — i.e. a **cracked** copy of the paid menu is what survives publicly.
- **Status:** Paid originally; cracked copy in the pack. No standalone free release verified.

#### Vortex — by xiBryan (2025)
- **Creator:** **xiBryan**.
- **What it does:** A **new** Ghosts SPRX menu released in the modern era and sold through the Eternal Team shop. The 2025 showcase (by Virus Mike) demonstrates it running on current setups.
- **Compatibility:** Shown running on **HEN 3.3.4 (HFW 4.92)** and modern CFW (Evilnat D-REX 4.92, Rebug D-REX) — the only Ghosts SPRX with verified modern HEN support found.
- **Source / showcase:** https://www.youtube.com/watch?v=Z2nn2HHzzOc (purchase link is in that video's description, on the Eternal Team shop).
- **Download:** Paid, via the Eternal Team shop.
- **Status:** The key "2020s activity" find for Ghosts: the scene isn't entirely frozen in 2016.

### Other SPRX menus (survive mainly via the mega-pack)

These menus are confirmed to exist as files in the Se7enSins mega-collection's Ghosts section, but standalone release pages with verified authorship could not be found for them. They are listed so the catalog is complete — treat every detail beyond the filename as **unverified**.

| Menu (pack filename) | Notes |
|---|---|
| **Genusion V1.3** | Pack marks it "[Latest Version]". Creator unclear. |
| **Destiny SPRX** (`Ghosts Destiny SPRX`) | Brazilian YouTube install tutorials (channel: Projeto Hacker Mods / [SMDC] HORNET) walk through installing it on **HEN** — part 1: https://www.youtube.com/watch?v=LMPlp-MQNSg . Creator unclear. |
| **Poltergeist SPRX** (`Ghost Poltergeist SPRX`) | No standalone release page found. Creator unclear. |
| **Rebound SPRX** (`Rebound_Ghosts_SPRX`) | No standalone release page found. Creator unclear. |
| **Reflex Engine** (`ReflexEngineGhosts`) | Ghosts build of the multi-CoD Reflex Engine family. Ghosts-specific version/creator details unverified. |
| **Rezzurection** (`Ghosts Rezzurection`) | No standalone release page found. Creator unclear. |
| **Pepitax (Ghosts build)** (`Ghost Pepitax`) | Ghosts entry from the Pepitax menu line, which also has AW/BO3 builds and an all-CoD pack. Ghosts-specific details unverified. |
| **Kebab V2 (Ghosts build)** (`Kebab V2 Ghost`) | Ghosts entry from the Kebab Engine line (also AW/BO2/BO3). Ghosts-specific details unverified. |
| **Eternal Paste 2.5** (`Eternal_Paste_2.5_GHOST`) | Creator unclear. |
| **Inphnect Pak (multi-CoD)** (`Multicod Inphnect Paks`) | Inphnect's multi-game pak line (also BO1/BO2/MW3 entries in the same collection); the Ghosts build's contents are unverified. |

---

## Extinction Mode

There is **no dedicated Extinction-only SPRX menu** for Ghosts on PS3 — that search came up empty across NGU, Se7enSins, ConsoleCrunch, YouTube and GitHub. Extinction modding arrived through three other doors:

- **RatchetBooty RTM Tool** (below) — Extinction prestige/level selector built in.
- **ExIIL Multitool** (below) — dedicated Extinction section: Extinction stats, Level 31, Extinction Mods, and Extinction Host Mods.
- **Luckeyy's anti-ban EBOOT** (below) — explicitly noted as fine for "MULTIPLAYER AND EXTINCTION."
- **Recovery services** — xKtF's NGU service sold Extinction prestige/teeth/stats packages alongside MP unlocks: [NGU service thread](https://nextgenupdate.com/forums/ghosts-lobbies-services/713234-openxktfs-ghosts-recovery-servicestatssquad-pointsunlock-all-extinction-29.html).

> ⚠️ **Trap:** the well-known "Extinction trainer" on 360haven is **Xbox 360 only** (.xex) — it has nothing to do with PS3.

---

## RTM / RPC Tools

RTM (real-time modding) tools run on a PC and edit the console's memory over **CCAPI** (for CEX) or **TMAPI** (for DEX). For Ghosts this category is larger and better documented than the SPRX category.

#### Eternity — by FMT (French Modding Team)
- **What it is:** A **paid RTM tool — not an SPRX.** This is the single most-misreported fact about Ghosts modding; era NGU threads correct it explicitly ("Yes but that isn't SPRX. It's an RTM menu."). Luckeyy's own recommendation for non-host aimbot on Ghosts was "Paradox or FMT Eternity."
- **Versions:** Sold in **Full** and **Lite** editions; video titles from the era read "Eternity Full/Lite [1.16/PS3] DEX + CEX."
- **Compatibility:** TU **1.16**, DEX + CEX.
- **Source:** Sold via FrenchModdingTeam; discussed across NGU Ghosts threads (see Sources). One NGU poster in the SSM thread directs buyers there directly for "a Good mod menu without ban."
- **Status:** Paid; the co-host lobbies sold by services like GamerChoice were run on Eternity.

#### Ghosts RTM Tool w/ Aimbot — by RatchetBooty
- **Creator:** **RatchetBooty**.
- **What it does:** The era's flagship free RTM tool. Started in the TU **1.06** era and updated to **v2.5.3**. Host mods, **RPC** host functions (added in 2.5.0), Extinction prestige/level selector, unlock all, reset stats, class-name changer. The 2.5.3 **aimbot** requires client 0 and a DEX connection.
- **Compatibility:** **CEX/DEX** (CCAPI/TMAPI).
- **Source:** [NGU release thread](https://nextgenupdate.com/forums/ghosts-modding-tools/707043-ghosts-rtm-tool-waimbot-106-ratchetbooty-cexdex-updated-253a-13.html)
- **Status:** Best-documented free Ghosts RTM tool.

#### ExIIL Multitool (CoD RTM Tool v5.0) — Ghosts module
- **Creator:** **ExIIL**.
- **What it does:** One multi-CoD tool; the Ghosts module covers: stats editing, **Fast Stats**, Unlock All, Extinction Stats, name/clan-tag changer, a full class editor, and an Extinction tab (stats, Level 31, Extinction Mods, Host Mods), plus RPC/CBUF host functions.
- **Source:** [Feature list (Scribd)](https://www.scribd.com/document/698694609/ExIIL-Multitool-Feature-List)
- **Status:** The most feature-complete Ghosts RTM option on paper, including the deepest Extinction support of any tool found.

#### ZER0x1337's Ghost RTM Tool (V2.0, 2022)
- **Creator:** **ZER0x1337**.
- **What it does:** Non-host RTM tool: unlock all camos, max level, set prestige, clan tag, name changer, Box ESP, Glow ESP, no recoil, 3rd person.
- **Source / download:** [GitHub repo](https://github.com/Zer0x1337/ZER0x1337s-Ghost-RTM-PS3) (created 2022-11-20; distributed as a release — the README notes the *source code* itself was not posted, it was put to a Discord vote).
- **Status:** The most modern free RTM release for Ghosts, and the only Ghosts-specific GitHub project of substance found.

#### DLC Camo Customizer — by Pyrex BLJ
- **What it does:** RTM tool for applying/customizing DLC camos on Ghosts. **PS3 only.**
- **Source:** [CabConModding thread](https://cabconmodding.com/threads/dlc-camo-customizer.3008/)

#### Named but unverified RTM tools
- **YAGT 1.07.3** — named by users in an NGU help thread alongside other 1.07-era tools. (The expansion "Yet Another Ghosts Tool" is a guess by analogy to similar tool names — **not verified**.)
- **"Call Of Duty Ghosts Tool 1.07" by ImSooCool** — same situation: named in-era, no release page retrieved. TU 1.07-era, historical only.

---

## Unlock / Stats / Recovery Tools & Services

- **Gamer Choice Ghosts Recovery Tool — by Luckeyy (iamLuckeyy7).** A paid recovery tool sold directly (his EBOOT thread ends: "PM ME IF YOU WOULD LIKE TO PURCHASE GAMER CHOICE GHOSTS RECOVERY TOOL"). His **GAMERCHOICE™** shop on NGU sold full Ghosts recovery packages with PS3→PS4 transfer: [shop thread](https://nextgenupdate.com/forums/ghosts-lobbies-services/915580-gamerchoice-productions-ghosts-shop-ps3ps4-transfer-trusted-staff-5.html).
- **xKtF's Ghosts Recovery Service** — NGU service selling stats, squad points, unlock all, and Extinction packages (linked in the Extinction section above).
- For free DIY stat/unlock editing, the RTM tools above (RatchetBooty, ExIIL, ZER0x1337) all cover it — no standalone free "stats editor" program separate from them was found.

---

## EBOOTs, Loaders & Builder Tooling

#### Luckeyy 1.16 Anti-Ban DEX EBOOTs + SPRX plugin (the standard loader)
- **Creator:** **Luckeyy (iamLuckeyy7)**.
- **What it is:** Region-free **1.16 debug EBOOTs, DEX ONLY**, in several variants: built-in non-host mods (anti-ban, no recoil, steady aim, red boxes, advanced UAV; later variants add laser, glow players, and a "real wall hack"), and variants with an **SPRX plugin slot** — rename your menu SPRX to **`Mod_Menu.sprx`** or **`Ghosts.sprx`** (per variant) and it loads at boot. His thread names Desire Engine and Frost Engine as example SPRX to load this way.
- **Anti-ban ritual (from the thread):** load the game **offline**, use PSNinja and PSNPatch, sign in via the XMB, then wait **10–15 seconds** before pressing Play Online.
- **Source:** [NGU release thread](https://nextgenupdate.com/forums/ghosts-mods-cheats-glitches/858210-call-duty-ghosts-116-updated-modded-anti-ban-dex-eboot-sprx-plugin.html)
- **Status:** The pairing most era Ghosts SPRX setups actually used. **DEX only — will not work on CEX or HEN.**

#### SPRX Elf Builder v1.03 — by seb5594
- **What it does:** The DIY route: a PC GUI that patches a decrypted EBOOT ELF (using Therifboy's `ingame_loader`) so it loads a named SPRX from `/dev_hdd0/tmp/`, after which you resign the EBOOT (CEX or DEX) with a resigner such as TrueAncestor. Its **v1.02** update specifically adopted the newer loader because it "fixes some Games like CoD Ghosts."
- **Source:** [NGU resource thread](https://nextgenupdate.com/forums/ps3-mods-cheats/748626-sprx-elf-builder-v103-ps3-plugins-11.html)
- **Note:** Closed-source; a modern reverse-engineering write-up of how it works (and a warning about running random scene executables) is at https://NotNite.com/blog/ps3.

#### V7UZ 1.04 PKG + debug EBOOT (early era)
- An early-release-era NGU thread distributing a TU **1.04** PKG with a working debug EBOOT — of historical interest only; everything later requires 1.16.
- **Source:** [NGU thread](https://nextgenupdate.com/forums/ghosts-mods-cheats-glitches/696648-call-duty-ghosts-104-pkg-w-working-eboot.html)

#### Bulk packs & installers
- **Se7enSins "Ultimate PS3 Mod Menu, Package & Tools Mega Collection"** — a currently maintained (updated 2026) mega-pack whose Ghosts section contains 14 items: Eternal Paste 2.5, Genusion V1.3, Frost Engine, Pepitax, Poltergeist, Destiny SPRX, Rezzurection, Kebab V2, the multi-CoD Inphnect Paks, the Paradox crack, Rebound, Reflex Engine, Sapphire V1, and the SSM menu. For most of those menus this pack is now the *only* surviving public source. Download is via the thread's download button: [Se7enSins thread](https://www.se7ensins.com/forums/threads/release-ultimate-playstation-3-ps3-mod-menu-package-tools-mega-collection.1931291/).
- **Zeam's 100+ SPRX Mod Installer PKG** — a PS4-themed one-click SPRX installer with **DEX and HEN** builds, still updated in 2026 (showcase: https://www.youtube.com/watch?v=gKpFuDtXtDc). It covers many CoD titles; whether its current build includes Ghosts menus specifically could **not** be confirmed from the showcase text — check the app's game list before relying on it.

---

## Open Source & Developer Resources

Ghosts has almost no open-source scene — set expectations accordingly:

- **ZER0x1337's Ghost RTM Tool** (above) lives on GitHub, but as a *release* repo; its source was not posted.
- **No open-source Ghosts SPRX menu source** was found on GitHub despite targeted searching. Ghosts SPRX development stayed closed and, at the top end, paid.
- **Ghosts 1.16 Offsets & Addresses Collection — by ItsJordanModz** (NGU): the era's public dev resource for building your own tool/menu — function addresses (TOC `0xA7F3C8`), offsets, and credits to Mango_Knife, Seb5594, VezahHFH, Bad Luck Brain, One, SC58, Shark, Jo-Milk, and Choco. [NGU thread](https://nextgenupdate.com/forums/ghosts-mods-cheats-glitches/901435-ghosts-offsets-addresses-collection-116updating.html)
- **Why no GSC sources:** Ghosts does use IW-engine scripting internally, but with no public fastfile workflow on PS3 there was never a GSC menu scene to open-source. RTM tools reached host functions through **RPC/CBUF calls** instead.

---

## Installation (DEX — e.g. PS3 Slim on Rebug 4.84.2 D-REX)

This is the standard Ghosts SPRX install, matching how the era's releases were packaged:

1. **Update Ghosts to 1.16.** Everything current is TU-locked to 1.16 — an SPRX or EBOOT built for 1.16 will freeze or black-screen on any other TU.
2. **Back up your original EBOOT** from `/dev_hdd0/game/<TITLEID>/USRDIR/EBOOT.BIN` (e.g. `BLUS31270` or `BLES01945`).
3. **Copy the menu SPRX to `/dev_hdd0/tmp/`** using a file manager (multiMAN / webMAN). The **filename matters**: Luckeyy's plugin EBOOTs look for exactly `Mod_Menu.sprx` or `Ghosts.sprx` depending on the variant; other menus ship with their own required name. A wrong name = the menu silently never loads.
4. **Install the matching DEX EBOOT** into `/dev_hdd0/game/<TITLEID>/USRDIR/`, overwriting `EBOOT.BIN`. It must be a **DEX (debug) EBOOT for TU 1.16** — this is the #1 failure cause in every CoD SPRX scene: a CEX EBOOT on DEX firmware (or vice versa) black-screens.
5. **Launch the game** and open the menu with its combo (SSM menu: **R3**; scroll R1/L1, X to select, Square to back out).
6. **Going online (era anti-ban routine):** start the game offline → run PSNinja and PSNPatch → sign in through the XMB → wait 10–15 seconds → then choose Play Online. Even then, era posters report Ghosts banned SPRX users quickly — use a throwaway account/ID if you test this at all.

### Failure modes (from era threads)

| Symptom | Likely cause |
|---|---|
| Black screen / kicked back to XMB at launch | EBOOT firmware-type mismatch (CEX vs DEX), or EBOOT built for the wrong TU |
| Game loads, menu never opens | SPRX filename doesn't match what the EBOOT looks for, SPRX not in `/dev_hdd0/tmp/`, or the EBOOT has no plugin loader at all |
| Menu opens offline but not online | It's a **host** menu — most only function when you're host or in a private match |
| Freeze at the Ghosts logo | SPRX built for a different TU than the installed game update |
| Menu "loads" on HEN but nothing works | Expected for most classic releases — they were built for DEX/CEX CFW. Verified HEN options are Vortex (2025) and the Destiny SPRX tutorials |

---

## Name Collisions & Traps

- **"WeAreGhosts SPRX"** (by Santo Oscuro & OmarGhost, on ConsoleCrunch/PlayerSquared) is a **GTA V** mod menu (BLES01807/BLUS31156) — *not* Call of Duty: Ghosts. The name fools every search engine.
- **360haven's Extinction trainer** is **Xbox 360 only**.
- **"Ghost Watchers"** GitHub projects are an unrelated PC co-op horror game.
- **"Ghosts Eternity" is an RTM tool, not an SPRX** — the most repeated mislabel in Ghosts modding write-ups.
- Any "Ghosts mod menu USB / no jailbreak" download is a scam pattern from the era — SPRX menus require CFW or HEN, full stop.

---

## What Could NOT Be Verified

Being explicit, per this guide's accuracy rules:

- **Creators** for: Frost Engine (OLDSCHOOLMODZ credit is likely the showcaser), Desire Engine, Genusion V1.3, Poltergeist, Rebound, Rezzurection, Eternal Paste 2.5, the Ghosts builds of Reflex Engine / Kebab V2 / Pepitax / Inphnect Pak, and the Destiny SPRX.
- **Host vs non-host, TU, and firmware details** for all pack-only menus listed in the mega-pack table.
- Whether Zeam's 100+ SPRX Installer currently includes Ghosts menus.
- Any surviving public download for **Desire Engine** (paid/private) or a standalone (non-crack) **Paradox** Ghosts release.
- Details of **YAGT 1.07.3** and **ImSooCool's Ghosts Tool 1.07** beyond their names appearing in an era help thread; the "Yet Another Ghosts Tool" expansion of YAGT is assumed, not verified.
- **BLES01946 / BLES01947** — no evidence these title IDs were ever used.
- No Ghosts SPRX item was found on **Archive.org**, **PSX-Place**, **Brewology**, **TheTechGame**, **Reddit** (r/ps3modding / PS3 jailbreak subs), **ps3pirata**, or **elotrolado** — those sources were checked and came up empty for Ghosts specifically (elotrolado's only Ghosts content is a clan thread). The Ghosts scene lived on NGU, YouTube, and Discord-era shops.

---

## Sources

- NextGenUpdate — SSM menu thread: https://nextgenupdate.com/forums/ghosts-mods-cheats-glitches/838311-call-duty-ghosts-116-cexdex-sprx-mod-menu.html
- NextGenUpdate — Luckeyy 1.16 anti-ban DEX EBOOT / SPRX plugin thread: https://nextgenupdate.com/forums/ghosts-mods-cheats-glitches/858210-call-duty-ghosts-116-updated-modded-anti-ban-dex-eboot-sprx-plugin.html
- NextGenUpdate — Sapphire V1 (MegaMister) + anti-ban EBOOT thread: https://nextgenupdate.com/forums/ghosts-mods-cheats-glitches/856660-116-ghost-sprx-menu-anti-ban-eboot-2.html
- NextGenUpdate — "Best free .sprx non-host menu for Ghost 1.16" (Desire Engine / Eternity discussion): https://nextgenupdate.com/forums/ghosts-modding-questions/865899-best-free-sprx-non-host-menu-ghost-116-mp.html/search
- NextGenUpdate — RatchetBooty Ghosts RTM Tool w/ Aimbot: https://nextgenupdate.com/forums/ghosts-modding-tools/707043-ghosts-rtm-tool-waimbot-106-ratchetbooty-cexdex-updated-253a-13.html
- NextGenUpdate — Ghosts 1.16 Offsets & Addresses Collection (ItsJordanModz): https://nextgenupdate.com/forums/ghosts-mods-cheats-glitches/901435-ghosts-offsets-addresses-collection-116updating.html
- NextGenUpdate — SPRX Elf Builder v1.03 (seb5594): https://nextgenupdate.com/forums/ps3-mods-cheats/748626-sprx-elf-builder-v103-ps3-plugins-11.html
- NextGenUpdate — V7UZ 1.04 PKG + debug EBOOT: https://nextgenupdate.com/forums/ghosts-mods-cheats-glitches/696648-call-duty-ghosts-104-pkg-w-working-eboot.html
- NextGenUpdate — GAMERCHOICE Productions Ghosts shop (Luckeyy): https://nextgenupdate.com/forums/ghosts-lobbies-services/915580-gamerchoice-productions-ghosts-shop-ps3ps4-transfer-trusted-staff-5.html
- NextGenUpdate — xKtF Ghosts recovery service: https://nextgenupdate.com/forums/ghosts-lobbies-services/713234-openxktfs-ghosts-recovery-servicestatssquad-pointsunlock-all-extinction-29.html
- Se7enSins — Ultimate PS3 Mod Menu Mega Collection (Ghosts section): https://www.se7ensins.com/forums/threads/release-ultimate-playstation-3-ps3-mod-menu-package-tools-mega-collection.1931291/
- YouTube — Frost Engine Non-Host 4.9 showcase: https://www.youtube.com/watch?v=vJh4TigFZbs
- YouTube — Vortex by xiBryan showcase (Virus Mike, 2025): https://www.youtube.com/watch?v=Z2nn2HHzzOc
- YouTube — Destiny SPRX HEN install tutorial, part 1 (Projeto Hacker Mods): https://www.youtube.com/watch?v=LMPlp-MQNSg
- YouTube — Zeam 100+ SPRX Mod Installer PKG showcase: https://www.youtube.com/watch?v=gKpFuDtXtDc
- GitHub — ZER0x1337's Ghost RTM Tool: https://github.com/Zer0x1337/ZER0x1337s-Ghost-RTM-PS3
- Scribd — ExIIL Multitool feature list: https://www.scribd.com/document/698694609/ExIIL-Multitool-Feature-List
- CabConModding — DLC Camo Customizer by Pyrex BLJ: https://cabconmodding.com/threads/dlc-camo-customizer.3008/
- RPCS3 Wiki — Call of Duty: Ghosts (title IDs, game version 1.16): https://wiki.rpcs3.net/index.php?title=Call_of_Duty:_Ghosts
- NotNite — reverse-engineering SPRX Elf Builder: https://NotNite.com/blog/ps3

*Researched October 2026. Game facts (final TU, title IDs) verified against the RPCS3 wiki and PS3 update listings; menu/tool facts taken from the release threads and showcases linked above. Creator credits are given only where a source states them — "creator unclear" is stated wherever it doesn't.*

---

## Community

- **Discord:** unosdopplegange
- **Discord server:** https://discord.gg/MDcaC5nPuA
