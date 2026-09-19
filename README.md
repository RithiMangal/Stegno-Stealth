# 🛡️ STEGNO STEALTH — *Privacy Is Our Rights*

> *"The best place to hide a secret is in plain sight — inside a file that looks 100% innocent."*

**Stegno Stealth** is a carrier-safe steganography suite forged in **Rust** — built for ghosts, whistleblowers, and anyone who believes **privacy is not a privilege, it's a right**. Hide entire files and folder trees inside any ordinary carrier — images, audio, executables, anything — with **zero modification to the carrier bytes**. The carrier opens, plays, and hashes exactly as before… while secretly carrying your payload in the shadows. 👻

No traces. No suspects. Just silence.

---

## ⚙️ UNDER THE HOOD // HOW THE GHOST WORKS

* **👻 Carrier-safe footer embedding** — payload layout: `[carrier][MAGIC][meta_len][meta][size][payload]`. The carrier prefix is NEVER touched. Every embed ends with a byte-level verification that reports `Carrier check: PERFECT` — anything less is rejected.
* **📦 Double-packed payload** — files and folders are first ZIP-deflated, then zlib-crushed at level 9. Maximum density, minimum footprint.
* **🔐 SHA-256 XOR stream encryption** — optional password lock derived from a SHA-256 key digest. Wrong password? You get static noise — never a crash, never a clue.
* **🔍 Forensic footer parsing** — extraction hunts the magic header in reverse (`rfind`) with full bounds-checking. Corrupted or truncated drops are flagged, not blindly trusted.
* **🎯 Three strike modes** — `EMBED` (plant the secret) · `EXTRACT` (pull it out + restore the original carrier) · `ANALYZE` (sniff any file for hidden payloads, sizes, encryption status).

---

## ✨ ARSENAL // HIGHLIGHTS

* **🖥️ Frameless neon war-room** — borderless window, custom single-click minimize / maximize / close controls. Glowing `Stegno Stealth` banner with the *Privacy Is Our Rights* oath burned beneath it. Dark cyan-magenta-lime ops aesthetic. Leave no window chrome behind.
* **⌨️ Dual-mode operative** — launch with zero args for the full GUI, or go dark with headless `embed / extract / analyze` CLI commands for scripts and automation.
* **🧵 Non-blocking phantom threads** — heavy crypto runs off-thread. The UI never freezes, never stutters — live status feed while the ghost works.
* **📁 Whole directory trees** — drop in full folder structures. Extraction rebuilds every path exactly.
* **💾 Large-file safe** — hardened against overflow with explicit guards (`Size too large` instead of silent corruption).
* **⚡ Tiny, fast, dependency-free** — ~14 MB stripped release binary. No interpreter, no runtime, no installation trail. Just execute and vanish.

---

## 🚀 DEPLOYMENT

### Run the ghost

```bash
./StegnoStealth              # frameless neon GUI
./StegnoStealth embed <carrier> <output> [password] <files/folders...>
./StegnoStealth extract <stego-file> <outdir> [password]
./StegnoStealth analyze <file>
```

### Build from source

```bash
cargo build --release        # optimized binary lands in target/release/
```

---

## ⚠️ OPSEC WARNING — LOCK YOUR STEGO FILE: SET IT READ-ONLY

> **After embedding, mark the carrier file as READ-ONLY. This step is not optional, operative.**
>
> Metadata-cleaner tools "sanitize" files by stripping trailing and foreign data blocks. Your hidden files and folders live in a footer appended *after* the carrier — so **running a metadata cleaner on the stego file will silently and permanently vaporize your embedded payload**. A read-only flag deadbolts the file: cleaners and careless overwrites bounce off, and your secret stays buried.
>
> * Linux: `chmod 444 <stego-file>`
> * Windows: right-click → Properties → ✅ Read-only
>
> **No read-only = no guarantee. Protect the drop.**

---

## 📜 CREED

*Privacy is our right. Stegno Stealth just enforces it — one invisible byte at a time.*

🖤 Stay hidden. Stay free.
