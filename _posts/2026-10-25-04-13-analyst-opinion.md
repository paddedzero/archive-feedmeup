---
layout: post
title: "Analyst Top 3: Cybersecurity — Oct 25, 2026"
date: 2026-10-25 04:13:38 -0400
categories: ["Analyst Opinion", "Cybersecurity"]
tags: ["Analyst Opinion", "Cybersecurity", "deep-dive"]
---
## This Week's Top 3: Cybersecurity

The **Cybersecurity** category captured significant attention this week with **411** articles and **25** trending stories.

Here are the **Top 3 Articles of the Week**—comprehensive analysis of the most impactful stories:

## Article 1: Appsec roundup - May 2026

Recent discussions highlight the **operational

<a href="https://shostack.org/blog/appsec-roundup-may-2026/">Read the full article</a>

### Technical Analysis: What's Really Happening

### The Mechanic: What's Actually Happening

We have entered the "Correction Era" of the mid-2020s. For the past two years, the C-suite has been intoxicated by the promise of generative AI as a panacea for headcount and productivity. But as we look at the landscape in May 2026, the bill is coming due, and it’s being presented in two currencies: **technical debt and logic regressions.**

The most striking technical failure this month isn't a sophisticated zero-day in a firewall; it’s the **uutils coreutils rewrite in Rust**. On paper, this was a security win. We’ve been told for years that memory-safe languages like Rust are the silver bullet for the vulnerabilities that have plagued C/C++ since the 1970s. However, as Colin Funk and Michal Zalewski (lcamtuf) have pointed out, the Rust rewrite of core utilities—the very bedrock of our operating systems—has introduced a series of **logic-based CVEs**. 

The mechanic here is a classic "Chesterton’s Fence" violation. The original C-based coreutils were messy, yes, but they were also battle-hardened by forty years of edge cases. They accounted for the "dark matter" of systems programming: **race conditions during file creation, complex permission inheritance, and symlink attacks.** The developers rewriting these tools in Rust focused on memory safety but ignored the **semantic safety** of the operations. They built a "safe" car but forgot to check if the brakes actually worked on ice. This is a microcosm of our current industry: we are replacing legacy systems with "modern" equivalents that solve yesterday’s problems while re-introducing vulnerabilities we solved in the 1990s.

Simultaneously, we are seeing the "AI Layoff Bill" manifest. Sarah Choudhary’s assessment is brutal but accurate: CTOs who slashed engineering teams in 2024 and 2025 in favor of AI-augmented developers are now realizing that **AI-generated code is a maintenance nightmare.** AI doesn't write code; it predicts the next token. It doesn't understand the long-term architectural implications of a specific library choice. We are seeing a massive spike in "maintenance friction" where the time saved in initial development is being eclipsed by the time required to debug "hallucinated logic" and brittle dependencies. 

Finally, the threat landscape is shifting toward **physical-digital hybrid scams**, as seen in the Rogers iPad incident. Attackers aren't just stealing data; they are using social engineering to turn customers into unwitting mules for physical hardware. This reflects a broader trend: as our digital perimeters become harder to crack through traditional means, attackers are pivoting back to the **human-physical interface**, exploiting the trust we place in "official" corporate communications.

### The "So What?": Why This Matters

If you are a CISO or a Security Architect, the "So What?" is simple: **Your attack surface is becoming more opaque just as your ability to maintain it is being hollowed out.**

The "Keys on Doormats" research by Nurullah Demir highlights a persistent, systemic failure in secrets management. Despite a decade of warnings, API credentials remain exposed in client-side JavaScript at an alarming rate. This isn't just a "developer mistake"; it’s a failure of the **Unified Security Model**. We are building complex, agentic AI systems (as Phil Venables notes) that rely on these very APIs to function. If an "Agentic AI" can access an exposed key, it can execute actions at high frequency—much like the High-Frequency Trading (HFT) systems Venables references—leading to **catastrophic automated loss** before a human even sees an alert.

The lack of a "Badness Meter" for AI, as noted by the Berryville Institute, means we are flying blind. We are deploying LLMs to secure source code (as Anthropic suggests), but we have no standardized way to measure if the AI is actually making the code safer or just making it *look* safer. This creates a **false sense of security** that is more dangerous than known vulnerability. 

Furthermore, the OWASP Strategic Plan's controversy stems from a fundamental tension: how do we govern a landscape that is moving faster than our ability to document it? If our core utilities (uutils) are failing on basic logic, and our hiring processes are being skewed by AI self-preferencing (as Jiannan Xu’s research suggests), we are effectively **poisoning the well of our own infrastructure.** We are hiring less-capable humans via biased AI to manage brittle code generated by LLMs, running on "safe" languages that are prone to old-school race conditions. 

This is not a "shift left" or "shift right" problem. This is a **foundational integrity crisis.**

### Strategic Defense: What To Do About It

To navigate this, we must move away from the "AI will fix it" mentality and return to **first-principles engineering**, albeit with modern guardrails.

#### 1. Immediate Actions (Tactical Response)

*   **Audit the "Modernization" Projects:** Immediately review any ongoing "rewrite" projects (e.g., C to Rust, or Legacy to Cloud-Native). Ensure the testing suite includes **logic-based fuzzing** and race-condition checks, not just memory-safety scans. Use tools like `syzkaller` or specialized logic checkers to ensure the "hard-learned lessons" of the legacy code haven't been discarded.
*   **Hard-Stop on Client-Side Secrets:** Implement automated blocking at the CI/CD level for any API keys or secrets detected in client-side code. Use tools like **TruffleHog** or **Gitleaks**, but specifically tune them to scan the *output* of your build processes (the transpiled JS), not just the source code.
*   **Implement "Agentic Guardrails":** If your organization is deploying Agentic AI, apply the lessons from HFT. This means **circuit breakers**. If an AI agent exceeds a specific API call volume or attempts a "high-stakes" transaction (like a permission change), it must require a physical "dead man's switch" or human-in-the-loop approval.

#### 2. Long-Term Strategy (The Pivot)

*   **The "AI Maintenance" Tax:** Adjust your 2027 budget now to account for the "Maintenance Bill." Stop assuming AI reduces headcount; instead, pivot your headcount toward **Senior Reviewers and Architects.** You need fewer "coders" and more "code auditors" who can spot the subtle logic flaws that LLMs and junior developers miss.
*   **Redefine Threat Modeling for Containment:** Follow Anthropic’s lead in "containing" LLMs. Treat every AI model as a **potentially compromised third-party vendor.** This means strict network isolation, input/output sanitization, and "No-Trust" zones between the AI and your core production data.
*   **Logic-First Security Training:** Re-train your AppSec teams. The last five years were about memory safety and cloud configuration. The next five years will be about **business logic and race conditions.** We need to bring back the "lcamtuf" mindset: understanding how the OS actually handles files, locks, and permissions. 

**The Bottom Line:** Security in 2026 isn't about the newest tool; it's about **not forgetting what we already learned.** We are currently trading deep expertise for shallow automation, and the "iPad scammers" and "Rust race conditions" are just the first symptoms of that rot. **Build for logic, not just for safety.**

---

## Article 2: Secure By Design roundup - Dec/Jan 2026

The article highlights a "normalization

<a href="https://shostack.org/blog/appsec-roundup-dec-jan-2026/">Read the full article</a>

### Technical Analysis: What's Really Happening

### The Mechanic: What's Actually Happening

We are currently witnessing the most significant architectural regression in the history of computing, and we are calling it "innovation." 

In his recent analysis, Wunderwuzzi (Johann Rehberger) highlights a phenomenon that should keep every CISO awake: **The Normalization of Deviance in AI.** To understand the technical reality here, we have to look past the shiny chat interfaces and into the plumbing. In traditional software engineering, a system that intermittently ignores its instructions, leaks its internal configuration, or executes unauthorized code is considered "broken." In the world of Large Language Models (LLMs) and Generative AI, these same catastrophic failures are rebranded as "probabilistic behaviors" or "known limitations."

The "drift" Rehberger describes is a social process masquerading as a technical one. We are seeing a fundamental shift where security teams are being pressured to accept **non-deterministic security boundaries.** In a standard web application, if I tell a database "do not show User A the records of User B," and it does so anyway, we file a CVE and patch it immediately. In an AI-integrated enterprise, when a prompt injection bypasses a system prompt to exfiltrate data, the industry’s collective response has become a shrug and a suggestion to "improve the system instructions." 

This is the **Normalization of Deviance** in real-time. It is the same organizational rot that led to the Challenger disaster—a slow, incremental acceptance of small risks until the "unthinkable" becomes inevitable. Technically, this manifests as the **collapse of the TCB (Trusted Computing Base).** We are injecting untrusted, unvalidated, and often adversarial user input directly into the "brain" of the application, then acting surprised when the application follows the user's instructions instead of the developer's. By treating LLMs as "engines" rather than "untrusted inputs," we have effectively invited the attacker to sit at the keyboard of our internal logic.

### The "So What?": Why This Matters

The danger here isn't just a single data breach; it is the **systemic erosion of the Secure by Design philosophy.** For thirty years, we have fought to move security "left," to make it a foundational element of the build process. AI is dragging us back to the 1990s, where security was a "bolt-on" afterthought, managed by reactive filters and "vibes" rather than rigorous verification.

When we normalize deviance, we lower the barrier to entry for attackers to a subterranean level. An attacker no longer needs to find a buffer overflow or a complex race condition. They simply need to be better at "talking" to your software than your developers were. This breaks the **unified security model** because it introduces a layer of the stack that is inherently un-patchable. You cannot "patch" the fact that an LLM is designed to follow instructions. 

Furthermore, this creates what Charles Perrow called **"Normal Accidents."** In complex, tightly coupled systems—like an AI agent with access to your corporate Slack, Jira, and AWS console—failure is not a possibility; it is a mathematical certainty. The complexity of these AI integrations ensures that we cannot predict every failure mode. When we combine this complexity with the "normalization of deviance"—the habit of ignoring "small" prompt injection successes or "minor" hallucinations—we are building a Rube Goldberg machine of catastrophic risk. 

If your organization accepts a 5% "failure rate" in an AI-driven security filter, you haven't built a filter; you've built a **lottery for attackers.** The "So What" is simple: We are currently training a generation of developers to believe that "mostly secure" is "secure enough." In a world of automated, AI-driven exploitation, "mostly secure" is just a delayed funeral.

### Strategic Defense: What To Do About It

We must stop treating AI as a "special case" that deserves a pass on basic security hygiene. If an AI component cannot meet the same security rigors as a SQL database or an authentication module, it does not belong in production.

#### 1. Immediate Actions (Tactical Response)

*   **Implement "Hard" Circuit Breakers:** Do not rely on the LLM to "refuse" a malicious request. Implement a deterministic middleware layer (using RegEx, YARA rules, or high-confidence keyword blocking) that sits between the user and the LLM, and more importantly, between the LLM and your internal APIs. If the LLM output contains strings like `DROP TABLE`, `admin_token`, or `Set-Cookie`, the transaction is killed by the middleware, not the model.
*   **Enforce the "Least Privilege" Agent Model:** If you are using AI Agents (autonomous LLMs that can call functions), each agent must have its own unique, scoped IAM role. Never use a "service account" that has broad access. If the AI is supposed to summarize emails, its API key should have `Read` access to emails and *nothing else*. No access to the directory, no access to the calendar, no access to the "send" function.
*   **Mandatory Red-Teaming for "System Prompts":** Treat your system prompts as code, not documentation. They must undergo version control and rigorous red-teaming. Use automated tools to test your prompts against known injection libraries (like Garak or PyRIT). If a prompt can be subverted in a lab, it *will* be subverted in the wild.

#### 2. Long-Term Strategy (The Pivot)

*   **Architectural Decoupling (The "Sandbox" Pivot):** Move toward an architecture where the AI is treated as a "untrusted processor" in a strictly isolated sandbox. The AI should never have direct access to a data store. Instead, it should output a "request for data" which is then validated by a **deterministic "Validator" service** before being executed. This moves the "trust" back into code we can actually audit.
*   **Establish "Deviance Thresholds" and Kill-Switches:** Define exactly what an "unacceptable failure" looks like for your AI implementations. If the model’s "drift" (measured by hallucination rates or successful injection attempts in logs) exceeds a pre-defined threshold, the system must automatically fail-over to a non-AI, deterministic logic path or shut down. We must stop "tuning" our way out of fundamental security flaws; sometimes the only secure answer is to turn the model off.
*   **Adopt "Secure by Design" for AI Procurement:** Stop buying "AI-powered" tools that don't provide a detailed **AI Software Bill of Materials (AI-SBOM)**. You need to know what models are being used, what datasets they were trained on (to assess poisoning risk), and what specific guardrails are baked into the inference engine. If a vendor claims their AI is "inherently secure," they are either lying or incompetent. Demand proof of adversarial testing.

We are at a crossroads. We can continue to normalize the deviance, accepting the "small" failures of AI until they aggregate into a systemic collapse. Or, we can re-assert the principles of rigorous engineering: that complexity is the enemy of security, and that "probabilistic" is just another word for "unreliable." **The choice is yours, but the attackers have already made theirs.**

---

## Article 3: U.S. CISA adds Collabora Online flaw to its Known Exploited Vulnerabilities catalog

CISA has added a critical

<a href="https://securityaffairs.com/201652/security/u-s-cisa-adds-collabora-online-flaw-to-its-known-exploited-vulnerabilities-catalog.html">Read the full article</a>

### Technical Analysis: What's Really Happening

### The Mechanic: What's Actually Happening

When CISA adds a vulnerability to its Known Exploited Vulnerabilities (KEV) catalog, the time for academic debate is over. We are no longer talking about theoretical "proof of concepts" or researchers competing for bug bounties. We are talking about active exploitation—real-world adversaries using a specific hole to climb into the digital windows of organizations.

In this instance, the target is **CVE-2026-110447**, a critical flaw in the **Collabora Online – Built-in CODE Server** with a staggering **CVSS score of 9.2**. To understand why this is a nightmare for security architects, we have to look past the marketing of "sovereign office suites" and into the plumbing of how modern web-based document editing actually works.

Collabora Online is essentially a headless version of LibreOffice, wrapped in a web-service layer. The "Built-in CODE Server" (Collabora Online Development Edition) is the engine that handles the heavy lifting—rendering complex spreadsheets, parsing legacy `.doc` files, and managing real-time collaborative sessions via WebSockets. Because document parsing is notoriously difficult to do securely, Collabora relies on a multi-layered isolation strategy, typically using Linux namespaces and `chroot` jails to keep the document-processing "kits" away from the host system.

**CVE-2026-110447 represents a catastrophic failure in that isolation.** While the specific technical minutiae of the exploit are often kept close to the chest by CISA to prevent a "how-to" guide for script kiddies, the 9.2 score and the "Known Exploited" status tell us the story. We are likely looking at a **Remote Code Execution (RCE)** vulnerability triggered by a malformed document or a crafted WebSocket request. In many default installations, especially those integrated into platforms like Nextcloud or ownCloud, the CODE server runs with just enough privilege to make a breakout devastating. If an attacker can bypass the jail, they aren't just reading your spreadsheets; they are executing commands with the permissions of the service user, often providing a beachhead for lateral movement into the wider private cloud environment.

I’ve seen this pattern before. When a service tries to be "all-in-one" and "easy to deploy," it often creates a monolithic attack surface. The "Built-in" version of the CODE server is designed for convenience—it’s a single app image or a simple toggle in a web interface. That convenience is exactly what attackers are preying on. They know that the administrators who choose the "easy" deployment path are also the ones least likely to have hardened the underlying kernel or implemented strict egress filtering.

### The "So What?": Why This Matters

This isn't just another patch Tuesday headache. This vulnerability strikes at the heart of the **"Sovereign Cloud" movement**. For the last few years, we’ve seen a significant push from government agencies, legal firms, and privacy-conscious enterprises to move away from the "Big Tech" ecosystems of Microsoft 365 and Google Workspace. The goal was simple: regain control of data and eliminate third-party telemetry.

The irony is now laid bare. By moving to a self-hosted stack like Collabora to "increase security," many organizations have inadvertently traded a managed, highly-monitored risk for an unmanaged, "set-it-and-forget-it" risk. **CVE-2026-110447 proves that the "Privacy Paradox" is real.** You might have kept your data away from a tech giant's AI training model, but you’ve opened the door to any threat actor with a CISA KEV scraper and an automated exploit script.

The "So What" here is three-fold:

First, **the barrier to entry for attackers has collapsed.** Because Collabora is often integrated into popular file-sharing platforms, an attacker doesn't need to find your specific document server. They just need to find a Nextcloud instance—of which there are hundreds of thousands exposed to the internet—and check if the Collabora plugin is active. It’s a target-rich environment with a standardized attack vector.

Second, **this breaks the "Document Trust" model.** We have spent twenty years training users not to click on suspicious `.exe` files, but we’ve spent the last five years telling them that "opening a document in the browser is safe because it’s just a web preview." This vulnerability turns that logic on its head. Simply clicking a shared link to "review the quarterly budget" can now result in a full system compromise of the server hosting the files.

Third, **the CVSS 9.2 rating in the KEV catalog is a signal of "Mass Exploitation Potential."** When CISA moves this fast, it usually means they are seeing "spray and pray" activity from state-sponsored actors or sophisticated ransomware groups. These groups aren't just looking for one specific secret; they are looking to build a botnet of high-performance servers that they can use for further attacks, data exfiltration, or as a pivot point into internal corporate networks. If you are running this software, you are no longer a bystander; you are a target in an active campaign.

### Strategic Defense: What To Do About It

If you are running Collabora Online, specifically the Built-in CODE Server, you need to stop thinking about this as a "software update" and start thinking about it as an **incident response exercise**.

#### 1. Immediate Actions (Tactical Response)

*   **Emergency Patching & Version Verification:** Do not trust your auto-update settings. Manually verify that your Collabora Online and CODE server versions are beyond the affected range. If you are using the Nextcloud "Built-in CODE Server" app, update it via the command line (`occ app:update richdocumentscode`) to ensure the latest binaries are pulled.
*   **Egress Filtering (The "Kill Switch"):** The primary goal of an RCE exploit is to "call home" to a Command & Control (C2) server. Immediately restrict the CODE server’s ability to initiate outbound connections. It should talk to your file storage and your users—nothing else. Use `iptables`, `nftables`, or your cloud firewall to block all outbound traffic from the CODE server UID/container except to known, required internal endpoints.
*   **Log Hunting for `coolwsd` Anomalies:** Audit your logs for the `coolwsd` process (the Collabora Online WebSocket Daemon). Look for unexpected child processes. A document editor should not be spawning `/bin/sh`, `curl`, `wget`, or `nc`. If you see these in your process audit logs (via `auditd` or Sysmon for Linux), assume the box is compromised and initiate your breach protocol.

#### 2. Long-Term Strategy (The Pivot)

*   **De-couple the "Built-in" Architecture:** The "Built-in" CODE server is a convenience that has become a liability. For production environments, move to a **standalone, containerized Collabora instance** (using Docker or Podman) running on a separate, hardened VM. This adds a layer of network and filesystem isolation that the "Built-in" version lacks.
*   **Implement "Disposable" Processing:** Move toward an architecture where the document rendering kits are truly ephemeral. Use container orchestration (like Kubernetes) to set strict memory and CPU limits on the CODE pods and ensure they are recycled frequently. If an attacker gains a foothold in a "kit," they should find themselves in a resource-constrained environment that disappears within minutes.
*   **The "Zero Trust" Document Layer:** Stop treating your internal document server as a "trusted" zone. Even if it sits behind your VPN, it should be treated as an untrusted gateway. Implement **mTLS (Mutual TLS)** between your file storage (Nextcloud/ownCloud) and your Collabora server. This ensures that even if the CODE server is popped, the attacker cannot easily spoof requests to the file storage to scrape other users' data.
*   **Adopt a "Vulnerability-Centric" Patching Cadence:** Most organizations patch on a 30-day cycle. CISA’s KEV catalog demands a **24-to-48-hour cycle** for anything listed. You must have the automation in place to identify, test, and deploy fixes for KEV-listed items within hours, not weeks. If you can’t do that, you shouldn't be self-hosting critical infrastructure.

**Final Thought:** CVE-2026-110447 is a reminder that "self-hosting" is not a synonym for "security." It is a commitment to professional-grade systems administration. If you aren't prepared to defend the stack with the same intensity that the attackers are using to break it, it might be time to reconsider the managed services you were so eager to leave behind.

---

**Analyst Note:** These top 3 articles this week synthesize industry trends with expert assessment. For strategic decisions, conduct thorough validation with your security, compliance, and risk teams.