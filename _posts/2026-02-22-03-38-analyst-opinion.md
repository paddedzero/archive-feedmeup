---
layout: post
title: "Analyst Top 3: Cybersecurity — Feb 22, 2026"
date: 2026-02-22 03:38:51 -0500
categories: ["Analyst Opinion", "Cybersecurity"]
tags: ["Analyst Opinion", "Cybersecurity", "deep-dive"]
---
## This Week's Top 3: Cybersecurity

The **Cybersecurity** category captured significant attention this week with **331** articles and **22** trending stories.

Here are the **Top 3 Articles of the Week**—comprehensive analysis of the most impactful stories:

## Article 1: Appsec Roundup - June 2025

The article notes advancements in **

<a href="https://shostack.org/blog/appsec-roundup-june-2025/">Read the full article</a>

### Technical Analysis: What's Really Happening

### The Mechanic: What's Actually Happening

The "Appsec Roundup" of June 2025 marks a definitive, if overdue, funeral for the static security spreadsheet. For a decade, we’ve treated threat modeling like a high school yearbook—something we compile once a year, sign with a flourish, and shove into a drawer until the next audit. The shift we are seeing now, characterized by "Threat Modeling as Code" (TMaC) and real-time risk telemetry, is an attempt to finally kill the "point-in-time" assessment. But beneath the marketing gloss of these new risk management tools lies a more complex, and frankly more dangerous, mechanical shift.

What’s actually happening is the **decentralization of the security gate.** We are moving away from a central Security Operations Center (SOC) dictating terms to developers. Instead, we are seeing the rise of **Continuous Threat Modeling (CTM)**. These tools don't just draw diagrams; they ingest eBPF (Extended Berkeley Packet Filter) data from production environments and compare it to the original design documents. When a microservice starts communicating with an unauthorized S3 bucket or an external API that wasn't in the initial model, the system doesn't just alert—it breaks the build or revokes the service identity. We’ve moved from "describing" the threat to "programmatically enforcing" the absence of it.

However, we must look skeptically at the "gamification" trend mentioned in the June roundup. While the industry is desperate to solve the "developer friction" problem, "Security Games" are often a thin veil for a lack of institutional culture. The mechanic here isn't just about making security "fun"; it’s an admission that **automated scanning has reached a plateau.** We can find the SQL injection and the leaked secret with 99% accuracy now, but we still can’t automate the "logic flaw"—the way an attacker might abuse a business process to bypass a payment gateway. The "games" are an attempt to crowdsource human intuition because the AI, for all its generative prowess, still lacks the "malicious creativity" of a bored teenager with a proxy tool.

Finally, the new risk management tools are shifting their focus from **CVSS scores to EPSS (Exploit Prediction Scoring System) plus business context.** In 2025, a CVSS 9.8 in a sandbox is a noise-level event. A CVSS 6.0 in a customer-facing authentication module is a board-level crisis. The mechanics of these tools now involve "Asset Criticality Mapping," where the tool automatically assigns value to a code repository based on its proximity to PII (Personally Identifiable Information) or financial transactions. We are finally seeing the "App" put back into "AppSec."

### The "So What?": Why This Matters

If you are a CISO, the "So What" is simple: **The barrier to entry for sophisticated architectural attacks has plummeted.** As we automate the basics, attackers are moving "up the stack." They aren't looking for a buffer overflow; they are looking for a flaw in your automated threat model’s logic. If your security-as-code assumes that "Service A" is trusted because it’s in the "Internal" zone, an attacker who compromises a developer’s local environment can inject a new "trusted" service into that code-defined model. By the time your automated tools realize the architecture has changed, the data is gone.

This shift also breaks the unified security model that many legacy enterprises still cling to. In the old world, the Network Team owned the firewall, and the AppSec team owned the code. In the June 2025 paradigm, **the code *is* the firewall.** This creates a massive "Accountability Gap." When a breach occurs because of a flawed threat model, who is responsible? The developer who wrote the TMaC file? The security architect who approved the template? Or the AI that suggested the remediation? We are entering an era of **"Distributed Liability,"** where the speed of deployment is outstripping our ability to assign blame—or even perform a coherent post-mortem.

Furthermore, the democratization of risk management tools means that "Shadow IT" has evolved into **"Shadow Security."** Departments are now spinning up their own risk-scoring instances, often with different thresholds than the central security office. This leads to "Risk Arbitrage," where teams move their most vulnerable projects to the business units with the most "lenient" automated security gates. We are seeing a fragmentation of the corporate risk posture that can be exploited by any adversary who understands the internal politics of a large organization.

Lastly, we cannot ignore the metrics. The June roundup suggests a reduction in Mean Time to Remediation (MTTR), but I argue this is a **vanity metric.** If you are fixing 1,000 low-level vulnerabilities in record time but missing the one structural flaw that allows for a full tenant-to-tenant breakout in your SaaS platform, your MTTR is irrelevant. The "So What" here is that we are getting better at the small things while becoming structurally more fragile at the macro level.

### Strategic Defense: What To Do About It

To navigate this shift, leadership must move beyond purchasing "tools" and start engineering "resilience." The goal isn't to have a perfect threat model; it's to have a system that fails gracefully when the model is inevitably proven wrong.

#### 1. Immediate Actions (Tactical Response)

*   **Audit the "As-Code" Templates:** If you are using Threat Modeling as Code (TMaC), your security is only as good as your templates. Conduct a manual "Red Team Review" of your TMaC library. Look for "Default Allow" logic and ensure that the templates require explicit justification for cross-zone communication.
*   **Implement "Identity-First" Micro-Segmentation:** Stop relying on network zones. Use tools like **Istio or Linkerd** to enforce mTLS (mutual TLS) and identity-based access between every service. If a service isn't in the threat model, it shouldn't just be "flagged"—it should be unable to obtain a cryptographic identity to talk to the rest of the cluster.
*   **Pivot from CVSS to EPSS + Asset Value:** Instruct your AppSec teams to ignore any vulnerability with an **EPSS score below 0.1** unless it sits on a "Tier 0" asset (e.g., your identity provider, your primary database, or your CI/CD pipeline). This will immediately reduce noise by 60-70% and allow your humans to focus on the architectural flaws that actually matter.

#### 2. Long-Term Strategy (The Pivot)

*   **The "Security Champion" 2.0:** Move away from the idea of a "Security Champion" as a developer who likes security. Instead, embed **"Security Engineers" directly into the product squads.** Their performance reviews should be tied to the "Architectural Integrity" of the product, not the speed of feature delivery. They are the ones who must "play the games" and challenge the automated threat models.
*   **Adversarial Resilience Testing (ART):** Replace your annual penetration test with continuous, automated adversarial simulations. Use platforms that integrate with your CI/CD to launch "safe" versions of real-world attacks (like those seen in the Feb 2026 scans) against your staging environment. If your automated threat model doesn't catch a simulated **Golden SAML attack** or a **CI/CD poisoning attempt**, the model is broken and must be reverted.
*   **Formalize the "Risk Appetite Statement" for Code:** CISOs must provide a machine-readable "Risk Appetite" that can be ingested by these new risk management tools. This isn't a PDF; it’s a set of **OPA (Open Policy Agent) policies** that define exactly what level of risk is acceptable for which service. This eliminates "Risk Arbitrage" by ensuring that the security gate is consistent across the entire enterprise, regardless of who is running the tool.

The June 2025 roundup isn't just a list of new toys; it’s a signal that the "Great Automation" of AppSec is nearly complete. The question for the executive is no longer "Are we scanning?" but **"Do we actually understand the architecture we’ve built?"** If you can't answer the latter, no amount of gamification will save you.

---

## Article 2: Secure By Design roundup - Dec/Jan 2026

The article discusses

<a href="https://shostack.org/blog/appsec-roundup-dec-jan-2026/">Read the full article</a>

### Technical Analysis: What's Really Happening

### The Mechanic: What's Actually Happening

When we look back at the wreckage of major breaches, we rarely find a "super-hacker" wielding a zero-day exploit that defies the laws of physics. Instead, we find the **normalization of deviance**. This term, coined by sociologist Diane Vaughan after the Challenger disaster, describes the process where a clearly dangerous practice becomes so ingrained in a culture that it is no longer viewed as a risk, but as a standard operating procedure. In the context of the 2026 "Secure by Design" landscape, we are seeing this play out in the architectural choices of the world’s largest SaaS and infrastructure providers. We have reached a point where shipping insecure code is not an oversight—it is a calculated business decision that has finally hit its breaking point.

The technical reality of "Secure by Design" isn't about adding another layer of paint to the house; it’s about the foundation. For years, we’ve relied on "bolted-on" security—WAFs, EDRs, and identity proxies—to compensate for the fact that our underlying applications are fundamentally porous. The Dec/Jan 2026 roundup highlights a pivot toward **automated threat modeling** integrated directly into the CI/CD pipeline. We are moving away from the era of the "Security Architect" who reviews a PDF once a quarter. Instead, we are seeing the rise of **Policy-as-Code (PaC)** that enforces architectural constraints at the pull-request level. If a developer attempts to spin up an S3 bucket with public read access or a service without a hardware-backed identity, the build simply fails. This isn't "shifting left"; it’s building a fence that cannot be climbed.

However, the most unsettling mechanic discussed in recent months is the commoditization of **Signal Interference and GPS Spoofing**. While the industry has been obsessed with software vulnerabilities, the physical layer—the actual radio frequency (RF) environment our devices inhabit—is being weaponized. We are seeing a surge in "low-cost, high-impact" GPS attacks that don't just affect navigation; they disrupt the **Precision Time Protocol (PTP)** that modern financial systems, power grids, and 6G networks rely on. When the "time" on your server is manipulated, your cryptographic handshakes fail, your logs become useless for forensics, and your distributed databases lose consistency. This is a "Secure by Design" failure at the hardware level that most CISOs are currently ignoring in favor of more traditional software threats.

Finally, we have to address the "Exciting Threat Modeling News" mentioned in the roundup. This refers to the integration of **Large Language Models (LLMs) into the STRIDE framework**. By feeding an application’s architecture diagram (rendered in Mermaid or JSON) into a specialized security LLM, teams are identifying edge cases in minutes that used to take weeks of manual review. But here is the catch: these tools are only as good as the telemetry they receive. If your organization is still operating with "shadow IT" or undocumented APIs, these automated threat models are merely hallucinating a sense of security that doesn't exist.

### The "So What?": Why This Matters

Why should a C-suite executive care about the "normalization of deviance" or GPS spoofing? Because the **regulatory floor is rising faster than the technical ceiling.** For the first time, we are seeing a convergence where technical debt is being reclassified as legal liability. The roundup poses a critical question: Do regulatory threats change the threat model as much as GPS attacks? The answer is "not yet," but the gap is closing.

If a GPS attack takes down your logistics fleet, you lose revenue for a day. If a regulator determines that your "Secure by Design" posture was a marketing fiction—that you knowingly allowed the normalization of deviance to bypass security controls for the sake of speed—the resulting fines and "consent decrees" can cripple a company for a decade. We are entering an era of **Personal Liability for Security Architects**. Just as structural engineers are held liable if a bridge collapses due to poor design, the 2026 regulatory landscape is moving toward holding individuals accountable for systemic design failures.

Furthermore, the threat to our **Unified Security Model** is profound. Most enterprises have spent the last five years moving toward a "Zero Trust" architecture. This model relies on three things: Identity, Device Health, and Context. GPS attacks break the "Context" pillar. If an attacker can spoof a device’s location and time, they can bypass geo-fencing and time-based access controls. This lowers the barrier to entry for sophisticated "Man-in-the-Middle" (MITM) attacks. An attacker no longer needs to compromise your password; they just need to make your server believe it is in a trusted data center at a trusted time.

The "So What" is simple: **We are losing our grip on the physical truth of our systems.** When we can no longer trust the time, the location, or the integrity of the design process itself, the entire stack becomes a house of cards. The Dec/Jan 2026 data suggests that while we’ve gotten better at catching bugs (the "micro" view), we are getting worse at understanding systemic risk (the "macro" view). The normalization of deviance has made us comfortable with "good enough" security, but in a world of automated RF attacks and aggressive regulators, "good enough" is a fast track to a catastrophic failure.

### Strategic Defense: What To Do About It

To counter these shifts, we must move beyond the "Weekly Scan" mentality and adopt a bifurcated strategy that addresses both the immediate technical rot and the long-term architectural drift.

#### 1. Immediate Actions (Tactical Response)

*   **Audit for "Time-Slamming" Resilience:** Most organizations assume their NTP/PTP sources are immutable. You must immediately audit your critical infrastructure (Active Directory, database clusters, and logging servers) to ensure they are using **authenticated NTP (NTS)** or have secondary, non-GPS-based time sources (such as atomic clocks or terrestrial fiber-based time). If your logs are out of sync by even a few seconds, your incident response will fail.
*   **Enforce Memory-Safety for New Proxies:** If you are deploying new edge infrastructure or microservices, mandate the use of **Rust or Go**. The "Secure by Design" roundup makes it clear: memory-safety vulnerabilities (Buffer Overflows, Use-After-Free) are no longer acceptable "accidents." They are design flaws. Any new code that handles untrusted input must be written in a memory-safe language—no exceptions.
*   **Kill the "Exception Culture":** Conduct a "Deviance Audit." Identify every security control that has been bypassed "temporarily" for a project over the last six months. If a bypass has existed for more than 30 days, it is no longer an exception; it is your new (insecure) standard. Force a "re-architect or shut down" policy for these deviations.

#### 2. Long-Term Strategy (The Pivot)

*   **Transition to "Model-Based Security":** Stop treating threat modeling as a document. Move toward **Continuous Threat Modeling** where your architecture diagrams are stored as code (e.g., using OpenThreatModel or IriusRisk). This allows you to run automated "security unit tests" against your design every time the infrastructure changes. If the model detects a new path to a crown jewel, the deployment is blocked before a single line of infrastructure is provisioned.
*   **Adopt "Hardware-Rooted Identity":** As GPS and RF spoofing become more common, software-based signals are no longer sufficient. The long-term pivot must be toward **TPM (Trusted Platform Module) 2.0 and FIDO2/WebAuthn** for everything. We must move to a state where an identity is tied to a specific piece of silicon that cannot be spoofed by a radio signal or a stolen session cookie. This is the only way to re-establish "truth" in a world of manipulated context.
*   **Regulatory Resilience as a Design Requirement:** Treat upcoming regulations (like the Cyber Resilience Act or updated SEC mandates) as **technical specifications**, not legal hurdles. Build "Auditability by Design" into your systems. This means immutable audit logs, automated SBOM (Software Bill of Materials) generation for every build, and a transparent "Security Scorecard" for every product line that is visible to executive leadership. When the regulator knocks, you shouldn't be "preparing for an audit"—you should simply be handing over a real-time dashboard.

The "Secure by Design" movement is not a trend; it is a survival mechanism. As we move through 2026, the organizations that thrive will be those that recognize that **security is a feature of engineering excellence, not a department that sits down the hall.** Stop normalizing deviance. Start designing for reality.

---

## Article 3: “Good enough” emulation: Fuzzing a single thread to uncover vulnerabilities

A Talos researcher uncovered

<a href="https://blog.talosintelligence.com/good-enough-emulation/">Read the full article</a>

### Technical Analysis: What's Really Happening

### The Mechanic: What's Actually Happening

For years, the cybersecurity industry has treated IoT and Industrial Control Systems (ICS) firmware like a Victorian-era "black box"—mysterious, proprietary, and notoriously difficult to audit without a specialized lab and a mountain of expensive hardware. The prevailing wisdom was that to find deep-seated vulnerabilities, you needed full-system emulation. You had to trick the software into thinking it was running on its native silicon, complete with all the quirky peripherals, sensors, and proprietary interrupts that usually cause standard emulators like QEMU to crash and burn.

The recent work by Cisco Talos on the **Socomec DIRIS M-70 gateway**—a critical piece of kit used for power monitoring and industrial communication—flips this script. Instead of trying to boil the ocean by emulating the entire device, the researcher employed what we call **"Good Enough" Emulation**. By isolating the specific thread responsible for handling Modbus traffic and emulating only that slice of the execution environment, they bypassed the "peripheral nightmare" that stops most audits in their tracks.

We are seeing a transition from brute-force hardware hacking to **surgical software instrumentation**. The researcher used a combination of **User-mode emulation** and custom "harnesses" to feed the Modbus thread a diet of malformed data (fuzzing). When the thread crashed, it wasn't because of a hardware mismatch; it was because of a genuine memory corruption or logic flaw in the code. This approach uncovered **six distinct vulnerabilities**, ranging from heap overflows to out-of-bounds reads. This isn't just "finding bugs"; it’s the systematic dismantling of the "security through obscurity" defense that ICS manufacturers have hidden behind for decades.

The technical reality is that the barrier to entry for high-end vulnerability research in the OT space has just plummeted. If you can isolate a thread and provide it with the expected memory state, you don't need the physical device at all. You just need the firmware image, a copy of **Ghidra**, and a few weeks of focused engineering. The "black box" is now transparent.

### The "So What?": Why This Matters

If you are a CISO in the manufacturing, energy, or critical infrastructure sectors, this should give you pause. The Socomec DIRIS M-70 is a gateway—a bridge. These devices are the connective tissue between the high-level management network and the low-level physical actuators and sensors. When a gateway falls, the entire "Air Gap" myth evaporates.

**The democratization of exploit development** is the primary takeaway here. Historically, finding zero-days in industrial gateways required state-sponsored levels of funding or a highly specialized lab. By proving that "good enough" emulation works, the researcher has essentially published a blueprint for how mid-tier threat actors—including sophisticated ransomware groups—can audit OT hardware on a budget. 

Consider the economics:
1.  **Lowered R&D Costs for Attackers:** An attacker no longer needs to steal or buy a $5,000 gateway and risk "bricking" it during testing. They can run a thousand instances of the vulnerable thread in the cloud for pennies.
2.  **The Modbus Achilles Heel:** Modbus is the lingua franca of the industrial world. It is also an unauthenticated, 40-year-old protocol that was never designed for a hostile network environment. By targeting the Modbus thread specifically, attackers are hitting the most exposed and least defended part of the industrial stack.
3.  **The Patching Paradox:** Even though Socomec has released patches for these six vulnerabilities, the "Long Tail" of OT maintenance means many of these gateways will remain unpatched for the next 5 to 10 years. In the industrial world, "if it ain't broke, don't fix it" usually trumps "patch Tuesday."

This research proves that the "proprietary" nature of your OT hardware is no longer a shield. It is a liability. If a single researcher can find six vulnerabilities using a "good enough" approach, imagine what a dedicated team of offensive engineers in a hostile nation-state can do with the same methodology. We are entering an era where **firmware is just another piece of software**, and it will be picked apart with the same ruthless efficiency as a web browser or a PDF reader.

### Strategic Defense: What To Do About It

The discovery of these vulnerabilities in a core industrial gateway necessitates a move away from "perimeter-only" security. You must assume that the devices sitting on your DIN rails are inherently flawed and that their "proprietary" nature offers zero protection.

#### 1. Immediate Actions (Tactical Response)

*   **Audit the Modbus Footprint:** Identify every device in your environment—like the Socomec M-70—that speaks Modbus. Use a tool like **Rumble (runZero)** or **Claroty** to map these assets. If a device doesn't *need* to be accessible via the network for its primary function, move it to a physically isolated segment.
*   **Implement Protocol-Aware Inspection:** Standard firewalls are blind to what’s happening *inside* a Modbus packet. Deploy Deep Packet Inspection (DPI) via tools like **Nozomi Networks** or **Dragos**, or even open-source **Zeek** with industrial analyzers. You need to be able to see if someone is sending "Function Code 16" (Write Multiple Registers) with a payload that looks like a heap spray.
*   **Credential and Access Tightening:** Many of these gateway vulnerabilities are reachable because the management interface is left with default credentials or is accessible from the general corporate VLAN. **Harden the management plane.** Use a jump box with Multi-Factor Authentication (MFA) for any administrative access to these gateways.

#### 2. Long-Term Strategy (The Pivot)

*   **Shift-Left Procurement (The SBOM Mandate):** Stop buying "black boxes." Moving forward, your procurement contracts for any ICS/OT hardware must require a **Software Bill of Materials (SBOM)**. You need to know if your gateway is running an ancient version of BusyBox or a vulnerable Modbus library before you bolt it into your power grid. If a vendor cannot provide an SBOM, they are a high-risk liability.
*   **Hardware-Rooted Trust:** We must move toward hardware that supports **Secure Boot** and **Trusted Execution Environments (TEEs)**. The reason "good enough" emulation works is that the firmware is often a monolithic blob with no internal compartmentalization. Future architectures should isolate communication threads (like Modbus) from the core logic of the device using hardware-backed memory protection.
*   **The Zero-Trust OT Architecture:** We have to kill the "Trusted Internal Network." Every communication between a PLC, a gateway, and an HMI should be treated as potentially malicious. This means moving toward encrypted industrial protocols (like **OPC UA with security profiles** or **Modbus/TCP Security**) and away from the raw, unauthenticated protocols that these six vulnerabilities exploit.

The Socomec research is a wake-up call. The "Mechanic" has shown us that the walls are thinner than we thought. It’s time to stop pretending our industrial hardware is special and start treating it like the vulnerable software it actually is.

---

**Analyst Note:** These top 3 articles this week synthesize industry trends with expert assessment. For strategic decisions, conduct thorough validation with your security, compliance, and risk teams.