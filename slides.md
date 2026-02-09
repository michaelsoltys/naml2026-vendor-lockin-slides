---
theme: seriph
title: Avoiding Vendor Lock-In in AI Procurement for the DoW
info: |
  NAML 2026 — 10th Annual Workshop on Naval Applications of Machine Learning
  March 2–3, 2026 · San Diego, California
author: Sam Bright, William Emeny, Alan Jaeger, Adam Larson, JP Lueck, Michael Soltys
keywords: vendor lock-in, AI procurement, machine learning, platform independence
class: text-center
transition: slide-left
mdc: true
---

# Avoiding Vendor Lock-In in AI Procurement for the DoW

Sam Bright · William Emeny · Alan Jaeger · Adam Larson · JP Lueck · Michael Soltys

GBL Systems Corp. · NSWC Port Hueneme Division

<div class="abs-b mb-8 text-sm opacity-60">
NAML 2026 · 10th Annual Workshop on Naval Applications of Machine Learning
</div>

<!--
Welcome everyone. We're here to talk about a problem that affects every naval organization procuring AI and ML systems: vendor lock-in. We'll cover why it's a critical risk, what the new policy mandates require, and — most importantly — give you five concrete things you can put into your next AI solicitation to protect against it.
-->

---
layout: default
---

# The Problem: Vendor Lock-In

<v-clicks>

- **Definition:** Switching costs become so high that you're trapped with a single vendor
- Dependencies limit competition, innovation, and operational flexibility
- AI/ML systems create *deeper* lock-in than traditional IT
  - Proprietary APIs, custom model formats, specialized training environments
  - Models can become inseparable from their training platforms

</v-clicks>

<br>

<v-click>

> *What begins as a useful tool can become an "iron cage" of constraint.*
> — Max Weber

</v-click>

<!--
Vendor lock-in occurs when the cost of switching away from a vendor becomes prohibitively high. This isn't new — but AI makes it worse. Unlike traditional software, ML models can become deeply entangled with their training platforms, creating dependencies that go beyond just APIs into the realm of intellectual property and algorithmic competence. Weber's "iron cage" metaphor is apt: the tools we adopt to increase capability can become the very constraints that limit us.
-->

---
layout: default
---

# The $112 Million Lesson

<div class="mt-8">

**USDA (2021):** Paid **$112 million more** for Microsoft Office than Google Workspace — specifically to avoid even *higher* switching costs.

</div>

<v-clicks>

- Migrating would have required:
  - Retraining thousands of employees
  - Converting years of templates and workflows
  - Rebuilding integrations with dozens of internal systems
- **This was commodity office software** — not mission-critical AI

</v-clicks>

<v-click>
<div class="mt-4 p-4 bg-red-500/10 rounded-lg border border-red-500/20">

**For defense AI** — where classified data, mission-critical uptime, proprietary model weights, and security requirements amplify barriers by orders of magnitude — the implications are far greater.

</div>
</v-click>

<!--
This is the number that makes the risk concrete. The USDA — a civilian agency dealing with commodity office software — found that switching would cost MORE than the $112 million premium they were already paying. Now imagine that in the context of naval AI systems with classified training data, real-time inference requirements for weapon systems, and FedRAMP security controls. The switching costs are orders of magnitude higher.
-->

---
layout: default
---

# Four Types of AI Vendor Lock-In

<v-clicks>

- **Platform lock-in** — Training, inference, and deployment tied to a specific cloud ecosystem (AWS Bedrock/SageMaker, Azure OpenAI, Google Vertex AI)

- **Data lock-in** — Training datasets and preprocessing pipelines optimized for vendor-specific formats and storage systems

- **Model lock-in** — Models dependent on proprietary frameworks, custom accelerators, or vendor-specific optimization libraries

- **Expertise lock-in** — Teams specialized in vendor-specific tools and APIs; organizational inertia reinforces the relationship

</v-clicks>

<!--
Lock-in manifests in four distinct ways, and they compound each other. Platform lock-in is the most visible — you're on AWS or Azure and your whole pipeline depends on their services. But data lock-in is often more insidious — your training data is structured around vendor-specific storage. Model lock-in means your trained models can't easily move. And expertise lock-in means your people only know how to work with one vendor's tools. Each of these alone creates friction; together, they create a trap.
-->

---
layout: default
---

# Defense-Specific Risks

<v-clicks>

- **Classification constraints** limit ability to evaluate alternatives
- **Clearance requirements** restrict the vendor pool
- **Mission-critical reliability** makes organizations risk-averse to platform changes
- **Long procurement cycles** (2–5 years) lock in choices made years earlier
- **Trust inertia** — users develop confidence in a model's specific behaviors and "quirks" that doesn't transfer to new systems

</v-clicks>

<v-click>
<div class="mt-4 p-4 bg-blue-500/10 rounded-lg border border-blue-500/20">

DoW Open Source Software memo (Jan 2022): Lock-in can occur *even with open source* through expertise dependencies and specialized implementations.

</div>
</v-click>

<!--
The defense environment makes all four types of lock-in worse. You can't easily evaluate alternatives when your data is classified. Only cleared vendors can compete, which shrinks the market. And when AI systems drive combat decisions, nobody wants to risk platform changes that could introduce instability. There's also a human factor — people develop trust in the specific behaviors and quirks of a model. That trust doesn't transfer easily. Even the DoW's own open source memo acknowledges that vendor lock-in can happen even with open-source software.
-->

---
layout: default
---

# Policy Mandate: Hegseth Acquisition Reforms

**November 7, 2025** — Secretary Hegseth, National War College

<v-clicks>

- Vendor lock-in avoidance elevated from *best practice* to **mandatory policy**
- Four core contractor requirements:
  1. Accept risk and invest in capacity
  2. Embrace commercial "85% solutions"
  3. **Supply chain resilience — maintain at least two qualified sources**
  4. Performance-based contracting with rewards and penalties
- Portfolio Acquisition Executives (PAEs) replace Program Executive Offices
  - Compensation tied to delivery speed and competition
- "Speed to delivery" as organizing principle

</v-clicks>

<!--
This is a game-changer. In November 2025, Secretary Hegseth made vendor lock-in avoidance a mandatory structural requirement — not just a nice-to-have. The key is requirement number three: maintain at least two qualified sources for critical program content, specifically to prevent vendor lock-in. The new PAE structure ties executive compensation to competition and speed, creating institutional incentives for vendor independence. This means the strategies we're about to discuss aren't optional — they're what the policy now demands.
-->

---
layout: two-cols
---

# Technical Strategies

**Containerization & Orchestration**
- Docker + Kubernetes = portable ML environments
- Models trained on one platform deploy to another
- Kubeflow for vendor-neutral ML workflows
- Standardized GPU management via device plugins

<br>

**Open Model Standards**
- ONNX — universal model format (1,700+ tools)
- Convert between PyTorch, TensorFlow, etc.
- MLflow — vendor-neutral experiment tracking (800+ contributors)

::right::

<div class="ml-4">

**Open Data Formats**
- Apache Iceberg — vendor-neutral data lakes
- Schema evolution, ACID transactions
- Separates storage from compute

<br>

**Infrastructure-as-Code**
- Terraform — same config deploys to AWS, Azure, GCP, or on-prem
- Version-controlled, auditable, reproducible
- JWCC enables multi-vendor cloud within DoW

<br>

**API Standards**
- REST + OpenAPI specifications
- OAuth2/OIDC authentication
- Swap backends without changing client code

</div>

<!--
Here are the technical building blocks. Containerization through Docker and Kubernetes gives you portable ML environments — train on one platform, deploy on another. ONNX provides a universal model format so your trained models aren't locked to PyTorch or TensorFlow. MLflow handles experiment tracking without vendor tie-in. Apache Iceberg gives you data lakes that work with multiple analytics engines. Terraform lets you define your infrastructure once and deploy it anywhere. And standard REST APIs with OpenAPI specs let you swap out backends. None of these are exotic — they're mature, production-ready technologies.
-->

---
layout: default
---

# Procurement Strategies

<v-clicks>

### Modular Contracting
- Break AI projects into interoperable increments
- Multiple vendors can compete for each module
- Supported by DoW Software Acquisition Pathway

### Government Data Rights
- Retain unlimited rights to: training data, model weights, training parameters, source code
- Distinguish background IP (vendor keeps) from foreground IP (government owns)
- Require Software Bill of Materials (SBOM)

### Performance-Based Contracting
- Define success by accuracy, availability, and operational effectiveness
- **Not** by vendor-specific features
- Include portability requirements in SLAs
- Reward vendor-independent implementations

</v-clicks>

<!--
The technical strategies only work if your contracts support them. Modular contracting breaks big AI projects into pieces — so you're not locked into one vendor for the whole thing. Data rights are critical — you MUST retain unlimited rights to training data, model weights, and source code developed under the contract. And performance-based contracting focuses on outcomes — accuracy and availability — not on which vendor's platform you use. This preserves your ability to compete follow-on work.
-->

---
layout: center
class: text-center
---

# Five Things to Require in Your Next AI Solicitation

<!--
This is the slide I want you to remember. If you take nothing else away from this talk, put these five requirements into your next AI solicitation.
-->

---
layout: default
---

# The Checklist

<v-clicks>

1. **Containerized Delivery**
   Require all AI/ML models delivered as Docker containers deployable on any Kubernetes cluster — not tied to a specific cloud runtime.

2. **Open Model Formats**
   Require model exports in ONNX or equivalent open standards, so trained models can run on alternative inference engines without vendor involvement.

3. **Government Data Rights**
   Explicitly retain unlimited rights to all training data, model weights, training parameters, and source code developed under the contract.

4. **Infrastructure-as-Code**
   Require infrastructure definitions in Terraform or equivalent, so the deployment environment can be reproduced on a different provider.

5. **Demonstrated Portability**
   Require vendors to demonstrate their solution deploys and passes acceptance tests on at least two different cloud environments before final acceptance.

</v-clicks>

<!--
Number one: containerized delivery. Docker containers on Kubernetes, not tied to one cloud. Number two: open model formats — ONNX or equivalent so you can move models between inference engines. Number three: government data rights — you own the training data, model weights, and source code. Number four: infrastructure-as-code — Terraform or equivalent so you can reproduce the environment anywhere. And number five: demonstrated portability — make the vendor prove it works on at least two different environments before you accept delivery. These five requirements are concrete, enforceable, and directly enable compliance with the new dual-source mandates.
-->

---
layout: default
---

# Lessons from DoW Programs

<v-clicks>

### CDAO — Global Information Dominance Experiments (GIDE)
- Vendor-agnostic data integration across **50+ sources**
- System availability **>99.5%** across multiple vendor environments
- Processing latencies within tactical decision-making bounds

### Army Enterprise Cloud
- Multi-cloud strategy across AWS, Azure, and Google Cloud
- Cloud-agnostic management layers and standardized security
- Improved resilience, cost optimization, and innovation access

### Navy AI Modernization
- Philosophy: **"Buy operational outcomes, not AI"**
- Performance-based contracts with portability requirements
- Robust competition for follow-on contracts maintained

</v-clicks>

<!--
These aren't hypothetical strategies — they're working in production today. The CDAO's GIDE program integrates data from over 50 sources using vendor-agnostic layers, achieving 99.5% availability. The Army runs a true multi-cloud strategy across all three major providers. And the Navy's approach of buying outcomes rather than platforms has kept follow-on competition robust. These programs prove that vendor independence doesn't compromise mission effectiveness — it enhances it.
-->

---
layout: center
---

# Vendor independence is achievable — and now mandatory.

<div class="mt-8 text-lg">

Technical solutions exist. Policy now demands them.

**The question isn't whether to pursue vendor independence — it's how fast you can get there.**

</div>

<div class="mt-12 text-sm opacity-70">

Sam Bright · William Emeny · Alan Jaeger · Adam Larson · JP Lueck · Michael Soltys

GBL Systems Corp. · NSWC Port Hueneme Division

</div>

<!--
To wrap up: vendor independence in AI procurement is both technically achievable and now mandated by policy. The tools are mature — containerization, ONNX, Terraform, open data formats. The policy is clear — dual-source requirements, PAEs with competition incentives. And the DoW programs we showed demonstrate it works at operational scale. Remember the five things for your next solicitation. We're happy to take questions.
-->
