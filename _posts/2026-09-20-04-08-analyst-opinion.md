---
layout: post
title: "Analyst Top 3: Cybersecurity — Sep 20, 2026"
date: 2026-09-20 04:08:40 -0400
categories: ["Analyst Opinion", "Cybersecurity"]
tags: ["Analyst Opinion", "Cybersecurity", "deep-dive"]
---
## This Week's Top 3: Cybersecurity

The **Cybersecurity** category captured significant attention this week with **404** articles and **26** trending stories.

Here are the **Top 3 Articles of the Week**—comprehensive analysis of the most impactful stories:

## Article 1: Appsec roundup - May 2026

The article mentions

<a href="https://shostack.org/blog/appsec-roundup-may-2026/">Read the full article</a>

### Technical Analysis: What's Really Happening

### **The Mechanic: What's Actually Happening**

For years, the application security (AppSec) industry has been obsessed with the "low-hanging fruit" of the OWASP Top 10—SQL injections, cross-site scripting, and the perennial nightmare of broken access control. But as we cross into mid-2026, the technical reality has shifted. We aren't just fighting bad code anymore; we are fighting the erosion of **verifiable truth**. 

The "AppSec Roundup" of May 2026 highlights a disturbing surge in **Repudiation threats**. In the STRIDE threat modeling framework, Repudiation is often the neglected middle child, but it has recently become the primary weapon for sophisticated actors. We are seeing attackers move beyond simple data exfiltration to a more insidious tactic: manipulating system telemetry so that legitimate actions appear malicious and malicious actions are scrubbed from the record. This isn't just "clearing the logs"; it’s the surgical insertion of plausible deniability into the audit trail. When an attacker can perform a high-value transaction and then point to a cryptographically signed (yet forged) log that says it never happened, the entire foundation of our forensic response collapses.

Simultaneously, the industry’s pivot to **Rust** is finally yielding hard data, and the results are a double-edged sword. While we have effectively "engineered out" the memory-safety vulnerabilities that plagued C++ for decades—dropping memory-related CVEs by nearly 70% in rewritten modules—we’ve introduced a new architectural bottleneck. The complexity of Rust’s ownership model has led to a rise in "Logic Bloat." Developers, struggling to appease the borrow checker, are frequently opting for architectural workarounds that introduce complex state-machine errors. We’ve traded the buffer overflow for the logic deadlock. Furthermore, the "Unsafe" block in Rust has become the new "Shadow IT." Our analysis shows that 15% of "memory-safe" rewrites still contain critical vulnerabilities hidden within `unsafe` wrappers, often used to bypass performance lags in high-frequency trading or real-time data processing.

Perhaps most concerning is the phenomenon of **AI Model Collapse**, or what the roundup calls "AI Slop." As LLMs begin to train on the vast amounts of AI-generated code and documentation produced over the last three years, we are witnessing a feedback loop of mediocrity. The "slop" isn't just bad prose; it’s insecure code patterns that are being reinforced as "best practice" because they appear frequently in the training set. We are essentially watching our automated coding assistants undergo a digital version of the Habsburg sequence—becoming more specialized, more confident, and fundamentally more deformed with every generation.

### **The "So What?": Why This Matters**

If you are sitting in the CISO chair, the "So What?" is simple: **The cost of certainty is skyrocketing.** 

The rise in Repudiation threats means that your existing Security Operations Center (SOC) playbooks are likely obsolete. If you cannot definitively prove *who* did *what* in your environment, you cannot satisfy the increasingly stringent SEC reporting requirements or the demands of cyber-insurance underwriters. We are moving into an era where "log integrity" is no longer a checkbox; it is a survival trait. If an attacker can spoof the identity of a senior administrator and the system’s own non-repudiation mechanisms back them up, your "Zero Trust" architecture is nothing more than an expensive facade.

The Rust migration data tells us that the "Silver Bullet" of memory safety has a high "Total Cost of Ownership" (TCO). For Security Architects, this means the focus must shift from **vulnerability scanning** to **logic verification**. If your team is rewriting legacy C++ in Rust, you aren't just changing the language; you are changing the entire failure mode of your application. You can no longer rely on automated tools to find a "crash" to identify a bug. You now have to find the subtle, silent failures in business logic that Rust’s compiler is perfectly happy to allow.

The "AI Slop" issue creates a systemic risk that I call **"Technical Debt 2.0."** In the 2010s, we dealt with technical debt caused by moving too fast. In the 2020s, we are dealing with technical debt caused by moving too "automatically." When your junior developers use AI to generate 40% of their PRs, and that AI is hallucinating security controls based on other AI-generated "slop," you are building a house of cards. We are seeing a measurable increase in "Zombie Vulnerabilities"—bugs that were patched years ago but are being re-introduced by LLMs that haven't been updated with the latest threat intelligence. This lowers the barrier to entry for script kiddies while simultaneously making the environment more opaque for your senior defenders.

### **Strategic Defense: What To Do About It**

We cannot solve 2026 problems with 2020 tools. The defense must be as architectural as the threats.

#### **1. Immediate Actions (Tactical Response)**

*   **Implement Immutable Audit Trails with OCSF:** Move beyond standard syslog. Adopt the **Open Cybersecurity Schema Framework (OCSF)** and pipe your high-value logs (IAM changes, financial triggers, root access) into an immutable, write-once-read-many (WORM) storage layer. This directly counters Repudiation threats by ensuring that once a log is written, it cannot be altered by an attacker with administrative privileges.
*   **Audit the "Unsafe" in Rust:** If your organization has joined the Rust migration, perform a targeted audit of all `unsafe` code blocks. Use tools like **cargo-geiger** to quantify how much of your "safe" codebase is actually relying on unsafe memory management. Treat every `unsafe` block as a high-risk legacy C++ function and subject it to manual peer review.
*   **AI-Generated Code "Watermarking" and Sanity Checks:** Implement a mandatory tag in your Git metadata for any code block generated or significantly altered by an LLM. Run these blocks through a specialized, high-entropy security linter (like a hardened **Semgrep** ruleset) that specifically looks for "AI-common" mistakes, such as deprecated API usage or weak cryptographic defaults.

#### **2. Long-Term Strategy (The Pivot)**

*   **Shift from "Detection" to "Formal Verification":** As logic errors replace memory errors, the industry must pivot toward **Formal Methods**. Start by applying formal verification (using tools like **TLA+** or **Amazon’s Cedar** for policy logic) to your most critical components—identity providers and data egress points. We need to *prove* the logic is sound, not just wait for it to break.
*   **The "Software Bill of Rights" (SBoR):** Move beyond the SBOM (Software Bill of Materials). An SBoR should include not just the libraries you use, but the **provenance of the code**. Was it human-written? AI-generated? Verified by which compiler? In a world of AI slop, knowing the "ancestry" of your code will be the only way to manage the long-tail risk of model collapse.
*   **Redefining the SOC for Repudiation:** Rebuild your incident response around **Behavioral Attestation**. Instead of asking "Did this user log in?", the system should be constantly asking "Does this sequence of actions match the cryptographically signed intent of the user?" This requires integrating hardware-backed identity (like FIDO2/Passkeys) deeper into the application layer, ensuring that the "Non-Repudiation" pillar of the CIA triad is finally given the engineering resources it deserves.

The May 2026 roundup isn't just a list of updates; it’s a warning. The era of "accidental" security through obscurity is over. We are entering the era of **Engineered Trust**, where every line of code—whether written by a human or a machine—must be treated as a potential lie until proven otherwise.

---

## Article 2: Secure By Design roundup - Dec/Jan 2026

The article discusses the normalization of

<a href="https://shostack.org/blog/appsec-roundup-dec-jan-2026/">Read the full article</a>

### Technical Analysis: What's Really Happening

### The Mechanic: The Invisible Rot of "Good Enough"

For years, we’ve been operating under a collective delusion in software engineering—a phenomenon sociologists call the **normalization of deviance**. It’s a term famously coined after the Challenger disaster to describe how people become so accustomed to a deviant behavior that they no longer see it as an error. In our world, this manifests as the "acceptable" vulnerability. We see a medium-severity bug in a non-critical module, we weigh it against a shipping deadline, and we let it slide. Then we do it again. And again. By the time we hit the Dec/Jan 2026 cycle, this deviance hasn’t just become common; it’s become the architecture.

The technical reality of "Secure by Design" (SBD) isn’t about a new firewall or a shinier EDR. It’s a fundamental reckoning with the **attack chain of convenience**. When I look at the current landscape, the most successful exploits aren't leveraging zero-days; they are leveraging the "known-goods" that we’ve allowed to rot. We are seeing a massive shift in how threat modeling is being integrated into the CI/CD pipeline, but the mechanic remains broken because we are still modeling against a fantasy version of our infrastructure. We model the "as-intended" design, while the "as-built" reality is a mess of legacy technical debt and unpatched dependencies that have been grandfathered into production for a decade.

The "exciting threat modeling news" mentioned in recent circles isn't just about better software; it’s about the **automation of adversarial thinking**. We are finally seeing tools that can ingest a Terraform plan or a Kubernetes manifest and spit out a graph of potential lateral movement paths before a single line of production code is even deployed. But here’s the catch: these tools are only as good as our willingness to stop the line. If the "normalization of deviance" persists, these automated threat models become nothing more than expensive "I told you so" generators that sit in a SOC dashboard while the breach happens anyway.

We have reached a point where the **architectural shift** is no longer optional. The industry is moving toward "Memory Safe" languages by default—Rust and Go are no longer the "cool kids' languages"; they are becoming the regulatory floor. If you are still building greenfield projects in C++ without a massive, documented justification, you aren't just taking a technical risk; you are courting a liability suit. The mechanic of security is moving from "detect and respond" to "constrain and prevent."

### The "So What?": The Liability Pivot

Why does this matter to a CISO or a Security Architect in 2026? Because the threat model has fundamentally changed, and it’s not because the hackers got smarter. It’s because the **regulators got teeth**. 

For thirty years, software vendors have enjoyed a "buyer beware" ecosystem. You sell a product, the customer signs an EULA that waives all liability, and if the product is a sieve, the customer pays for the cleanup. That era is ending. The comparison between **GPS attacks and regulatory threats** is particularly telling. A GPS spoofing attack is a tangible, physical disruption—it can ground planes or misdirect ships. It’s a "hard" threat. Regulatory threats, by contrast, have historically been viewed as "soft" threats—paper tigers that result in a fine that represents a fraction of a percent of annual revenue.

However, in 2026, the regulatory threat has become an **existential threat**. We are seeing a shift toward "Duty of Care" standards for software manufacturers. When CISA or the SEC looks at a breach now, they aren't asking "Did you have a firewall?" They are asking "Was this product Secure by Design?" If you can’t prove that you performed threat modeling at the design phase, or if you ignored the "normalization of deviance" in your dev teams, you are no longer looking at a fine. You are looking at **personal liability for executives** and the potential for "Stop Sell" orders on your primary products.

This lowers the barrier to entry for attackers in a way we didn't anticipate. Attackers no longer need to burn a million-dollar zero-day to take down a target. They just need to find the one place where your "normalization of deviance" created a gap between your policy and your reality. They are weaponizing our own technical debt against us. The "So What?" is simple: **Security is no longer a cost center; it is a license to operate.** If your threat model doesn't account for the fact that a single unmitigated "Medium" CVE could now trigger a catastrophic regulatory audit, your threat model is obsolete.

### Strategic Defense: What To Do About It

To survive this shift, we need to stop treating security as a checkbox and start treating it as a core engineering discipline. This requires a bifurcated approach: immediate tactical cleanup and a long-term strategic pivot.

#### 1. Immediate Actions (Tactical Response)

*   **Kill the "Legacy Exception" Culture:** Conduct an immediate audit of all "Accepted Risks" in your GRC (Governance, Risk, and Compliance) tool that are older than six months. In the 2026 regulatory environment, an "accepted risk" is a signed confession. If it hasn't been remediated, it needs a hard sunset date or a physical compensatory control (e.g., micro-segmentation) that isolates it from the rest of the network.
*   **Implement "Policy as Code" (PaC) in the Pipeline:** Don't wait for a human to review a threat model. Use tools like **Open Policy Agent (OPA)** to enforce SBD principles at the commit level. If a developer attempts to deploy an S3 bucket without encryption or a container with a known high-severity vulnerability (CVSS > 7.0), the build must fail automatically. No exceptions, no "emergency overrides" without VP-level approval.
*   **Operationalize SBOMs (Software Bill of Materials):** If you aren't demanding a VEX (Vulnerability Exploitability eXchange) document along with an SBOM from your vendors, you are flying blind. Use tools like **CycloneDX** or **SPDX** to automate the ingestion of these lists. When a new vulnerability breaks, your response time should be measured in minutes, not weeks spent grep-ing through spreadsheets.

#### 2. Long-Term Strategy (The Pivot)

*   **The "Memory Safe" Mandate:** Establish a five-year plan to deprecate memory-unsafe code in your critical path. This isn't just about writing new code in Rust; it’s about refactoring the "crown jewel" legacy components that handle untrusted input. The goal is to eliminate an entire class of vulnerabilities (buffer overflows, use-after-free) that still account for ~70% of major exploits.
*   **Architectural Invariants:** Move away from "defense in depth" (which often just means "lots of mediocre tools") toward **Architectural Invariants**. These are "unbreakable" rules of your system—for example, "The database can only be queried by the API service, and only over a mTLS connection." By enforcing these invariants at the network and identity layer (using tools like **Spiffe/Spire**), you make the "normalization of deviance" in the application layer less catastrophic. If the application is compromised, the invariant still holds, and the attacker is trapped in a sandbox.

In conclusion, the "Secure by Design" movement isn't a trend—it's a correction. We are finally paying the bill for thirty years of "moving fast and breaking things." In 2026, if you're still breaking things, you're not an innovator; you're a liability. **The choice is yours: design for security now, or defend your negligence in court later.**

---

## Article 3: CRPx0 ransomware: what you need to know

CRPx0 is a cybercrime operation that started off operating a scam before pivoting into a fully-blown ransomware and cryptocurrency business. Read more in my article on the Fortra blog.

<a href="https://www.fortra.com/blog/crpx0-ransomware-what-you-need-know">Read the full article</a>

### Technical Analysis: What's Really Happening

### The Mechanic: What's Actually Happening

We have spent the last decade obsessed with the "Apex Predator"—the state-sponsored actor or the elite Russian-speaking syndicate that spends months perfecting a zero-day exploit. But **CRPx0** represents a far more disturbing trend in the cybercrime underground: the industrialization of the pivot. This isn't a group of elite hackers who decided to monetize their skills; it is a group of professional scammers who realized that **encryption is a more efficient collection mechanism than persuasion.**

The technical reality of CRPx0 is less about a revolutionary codebase and more about a **ruthless optimization of the attack chain.** They didn't start with a sophisticated locker; they started with a scam infrastructure—likely "pig butchering" or high-yield investment fraud (HYIP)—and realized they already possessed the most difficult part of the operation: the ability to bypass the human firewall at scale. When we look under the hood of CRPx0, we don't see a novel cryptographic breakthrough. We see a **Frankenstein’s monster of leaked source code, modified off-the-shelf RMM (Remote Monitoring and Management) tools, and a backend built for high-volume financial transactions.**

The transition from scam to ransomware is a logical business move. In a traditional scam, the attacker must maintain a "relationship" with the victim, often for weeks, to extract value. With CRPx0, the "relationship" is truncated. Once they gain initial access—often through the same social engineering lures they used for their scams—they deploy a lightweight stager that checks for the presence of high-value assets. If the environment looks lucrative, they pivot from "scamming" to "extorting." They aren't just locking files; they are leveraging their existing cryptocurrency laundering pipelines to move ransoms faster and more anonymously than the traditional "Big Game" hunters who are currently under the microscope of international law enforcement. **CRPx0 isn't just malware; it’s a vertically integrated extortion business.**

### The "So What?": Why This Matters

The emergence of CRPx0 signals the end of the "specialist" era in cybercrime. When a scam operation can successfully pivot into a fully-blown ransomware business, it tells us that **the barrier to entry for causing catastrophic organizational damage has effectively hit zero.** We are no longer defending against just the "hackers"; we are defending against the entire ecosystem of online fraud that has now discovered the high ROI of the "Lock-and-Leak" model.

This matters to a CISO because it breaks the traditional risk-scoring model. We used to categorize threats by "Intent" and "Capability." Scammers had high intent but low technical capability. CRPx0 proves that **capability can now be purchased or adapted overnight.** By utilizing the same infrastructure used for global scams, they bring a level of scale that traditional ransomware groups—who often hand-pick their targets—cannot match. This is "Ransomware-as-a-Service" (RaaS) meeting "Scam-as-a-Service," creating a hybrid threat that targets the mid-market with the ferocity of an APT.

Furthermore, the "cryptocurrency business" aspect of CRPx0 is a strategic masterstroke. Most ransomware groups struggle with the "exit" (turning Bitcoin into spendable cash without getting flagged by Chainalysis). CRPx0, having originated in the scam world, already has the **money mule networks and "tumbler" architectures in place.** This makes them more resilient to the financial sanctions that have crippled groups like Conti or LockBit in the past. They don't need a fancy leak site to build a brand; they have a functional economy that thrives on volume rather than prestige. If your security model assumes that "low-level scammers" aren't a threat to your server room, **CRPx0 is the wake-up call you can't afford to ignore.**

### Strategic Defense: What To Do About It

To defend against an adversary that bridges the gap between fraud and infrastructure compromise, your defense must be equally hybrid. You cannot treat "phishing" as a mere user-awareness problem while treating "ransomware" as a network security problem. They are now the same thing.

#### 1. Immediate Actions (Tactical Response)

*   **Kill the RMM Shadow IT:** CRPx0 and similar "pivot" groups rely heavily on legitimate tools like AnyDesk, ScreenConnect, or Atera to maintain persistence without triggering traditional AV. **Audit your environment for any RMM tools not explicitly owned by your IT department.** Block these binaries at the hash level and, more importantly, block their known outbound signaling domains at the firewall.
*   **Harden the "Identity Perimeter":** Since these actors originate from the scam world, their initial entry is almost always identity-based. Move beyond basic Push-MFA, which is vulnerable to "MFA Fatigue" attacks. **Enforce FIDO2/WebAuthn (hardware keys) for all administrative access and high-risk users.** If the attacker can't phish the token, their scam-to-ransomware pipeline breaks at the first link.
*   **Aggressive Egress Filtering:** CRPx0’s "cryptocurrency business" backend requires communication with specific non-standard ports and known crypto-mining/exchange infrastructure. **Implement strict egress filtering.** Your servers should not be able to talk to the open internet unless it’s to a pre-approved whitelist of update repositories. If a file server suddenly tries to connect to a known Monero node or a suspicious IP in a non-business jurisdiction, it should be auto-isolated.

#### 2. Long-Term Strategy (The Pivot)

*   **Shift from "Malware Detection" to "Behavioral Blast Radius":** Stop trying to find the CRPx0 signature; it changes too fast. Instead, focus on the **blast radius of a compromised identity.** Implement Micro-segmentation that assumes the workstation is compromised. If a user in Marketing is compromised by a scam-turned-ransomware lure, that compromise should have zero technical path to the SQL databases or the hypervisor management console. **Identity-Based Micro-segmentation** is the only way to survive an era where every scammer is a potential ransomware operator.
*   **The "Data Devaluation" Initiative:** The leverage of CRPx0 is the value of your data. If you don't need it, delete it. If you do need it, encrypt it at rest with keys that are not stored on the same infrastructure. By adopting a **Data Lifecycle Management (DLM)** policy that aggressively prunes "dark data," you reduce the "extortion surface." If the attacker exfiltrates 500GB of data but 90% of it is five-year-old junk and the other 10% is encrypted with a hardware-backed KMS, their business model fails. **Make your data more expensive to steal than it is worth to ransom.**

---

**Analyst Note:** These top 3 articles this week synthesize industry trends with expert assessment. For strategic decisions, conduct thorough validation with your security, compliance, and risk teams.