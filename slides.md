---
theme: default
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Avoiding Vendor Lock-In in AI Procurement for the DoW
  NAML 2026 — 10th Annual Workshop on Naval Applications of Machine Learning
  March 2–3, 2026 · San Diego, California
drawings:
  persist: false
transition: slide-left
title: Avoiding Vendor Lock-In in AI Procurement for the DoW
mdc: true
---

# Avoiding Vendor Lock-In in AI Procurement for the DoW

**Strategies for ML Platform Independence in Naval AI Systems**

Sam Bright · William Emeny · Alan Jaeger · Adam Larson · JP Lueck · Michael Soltys

GBL Systems Corp. · NSWC Port Hueneme Division

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<!--
Welcome everyone. We're here to talk about a problem that affects every naval organization procuring AI and ML systems: vendor lock-in. We'll cover why it's a critical risk, what the new policy mandates require, and — most importantly — give you five concrete things you can put into your next AI solicitation to protect against it.
-->

---
layout: center
---

# The Problem: Vendor Lock-In

<div class="text-3xl font-bold text-center text-red-600">
Switching costs become so high that you're trapped with a single vendor
</div>

<v-click>

<div class="mt-8 text-xl">

- Dependencies limit competition, innovation, and operational flexibility
- AI/ML systems create *deeper* lock-in than traditional IT
- Models can become inseparable from their training platforms

</div>

</v-click>

<v-click>

<div class="bg-blue-100 dark:bg-blue-900 p-4 rounded mt-6 text-center text-xl">

> *What begins as a useful tool can become an "iron cage" of constraint.* — Max Weber

</div>

</v-click>

<!--
Vendor lock-in occurs when the cost of switching away from a vendor becomes prohibitively high. This isn't new — but AI makes it worse. Unlike traditional software, ML models can become deeply entangled with their training platforms, creating dependencies that go beyond just APIs into the realm of intellectual property and algorithmic competence. Weber's "iron cage" metaphor is apt: the tools we adopt to increase capability can become the very constraints that limit us.
-->

---

# The $112 Million Lesson

## <span style="color: #6b21a8;">USDA Case Study (2021)</span>

<div class="grid grid-cols-2 gap-8 mt-4">

<div>

### <span style="color: #6b21a8;">What Happened</span>

Paid **$112 million more** for Microsoft Office than Google Workspace — specifically to avoid even *higher* switching costs.

Migrating would have required:
- Retraining thousands of employees
- Converting years of templates and workflows
- Rebuilding integrations with dozens of internal systems

</div>

<div>

### <span style="color: #6b21a8;">Why This Matters for Defense AI</span>

- This was <span style="background-color: #ffe4e1; padding: 2px 6px; border-radius: 3px;">commodity office software</span>
- Not mission-critical AI

For defense AI — classified data, mission-critical uptime, proprietary model weights, security requirements — switching barriers are **orders of magnitude** greater.

</div>

</div>

<v-click>

<div class="text-2xl font-bold text-center mt-6 text-red-600">
If commodity software costs $112M to escape, what does defense AI lock-in cost?
</div>

</v-click>

<!--
This is the number that makes the risk concrete. The USDA — a civilian agency dealing with commodity office software — found that switching would cost MORE than the $112 million premium they were already paying. Now imagine that in the context of naval AI systems with classified training data, real-time inference requirements for weapon systems, and FedRAMP security controls. The switching costs are orders of magnitude higher.
-->

---

# Four Types of AI Vendor Lock-In

<div class="grid grid-cols-2 gap-4 mt-6">

<div class="border-2 border-blue-500 p-4 rounded">

### <span style="color: #6b21a8;">Platform Lock-In</span>

Training, inference, and deployment tied to a specific cloud ecosystem (AWS Bedrock/SageMaker, Azure OpenAI, Google Vertex AI)

</div>

<div class="border-2 border-yellow-500 p-4 rounded">

### <span style="color: #6b21a8;">Data Lock-In</span>

Training datasets and preprocessing pipelines optimized for vendor-specific formats and storage systems

</div>

<div class="border-2 border-green-500 p-4 rounded">

### <span style="color: #6b21a8;">Model Lock-In</span>

Models dependent on proprietary frameworks, custom accelerators, or vendor-specific optimization libraries

</div>

<div class="border-2 border-red-500 p-4 rounded">

### <span style="color: #6b21a8;">Expertise Lock-In</span>

Teams specialized in vendor-specific tools and APIs; organizational inertia reinforces the relationship

</div>

</div>

<v-click>

<div class="bg-blue-100 dark:bg-blue-900 p-4 rounded mt-4 text-center text-xl font-bold">
These four types compound each other — together, they create a trap
</div>

</v-click>

<!--
Lock-in manifests in four distinct ways, and they compound each other. Platform lock-in is the most visible — you're on AWS or Azure and your whole pipeline depends on their services. But data lock-in is often more insidious — your training data is structured around vendor-specific storage. Model lock-in means your trained models can't easily move. And expertise lock-in means your people only know how to work with one vendor's tools. Each of these alone creates friction; together, they create a trap.
-->

---

# Defense-Specific Risks

## <span style="color: #6b21a8;">Why the DoW Is Uniquely Vulnerable</span>

<v-clicks>

- **Classification constraints** limit ability to evaluate alternatives
- **Clearance requirements** restrict the vendor pool
- **Mission-critical reliability** makes organizations risk-averse to platform changes
- **Long procurement cycles** (2–5 years) lock in choices made years earlier
- **Trust inertia** — users develop confidence in a model's specific behaviors and "quirks" that doesn't transfer to new systems

</v-clicks>

<v-click>

<div class="bg-blue-100 dark:bg-blue-900 p-4 rounded mt-4">

**DoW Open Source Software memo (Jan 2022):** Lock-in can occur *even with open source* through expertise dependencies and specialized implementations.

</div>

</v-click>

<v-click>

<div class="text-xl font-bold text-center mt-4 text-green-600">
Good news: CDAO has already proven vendor-agnostic approaches work at DoW scale
</div>

</v-click>

<!--
The defense environment makes all four types of lock-in worse. You can't easily evaluate alternatives when your data is classified. Only cleared vendors can compete, which shrinks the market. And when AI systems drive combat decisions, nobody wants to risk platform changes that could introduce instability. There's also a human factor — people develop trust in the specific behaviors and quirks of a model. That trust doesn't transfer easily. Even the DoW's own open source memo acknowledges that vendor lock-in can happen even with open-source software.
-->

---

# Policy Mandate: Hegseth Acquisition Reforms

## <span style="color: #6b21a8;">November 7, 2025 — Secretary Hegseth, National War College</span>

<div class="grid grid-cols-2 gap-8 mt-4">

<div>

### <span style="color: #6b21a8;">Four Core Contractor Requirements</span>

<v-clicks>

1. Accept risk and invest in capacity
2. Embrace commercial "85% solutions"
3. **Supply chain resilience** ← <span style="background-color: #ffe4e1; padding: 2px 6px; border-radius: 3px;">DUAL-SOURCE MANDATE</span>
4. Performance-based contracting

</v-clicks>

</div>

<div>

### <span style="color: #6b21a8;">Structural Changes</span>

<v-clicks>

- Portfolio Acquisition Executives (PAEs) replace Program Executive Offices
- Compensation tied to delivery speed and competition
- "Speed to delivery" as organizing principle
- Lock-in avoidance: *best practice* → **mandatory policy**

</v-clicks>

</div>

</div>

<v-click>

<div class="text-2xl font-bold text-center mt-6 text-red-600">
"Maintain at least two qualified sources for critical program content"
</div>

</v-click>

<!--
This is a game-changer. In November 2025, Secretary Hegseth made vendor lock-in avoidance a mandatory structural requirement — not just a nice-to-have. The key is requirement number three: maintain at least two qualified sources for critical program content, specifically to prevent vendor lock-in. The new PAE structure ties executive compensation to competition and speed, creating institutional incentives for vendor independence. This means the strategies we're about to discuss aren't optional — they're what the policy now demands.
-->

---

# Technical Strategies for Platform Independence

<div class="grid grid-cols-3 gap-4 mt-6">

<div class="border-2 border-blue-500 p-4 rounded">

### <span style="color: #6b21a8;">Containerization</span>

- Docker + Kubernetes
- Portable ML environments
- Kubeflow for vendor-neutral workflows
- Standardized GPU management

</div>

<div class="border-2 border-yellow-500 p-4 rounded">

### <span style="color: #6b21a8;">Open Standards</span>

- **ONNX** — universal model format (1,700+ tools)
- **MLflow** — experiment tracking (800+ contributors)
- **Apache Iceberg** — vendor-neutral data lakes

</div>

<div class="border-2 border-green-500 p-4 rounded">

### <span style="color: #6b21a8;">Infrastructure-as-Code</span>

- **Terraform** — deploy to AWS, Azure, GCP, or on-prem
- **JWCC** — multi-vendor cloud within DoW
- **REST + OpenAPI** — swap backends freely

</div>

</div>

<v-click>

<div class="bg-blue-100 dark:bg-blue-900 p-4 rounded mt-6 text-center text-xl font-bold">
These are mature, production-ready technologies — not research projects
</div>

</v-click>

<!--
Here are the technical building blocks. Containerization through Docker and Kubernetes gives you portable ML environments — train on one platform, deploy on another. ONNX provides a universal model format so your trained models aren't locked to PyTorch or TensorFlow. MLflow handles experiment tracking without vendor tie-in. Apache Iceberg gives you data lakes that work with multiple analytics engines. Terraform lets you define your infrastructure once and deploy it anywhere. And standard REST APIs with OpenAPI specs let you swap out backends. None of these are exotic — they're mature, production-ready technologies.
-->

---

# Procurement Strategies

## <span style="color: #6b21a8;">Contracts Must Enable Technical Independence</span>

<div class="grid grid-cols-3 gap-4 mt-6">

<div class="border-2 border-blue-500 p-4 rounded">

### <span style="color: #6b21a8;">Modular Contracting</span>

- Break AI projects into interoperable increments
- Multiple vendors compete for each module
- Supported by DoW Software Acquisition Pathway

</div>

<div class="border-2 border-yellow-500 p-4 rounded">

### <span style="color: #6b21a8;">Government Data Rights</span>

- Retain unlimited rights to: training data, model weights, source code
- Require SBOM
- Distinguish background IP from foreground IP

</div>

<div class="border-2 border-green-500 p-4 rounded">

### <span style="color: #6b21a8;">Performance-Based</span>

- Define success by accuracy, availability, effectiveness
- Include portability in SLAs
- Reward vendor-independent implementations

</div>

</div>

<v-click>

<div class="text-xl font-bold text-center mt-6 text-green-600">
Technical strategies only work if contracts support them
</div>

</v-click>

<!--
The technical strategies only work if your contracts support them. Modular contracting breaks big AI projects into pieces — so you're not locked into one vendor for the whole thing. Data rights are critical — you MUST retain unlimited rights to training data, model weights, and source code developed under the contract. And performance-based contracting focuses on outcomes — accuracy and availability — not on which vendor's platform you use. This preserves your ability to compete follow-on work.
-->

---
layout: center
---

# Five Things to Require in Your Next AI Solicitation

<div class="text-3xl font-bold text-center text-blue-600 mt-8">
The actionable takeaway
</div>

<!--
This is the slide I want you to remember. If you take nothing else away from this talk, put these five requirements into your next AI solicitation.
-->

---

# The Checklist

<v-clicks>

<div class="border-2 border-blue-500 p-3 rounded mb-3">

**1. Containerized Delivery** — Require all AI/ML models delivered as Docker containers deployable on any Kubernetes cluster, not tied to a specific cloud runtime.

</div>

<div class="border-2 border-yellow-500 p-3 rounded mb-3">

**2. Open Model Formats** — Require model exports in ONNX or equivalent open standards, so trained models can run on alternative inference engines without vendor involvement.

</div>

<div class="border-2 border-green-500 p-3 rounded mb-3">

**3. Government Data Rights** — Explicitly retain unlimited rights to all training data, model weights, training parameters, and source code developed under the contract.

</div>

<div class="border-2 border-purple-500 p-3 rounded mb-3">

**4. Infrastructure-as-Code** — Require infrastructure definitions in Terraform or equivalent, so the deployment environment can be reproduced on a different provider.

</div>

<div class="border-2 border-red-500 p-3 rounded mb-3">

**5. Demonstrated Portability** — Require vendors to demonstrate their solution deploys and passes acceptance tests on at least two different cloud environments before final acceptance.

</div>

</v-clicks>

<!--
Number one: containerized delivery. Docker containers on Kubernetes, not tied to one cloud. Number two: open model formats — ONNX or equivalent so you can move models between inference engines. Number three: government data rights — you own the training data, model weights, and source code. Number four: infrastructure-as-code — Terraform or equivalent so you can reproduce the environment anywhere. And number five: demonstrated portability — make the vendor prove it works on at least two different environments before you accept delivery. These five requirements are concrete, enforceable, and directly enable compliance with the new dual-source mandates.
-->

---

# Lessons from DoW Programs

## <span style="color: #6b21a8;">Vendor Independence Works at Operational Scale</span>

<div class="grid grid-cols-3 gap-4 mt-6">

<div class="border-2 border-blue-500 p-4 rounded">

### <span style="color: #6b21a8;">CDAO GIDE</span>

- Vendor-agnostic data integration across **50+ sources**
- Availability **>99.5%** across multiple vendor environments
- Tactical decision-making latencies met

</div>

<div class="border-2 border-yellow-500 p-4 rounded">

### <span style="color: #6b21a8;">Army Enterprise Cloud</span>

- Multi-cloud across AWS, Azure, and Google Cloud
- Cloud-agnostic management layers
- Improved resilience and cost optimization

</div>

<div class="border-2 border-green-500 p-4 rounded">

### <span style="color: #6b21a8;">Navy AI Modernization</span>

- **"Buy operational outcomes, not AI"**
- Performance-based contracts with portability
- Robust follow-on competition maintained

</div>

</div>

<v-click>

<div class="text-xl font-bold text-center mt-6 text-green-600">
These implementations validate that dual-source requirements are technically feasible and operationally advantageous
</div>

</v-click>

<!--
These aren't hypothetical strategies — they're working in production today. The CDAO's GIDE program integrates data from over 50 sources using vendor-agnostic layers, achieving 99.5% availability. The Army runs a true multi-cloud strategy across all three major providers. And the Navy's approach of buying outcomes rather than platforms has kept follow-on competition robust. These programs prove that vendor independence doesn't compromise mission effectiveness — it enhances it.
-->

---
layout: end
class: text-center
---

# Closing

<div class="grid grid-cols-3 gap-4 mt-8">

<div class="border-2 border-blue-500 p-4 rounded">

### <span style="color: #6b21a8;">The Risk</span>
$112M+ switching costs
Four compounding lock-in types
Defense amplifies every barrier

</div>

<div class="border-2 border-yellow-500 p-4 rounded">

### <span style="color: #6b21a8;">The Mandate</span>
Hegseth dual-source policy
PAEs incentivized for competition
No longer optional

</div>

<div class="border-2 border-green-500 p-4 rounded">

### <span style="color: #6b21a8;">The Solution</span>
Five checklist items
Proven at DoW scale
Mature technologies

</div>

</div>

<div class="mt-10 text-2xl font-bold">
Vendor independence is achievable — and now mandatory
</div>

<div class="mt-6 text-lg">
The question isn't whether to pursue vendor independence — it's how fast you can get there.
</div>

<div class="mt-8 text-xl">
<strong>GBL Systems Corp. · NSWC Port Hueneme Division</strong>
</div>

<!--
To wrap up: vendor independence in AI procurement is both technically achievable and now mandated by policy. The tools are mature — containerization, ONNX, Terraform, open data formats. The policy is clear — dual-source requirements, PAEs with competition incentives. And the DoW programs we showed demonstrate it works at operational scale. Remember the five things for your next solicitation. We're happy to take questions.
-->
