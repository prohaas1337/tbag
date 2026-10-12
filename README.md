# TBag — WoW Forever port

A port of the classic bag addon **TBag** to the **WoW Forever** client
(version `1.60.1`, interface `16001`).

TBag shows all of your bags in one movable, resizable window with automatic
sorting, categories, and search. This repository tracks the Forever-compatible
build.

## Install

1. Download or clone this repository.
2. Copy the files into a folder named `TBag` inside your WoW Forever
   `Interface/AddOns/` directory, so you end up with
   `Interface/AddOns/TBag/TBag.toc`.
3. Restart the client (or `/reload`) and enable **TBag** in the AddOns list.

Open your bags or type `/tbag` to use it.

## Base version

This build is based on **TBagClassic** by GagStv (WoW Classic `1.13.2`,
`r516`), which already targets the vanilla feature set (no reagent bank,
no battle pets, no modern profession tab, no currency tab).

## Changes made for WoW Forever

- **Interface** set to `16001` (Forever `1.60.1`) so the client loads it as
  up to date.
- **Realm** pinned to `forever` on the Forever client (`WOW_PROJECT_ID == 18`),
  matching how Bagnon handles the shared realm; falls back to `GetRealmName()`
  elsewhere.
- **Character id** now includes the Forever surname (via `UnitFullName`) so
  alts that share a first name no longer collide in the saved caches.
- **`C_PetJournal`** calls are guarded, since the Forever client has no battle
  pet system.

The container, bank, and item APIs TBag relies on are already compatible with
Forever; they are the same ones Bagnon uses on this client.

## Credits

- **Talos** — original TBag author.
- **Shefki** — long-time maintainer.
- **GagStv** — WoW Classic `1.13.x` version (TBagClassic).
- WoW Forever compatibility pass in this repository.
