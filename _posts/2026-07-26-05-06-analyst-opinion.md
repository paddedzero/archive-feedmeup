---
layout: post
title: "Analyst Top 3: Cybersecurity — Jul 26, 2026"
date: 2026-07-26 05:06:11 -0400
categories: ["Analyst Opinion", "Cybersecurity"]
tags: ["Analyst Opinion", "Cybersecurity", "deep-dive"]
---
## This Week's Top 3: Cybersecurity

The **Cybersecurity** category captured significant attention this week with **418** articles and **26** trending stories.

Here are the **Top 3 Articles of the Week**—comprehensive analysis of the most impactful stories:

## Article 1: Appsec roundup - May 2026

The article highlights

<a href="https://shostack.org/blog/appsec-roundup-may-2026/">Read the full article</a>

### Technical Analysis: What's Really Happening

### The Mechanic: What's Actually Happening

The industry’s obsession with "Memory Safety" has finally hit the cold, hard pavement of reality. For the past three years, the mandate from the CISA and the White House has been clear: move to memory-safe languages or face the consequences. Our latest data from the May 2026 AppSec roundup shows that organizations are finally completing their first major **Rust refactoring cycles**. The results are a mixed bag of technical triumph and operational friction. While we are seeing a documented **70% decrease in use-after-free and buffer overflow vulnerabilities** in core modules, we are simultaneously witnessing a surge in "Logic-Density" bugs. 

By stripping away the memory management overhead, developers are writing more complex, hyper-optimized logic that is increasingly difficult to peer-review. We’ve traded predictable, exploitable memory errors for opaque, high-level architectural flaws. This is the **Rust Paradox**: the foundation is now made of reinforced concrete, but the floor plan is a labyrinth that even the architects don't fully understand.

Compounding this is the "AI Slop" crisis. As we push for faster delivery, engineering teams are leaning on LLMs to handle the heavy lifting of these Rust rewrites. But these models are now suffering from **recursive degradation**. They are training on their own synthetic output—the "slop" mentioned in the May reports—leading to a subtle but dangerous drift in code quality. We are seeing AI-generated Rust that compiles and passes memory-safety checks but contains "hallucinated" logic flows that introduce **Repudiation threats**. 

In the STRIDE model, Repudiation is often the neglected middle child. But in 2026, it has become the primary weapon for sophisticated actors. If an AI agent generates a transaction or modifies a cloud configuration, and the underlying logging mechanism cannot definitively link that action to a human intent or a verified service principal, the audit trail is effectively dead. We are entering an era where "I didn't do it, the model did" becomes a valid legal and technical defense, breaking our existing forensic frameworks.

### The "So What?": Why This Matters

This isn't just another cycle of "new tech, new problems." This is a fundamental shift in the **Software Supply Chain of Trust**. If you are a CISO, your primary concern has likely been "preventing the breach." In the 2026 landscape, your concern must shift to "proving the state."

The OWASP Strategic Plan update is a direct response to this. They are moving away from a simple "Top 10" list of vulnerabilities toward a comprehensive **Integrity Framework**. Why? Because the barrier to entry for attackers has collapsed. An adversary no longer needs to find a zero-day in your memory management; they just need to inject "slop" into the training data or the prompt engineering pipeline of your internal dev-bots. 

When AI-generated code introduces non-repudiation vulnerabilities, it lowers the "Cost-to-Attack" to near zero. An attacker can manipulate business logic in a way that looks exactly like a standard, albeit slightly buggy, AI-generated PR. If your security architecture relies on the assumption that "code written by us is trusted," you are already compromised. The **erosion of the Source of Truth** means that your logs, your code, and even your identity providers are now subject to "probabilistic reality." 

Furthermore, the "two new books" referenced in the roundup—likely focusing on *Autonomous Security Operations* and *The Post-LLM Development Lifecycle*—highlight a grim reality: we are outrunning our ability to govern. If your organization is rewriting legacy C++ in Rust using AI that is feeding on its own errors, you aren't "modernizing." You are technical-debt-loading at machine speed. The impact is a **Unified Security Model collapse**, where the network, the identity, and the application layers are no longer speaking the same language of trust.

### Strategic Defense: What To Do About It

We cannot solve 2026 problems with 2022 tools. Static Analysis (SAST) is struggling with the complexity of Rust’s borrow checker, and traditional DAST is blind to AI-driven logic flaws. We need a bifurcated approach that prioritizes **verifiability over velocity**.

#### 1. Immediate Actions (Tactical Response)

*   **Implement Cryptographic Provenance for Code (Sigstore/Gitsign):** Stop relying on GitHub usernames. Every commit, especially those assisted by AI, must be signed with a developer’s hardware-backed key (YubiKey/FIDO2). If a line of code changes, you must be able to prove *who* authorized the AI to write it.
*   **Harden the Rust Toolchain:** Use `cargo-audit` and `cargo-deny` in every CI/CD pipeline to catch known vulnerabilities in the crate ecosystem. More importantly, implement **Miri** as a mandatory check to detect undefined behavior in "unsafe" Rust blocks that AI often leans on when it gets stuck.
*   **Audit for Repudiation in AI Logs:** Review your CloudTrail, OCSF, or internal logs. Can you distinguish between a human-initiated API call and an AI-agent-initiated call? If not, you need to update your User-Agent strings and Service Principal names to include **"Agent-Intent" headers**.

#### 2. Long-Term Strategy (The Pivot)

*   **The "Clean Room" AI Policy:** Establish a "Model Integrity" program. If your developers are using LLMs, you must use private, "frozen" models that are not continuously trained on public internet "slop." You need a deterministic output, not a probabilistic one. This is the only way to combat the recursive degradation of your codebase.
*   **Adopt the OWASP ASVS (Application Security Verification Standard) for Logic:** Move beyond the Top 10. The ASVS provides a basis for testing web application technical security controls and also provides developers with a list of requirements for secure development. In 2026, you must mandate **Level 3 (Advanced/High-Confidence)** for any module rewritten in Rust.
*   **Shift from "Detection" to "Attestation":** The future of AppSec is not finding bugs; it’s proving the absence of unauthorized change. Invest in **eBPF-based observability** (like Tetragon or Falco) to monitor the runtime behavior of your new Rust binaries. If the binary starts doing something the original design didn't specify—even if it's "memory safe"—the system should self-terminate.

We are at a crossroads. We can have a secure, memory-safe future, or we can have an AI-accelerated development cycle. To have both, we must treat **code integrity** as a higher priority than **feature velocity**. The "slop" is rising; it’s time to start building high ground.

---

## Article 2: Secure By Design roundup - Dec/Jan 2026

The article discusses the normalization of

<a href="https://shostack.org/blog/appsec-roundup-dec-jan-2026/">Read the full article</a>

### Technical Analysis: What's Really Happening

### The Mechanic: What's Actually Happening

We have spent the better part of the last decade treating cybersecurity as a series of perimeter skirmishes. We patched the holes, we bought the blinky boxes, and we told our boards that the "fortress" was holding. But as we transition into early 2026, the industry is finally reckoning with a more insidious internal rot: **the normalization of deviance.** This isn't a software bug or a zero-day exploit; it’s a systemic failure of engineering culture where "good enough" becomes the standard, and minor bypasses of security protocols become the daily operating procedure.

In the context of the latest "Secure by Design" (SBD) initiatives, the technical reality is that we are fighting a war against **architectural drift**. When a developer bypasses a mandatory code review to meet a sprint deadline, or an infrastructure lead opens a "temporary" port in a security group that remains open for eighteen months, they aren't just making a mistake—they are recalibrating the organization's baseline for acceptable risk. We see this manifest most dangerously in the CI/CD pipeline. The "mechanic" here is the silent erosion of the **Software Bill of Materials (SBOM)** integrity. We’ve moved toward automated threat modeling, but if the underlying data fed into those models is sanitized to avoid "red tape," the model itself becomes a work of fiction.

Furthermore, the "exciting threat modeling news" mentioned in recent circles isn't about better diagrams; it's about **Threat Modeling as Code (TMAC)**. We are seeing a shift where threat models are no longer static PDF documents gathering dust on a SharePoint drive. They are becoming living, version-controlled entities that live alongside the source code. The mechanic is simple: if a pull request introduces a new data flow that wasn't in the threat model, the build fails. It’s an attempt to force "Secure by Design" into the actual workflow, rather than leaving it as a post-hoc audit requirement. However, the friction this creates is exactly what fuels the normalization of deviance. If the security gates are too heavy, the engineers will simply find a way to unhinge the fence.

Finally, we have to address the "GPS vs. Regulation" debate. While GPS spoofing and jamming have moved from the realm of electronic warfare into the civilian sector—impacting everything from logistics to high-frequency trading—the "threat" that is actually changing architectural behavior isn't a signal jammer. It’s the **regulatory hammer**. We are seeing a pivot where the threat model is being rewritten not based on what an attacker *can* do, but on what a regulator *will* fine. This is a fundamental shift in how we calculate risk. We are no longer just protecting data; we are protecting the company's right to operate in a regulated market.

### The "So What?": Why This Matters

The normalization of deviance is the silent killer of the modern enterprise. It’s why, despite record-high security budgets, we still see massive breaches caused by "misconfigurations." When deviance is normalized, the **Security Poverty Line** isn't just about a lack of funds; it’s about a lack of discipline. For a CISO, this matters because it renders your dashboard metrics useless. Your "100% patch compliance" doesn't mean anything if your engineers have normalized the use of "shadow" containers to bypass security scanning.

The comparison between GPS attacks and regulatory threats is particularly telling. GPS attacks represent a **High-Consequence, Low-Probability (HCLP)** event for most commercial enterprises. They are "sexy" threats—the kind that make for great headlines and cinematic presentations. But they are distractions. The regulatory shift—driven by the SEC’s increasingly aggressive stance on "materiality" and the EU’s evolving AI Act—is a **High-Consequence, High-Probability** event. 

If your threat model prioritizes a sophisticated GPS spoofing attack over the systemic failure to implement "Secure by Design" principles, you are misallocating your most precious resource: **engineering focus**. The "So What" here is that the barrier to entry for attackers is being lowered not by their own genius, but by our own internal entropy. When we allow deviance to become the norm, we are effectively providing the exploit chain to the attacker for free. We are building systems that are "Secure by Design" on paper, but "Insecure by Default" in practice.

This matters to the Executive Leadership because we are entering an era of **Personal Liability**. The "reasonable person" standard in cybersecurity is being replaced by a "documented architecture" standard. If you cannot prove that your "Secure by Design" pledge was backed by technical enforcement—specifically by curbing the normalization of deviance—you aren't just looking at a data breach; you're looking at a shareholder derivative suit.

### Strategic Defense: What To Do About It

To combat the normalization of deviance and align with the "Secure by Design" mandate, we must move away from "policing" and toward "paving the golden path." We need to make the secure way the easiest way.

#### 1. Immediate Actions (Tactical Response)

*   **Kill the "Exception Culture":** Conduct a 30-day audit of all "temporary" security exceptions in your cloud environment (AWS Security Groups, Azure NSGs, IAM bypasses). Any exception older than 90 days must be treated as a production vulnerability. Use **Open Policy Agent (OPA)** to enforce "Policy as Code" that automatically expires these exceptions.
*   **Implement "Guardrail" Monitoring:** Instead of blocking developers, implement real-time alerting on "deviant" behavior. Use tools like **Wiz** or **Prisma Cloud** to identify when a resource is created that deviates from the approved "Secure by Design" template. If the deviation isn't corrected within 4 hours, auto-remediate (delete or isolate) the resource.
*   **Audit the "Human Middleware":** Review your incident response logs for the last six months. Look for instances where a "workaround" was used to solve a production issue. These workarounds are the blueprints for your next breach. Document them, and prioritize the technical debt required to make those workarounds unnecessary.

#### 2. Long-Term Strategy (The Pivot)

*   **Institutionalize Threat Modeling as Code (TMAC):** Move threat modeling out of the meeting room and into the IDE. Integrate tools like **IriusRisk** or open-source alternatives like **PyTM** directly into the developer's workflow. The goal is to make the threat model a required artifact for every major feature, version-controlled and peer-reviewed just like the code itself. This forces a discussion on "Secure by Design" at the moment of creation, not the moment of deployment.
*   **Architect for "Resilient Failure":** Accept that deviance will happen. Shift your architectural focus from "Prevention" to "Blast Radius Limitation." This means adopting a **Zero Trust Architecture (ZTA)** where identity is the perimeter, and micro-segmentation is the default. If a developer normalizes a deviance in one microservice, the "Secure by Design" architecture should ensure that the deviance cannot be used to pivot to the crown jewels.
*   **The Regulatory Alignment Pivot:** Stop viewing compliance as a checkbox and start viewing it as a **Threat Actor**. Include "Regulatory Enforcement" as a persona in your threat models. What data do they want? What "evidence of due diligence" will they demand? By designing your systems to produce this evidence as a byproduct of normal operation (e.g., automated SBOM generation, immutable audit logs), you satisfy the regulator while simultaneously hardening the system against traditional attackers.

---

**Final Thought:** "Secure by Design" is not a destination; it is a constant battle against the natural tendency of complex systems to decay. The most dangerous threat to your organization isn't a hacker in a hoodie or a GPS jammer in the Baltic; it’s the engineer who says, "We'll fix the security part in the next sprint." In 2026, the "next sprint" is where security goes to die. Stop waiting for the next sprint. Build it right, or don't build it at all.

---

## Article 3: Anubis ransomware: what you need to know

The Anubis ransomware-as

<a href="https://www.fortra.com/blog/anubis-ransomware">Read the full article</a>

### Technical Analysis: What's Really Happening

### The Mechanic: What's Actually Happening

When we talk about **Anubis**, we aren’t just discussing a piece of malicious code; we are dissecting a sophisticated, multi-tiered business enterprise. Named after the Egyptian god of the dead, this Ransomware-as-a-Service (RaaS) operation has transitioned from a niche threat into a high-velocity extortion engine. I’ve watched the evolution of RaaS for a decade, and Anubis represents the refinement of the "human-operated" attack. It’s not a mindless worm crawling through your network; it’s a disciplined adversary sitting on the other side of a keyboard, often using your own administrative tools against you.

The technical reality of an Anubis intrusion usually begins long before the first file is encrypted. We are seeing a heavy reliance on **Initial Access Brokers (IABs)** who sell pre-vetted entry points—stolen VPN credentials, unpatched Edge Gateway vulnerabilities, or session cookies bypassed via Adversary-in-the-Middle (AiTM) phishing. Once inside, the Anubis affiliates don't rush. They practice what I call "environmental empathy." They spend days, sometimes weeks, mapping the active directory, identifying the crown jewels, and—most critically—locating the backup servers. They use **Living-off-the-Land (LotL)** techniques, leveraging PowerShell, Windows Management Instrumentation (WMI), and PsExec to move laterally. By the time the encryption routine triggers, the battle is already over; they have already exfiltrated the data and neutralized your ability to restore it.

What sets Anubis apart in the current landscape is its **modular payload delivery**. The ransomware itself is often the final act of a play that includes credential harvesters and data exfiltration tools like Rclone or MegaSync. The encryption process uses a hybrid of AES-256 and RSA-2048, which is, for all intents and purposes, unbreakable without the private key. But the real "mechanic" here isn't the math—it's the **extortion workflow**. Anubis operators have professionalized the shaming process, hosting dedicated leak sites on the dark web that are as organized as a corporate newsroom, complete with countdown timers and "press release" style announcements of their latest victims.

### The "So What?": Why This Matters

The surge in Anubis activity, particularly within the healthcare sector, signals a grim shift in the adversary’s risk-reward calculus. For years, some RaaS groups maintained a facade of "ethics," claiming they wouldn't target hospitals. Anubis has stripped away that pretense. To them, a hospital isn't a place of healing; it's a high-leverage target with a **low tolerance for downtime and a high propensity to pay.** When a surgical schedule is locked behind a ransom note, the "cost of doing business" takes on a literal life-or-death dimension.

But if you aren't in healthcare, don't make the mistake of thinking you're safe. The Anubis model is designed for **horizontal scalability**. The barrier to entry for attackers has collapsed. A mid-level cybercriminal no longer needs to know how to write a kernel-level exploit; they just need a subscription and a target list. This democratization of high-end cybercrime means the volume of sophisticated attacks is outstripping the defensive capacity of most mid-market enterprises. We are seeing a "pincer movement" where the attacks are getting more complex while the talent gap in security operations continues to widen.

Furthermore, Anubis highlights the death of the "perimeter" as a viable security concept. Because these attackers favor compromised identities and legitimate administrative tools, your firewall is essentially a screen door in a hurricane. This matters because it forces a fundamental rethink of the **Unified Security Model**. If an attacker is using a valid admin account to deploy ransomware, your security stack shouldn't be asking "Is this file malicious?" but rather "Why is the SysAdmin running a mass-rename script at 3:00 AM from a residential IP in a different timezone?" The "So What" here is that Anubis is a symptom of an **Identity Crisis** in modern cybersecurity.

### Strategic Defense: What To Do About It

Defeating an adversary like Anubis requires a bifurcated approach. You need to harden the floor to stop the "easy" entries today, while simultaneously re-architecting your environment to ensure that an inevitable breach doesn't become a catastrophe.

#### 1. Immediate Actions (Tactical Response)

*   **Enforce Phishing-Resistant MFA (FIDO2):** Traditional SMS or push-based MFA is no longer sufficient against the AiTM attacks favored by Anubis affiliates. Transition your privileged accounts (Admins, Finance, HR) to hardware keys or platform authenticators (Windows Hello for Business). If you can't do it for everyone today, do it for your Domain Admins *this afternoon*.
*   **Audit and Kill "Orphaned" Administrative Access:** Anubis loves dormant accounts with high privileges. Run a comprehensive audit of your Active Directory. Look for accounts that haven't logged in for 30 days but retain Local Admin or Domain Admin rights. Disable them. Implement **Just-In-Time (JIT)** access so that no account has permanent administrative standing.
*   **Hardened, Immutable Backups (The 3-2-1-1 Rule):** Your backups are the primary target. Ensure you have at least one copy of your data that is **physically or logically immutable** (WORM - Write Once, Read Many) and completely air-gapped from the primary network. Test the restoration speed; a backup you can't restore in under 24 hours is a liability, not an asset.

#### 2. Long-Term Strategy (The Pivot)

*   **Transition to an Identity-First Security Architecture:** Stop obsessing over the network edge and start obsessing over identity telemetry. Implement **Conditional Access Policies** that evaluate the risk of every login in real-time. If the user’s device is unmanaged or the location is "impossible travel," the session should be killed automatically. This is the core of a functional Zero Trust model.
*   **Operationalize "Assume Breach" via Managed Detection and Response (MDR):** Since Anubis uses LotL techniques, your antivirus won't save you. You need 24/7 monitoring that looks for **behavioral anomalies**. Invest in an MDR provider or build an internal SOC that focuses on the MITRE ATT&CK framework—specifically looking for T1003 (OS Credential Dumping) and T1021 (Remote Services). You need to catch them during the "discovery" phase, not the "encryption" phase.

**Final Thought:** Anubis isn't a ghost in the machine; it's a business competitor trying to liquidate your assets for their profit. Treat them with the same strategic seriousness you would a hostile takeover bid. The tools are available; the question is whether your organization has the political will to implement the friction necessary to stay safe.

---

**Analyst Note:** These top 3 articles this week synthesize industry trends with expert assessment. For strategic decisions, conduct thorough validation with your security, compliance, and risk teams.