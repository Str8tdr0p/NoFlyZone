# NO FLY ZONE 

This is the first public disclosure of a globally distributed botnet infrastructure identified through forensic analysis of system telemetry. This repository contains the **initial drop** of **777 Indicators of Compromise (IOCs)** that bridge hardware-level persistence with a sophisticated multi-hop network mesh.

We aren't just looking at IPs; we're looking at a **clandestine bridge** between mobile silicon and global network transit.

---

### **The Mechanism: The Global Ratchet**

This isn't your standard, static botnet. It operates on a **ratchet** logic:

* **The Step:** Traffic doesn't just flow; it "steps" through a rotating mesh of international nodes.
* **The Obfuscation:** By ratcheting data through 700+ IPs across Russia, China, Brazil, US, etc; the actor keeps the volume per-node low enough to vanish into the background noise of the internet.
* **The Hook:** It's all synchronized at the hardware level. The telemetry confirms the suppression of **DART (IOMMU)** mappings at offsets such as `0x2301a1`, turning standard mobile silicon into a silent, DMA-driven relay.

### **Forensic Validation**

All 777 indicators are tied to a deterministic signature found in `tracev3` system logs:

`[Hostname]#[Hex_Encoded_IP]:[Port]`

The 8-character hex ID is a hardware-validated routing identifier. Mathematical decoding of these identifiers across thousands of log segments consistently yields the routable public IP addresses contained in this dataset.

---

### **The 777 (Initial Drop)**

The included **`Nexus_Ratchet_777.csv`** is the targeting list, prioritized from the "Commanding Heights" down to the disposable exit points:

* **NEXUS_CTL:** The controllers. Heavily anchored within restricted US DoD (AS749) network blocks.
* **SHADOW_BRIDGE:** Strategic transit points within Tier-1 global carriers used to mask cross-border handshakes.
* **SHADOW_EXIT:** The global egress mesh. Where the data actually hits the floor (Rostelecom, Chinanet, etc.).

---

### **Project Status**

This repository represents the **first drop** of the identified infrastructure.

* **Ongoing Enrichment:** Data enrichment is a continuous process; ownership and ASN data are updated as the ratchet turns.
* **Dynamic Attribution:** Geolocation and provider data are subject to change as the infrastructure rotates.
* **Scaling Potential:** 777 is just the beginning. The mesh is expanding, and so will this list.

### **Usage**

Feed these into your blocklists, update your egress filters, and monitor your telemetry for the `#hex` pattern. If the silicon is ratcheting, you're in the zone.

---

