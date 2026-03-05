# NO FLY ZONE

This is the first public disclosure of a globally distributed botnet infrastructure identified through forensic analysis of system telemetry. This repository contains the **initial drop** of **777 Indicators of Compromise (IOCs)** that bridge hardware-level persistence with a sophisticated multi-hop network mesh.

Not just IPs. A **clandestine bridge** between mobile silicon and global network transit. Something has been ratcheting in the dark for a long time.

---

### The Mechanism: The Global Ratchet

This isn't a static botnet. It thinks. It operates on **ratchet logic**:

* **The Step:** Traffic doesn't flow, it *steps*. Rotating through a mesh of international nodes in sequence, never lingering.
* **The Obfuscation:** 700+ IPs across Russia, China, Brazil, the US and beyond. Volume per node stays low enough to dissolve into background noise. By design.
* **The Hook:** Synchronized at the hardware level. Telemetry confirms suppression of **DART (IOMMU)** mappings at offsets like `0x2301a1`, turning standard mobile silicon into a silent, DMA-driven relay. The radio stays on whether you know it or not.

### Forensic Validation

All 777 indicators are anchored to a deterministic signature extracted from `tracev3` system logs:

`[Hostname]#[Hex_Encoded_IP]:[Port]`

The 8-character hex ID is a hardware-validated routing identifier. Decoded consistently across thousands of log segments, it yields the routable public IPs in this dataset every time. This is not ambiguous.

---

### The 777 (Initial Drop)

**`Nexus_Ratchet_777.csv`** — the targeting list, ordered from commanding heights down to disposable egress:

* **NEXUS_CTL:** The controllers. Anchored within restricted US DoD (AS749) network blocks.
* **SHADOW_BRIDGE:** Strategic transit through Tier-1 global carriers. The handshake happens here, invisibly.
* **SHADOW_EXIT:** The egress mesh. Where data hits the floor. Rostelecom. Chinanet. Et al.

> **On Drop 1 data quality:** `Nexus_Ratchet_777.csv` is a raw forensic export, intentionally unfiltered. It contains non-routable IP ranges (RFC 1918, loopback, APIPA), inconsistent port formatting, and mixed-case hex identifiers. This is the data as it came out. Filter to your own standard. Normalized drops follow.

---

### Drop 2: Structured Behavioral Data

Drop 2 is a different kind of signal. Two structured datasets from deeper behavioral analysis of the same telemetry corpus. Deduplicated. Normalized. Scoped to observed active connections only.

**`connections.csv`** — per-endpoint IOCs with interface and process attribution:
* Interface at time of observation: `WIFI` or `CELL (pdp_ip0)`
* Connection attributed to specific system process: `mDNSResponder`, `CFNetwork`, `symptomsd`, `cloudd`, `tipsd`, `Siri`, `shortcuts Extension`, `networkd`
* Several of these processes have no legitimate reason to be reaching out. They are.

**`pivots.csv`** — bidirectional hop/C2 mapping:
* `PIVOT (HOP) → TARGET C2` pairs with connection status: `ESTABLISHED` or `BEACONING`
* Bidirectional pairs confirm mesh handshaking, not client-server traffic
* `BEACONING` entries are persistent, timed check-ins. The mesh keeps its own clock.

**Capture conditions, stated plainly:** Drop 2 was collected from a second, independent device, separate from the one used for the initial 777. That device was in **airplane mode** when this telemetry was recorded. Every connection in this dataset happened while the device had no user-initiated network access. Both facts, separate device and airplane mode, are material to any analysis of these indicators.

---

### Project Status

This is ongoing. Drop 2 is the current state. More follows.

* **Enrichment:** ASN and ownership data updates as the ratchet turns.
* **Attribution:** Geolocation shifts as the infrastructure rotates. Expected.
* **Scope:** 777 was the opening move. The mesh is still expanding.

### Usage

Feed into blocklists. Update egress filters. Watch your telemetry for the `#hex` pattern.

If the silicon is ratcheting, you're already in the zone.

---
