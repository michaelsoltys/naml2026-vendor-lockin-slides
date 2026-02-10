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

<!--
William opens. Welcome everyone. We're William Emeny and Michael Soltys, and we're here to talk about a problem that affects every naval organization procuring AI and ML systems: vendor lock-in. William will frame the problem — what vendor lock-in is, how it has evolved, and why today's AI systems make it worse. Then Michael will present solutions — policy, technical strategies, and five concrete things you can put into your next solicitation.
-->

---

# What is Vendor Lock-In?

<div class="grid grid-cols-2 gap-8 mt-4">

<div>

### <span style="color: #6b21a8;">Defining the Problem</span>

<v-clicks>

- Switching costs become so high that an organization is effectively **trapped** with a single provider
- We define it across **four dimensions**: platform, data, model, and expertise dependencies

</v-clicks>

</div>

<div>

### <span style="color: #6b21a8;">Impact on the DoW</span>

<v-clicks>

- **Technological sovereignty** — losing control of critical AI capabilities
- **Competition** — sole-source lets vendors increase prices
- **Operational flexibility** — inability to adapt as threats evolve
- **Innovation access** — locked out of better solutions

</v-clicks>

</div>

</div>

<v-click>

<div class="text-2xl italic text-left mt-6" style="color: #2E7D32; border-left: 4px solid #2E7D32; padding-left: 16px;">
"What begins as a useful tool can become an iron cage of constraint." — Max Weber
</div>

</v-click>

<div class="abs-br m-6 text-sm opacity-50 font-bold">WE</div>

<!--
Let me start by defining what we mean by vendor lock-in in the context of our paper. At its core, it's about switching costs becoming so high that you're effectively trapped. For defense AI, the stakes are uniquely high — we're talking about technological sovereignty, competition for taxpayer dollars, and the ability to adapt our systems as threats change. Weber's iron cage metaphor captures it well: the tools we adopt for capability can become the constraints that limit us.
-->

---

# The $112 Million Lesson - USDA Case Study (2021)

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

- This was commodity office software
- Not <span style="background-color: #ffe4e1; padding: 2px 6px; border-radius: 3px;">mission-critical AI</span>

For defense AI — classified data, mission-critical uptime, proprietary model weights, security requirements — switching barriers are **orders of magnitude** greater.

</div>

</div>

<v-click>

<div class="text-2xl italic text-left mt-6" style="color: #2E7D32; border-left: 4px solid #2E7D32; padding-left: 16px;">
If commodity software costs $112M to escape, what does defense AI lock-in cost?
</div>

</v-click>

<div class="abs-br m-6 text-sm opacity-50 font-bold">WE</div>

<!--
This is the case study that makes the risk concrete. The USDA — a civilian agency dealing with commodity office software — found that switching would cost MORE than the $112 million premium they were already paying. Retraining, converting workflows, rebuilding integrations. And that's just email and documents. Now imagine defense AI systems with classified training data, real-time inference for weapon systems, and FedRAMP security controls. The switching costs are orders of magnitude higher.
-->

---

# Historical Context: Lock-In Through the Decades

How Has Lock-In Presented Itself in Past Architectures?

<v-clicks>

- <strong style="color: #6b21a8;">1960s–80s: Mainframe era</strong> — IBM's proprietary hardware and software created total dependency; migrating off a mainframe meant rebuilding everything from scratch

- <strong style="color: #6b21a8;">1990s: Client-server</strong> — Microsoft and Oracle established dominance through proprietary protocols, file formats, and database engines that resisted interoperability

- <strong style="color: #6b21a8;">2000s: Enterprise software</strong> — ERP and CRM vendors (SAP, Salesforce) created lock-in through deeply customized implementations and proprietary data models

- <strong style="color: #6b21a8;">2010s: Cloud computing</strong> — Lock-in came not from generic services (Linux VMs, object storage) but from *managed services* like AWS Lambda and Azure Functions — convenient, but dangerous to build around

</v-clicks>

<v-click>

<div class="text-2xl italic text-left mt-4" style="color: #2E7D32; border-left: 4px solid #2E7D32; padding-left: 16px;">
Each technology wave created new opportunities for vendors to establish proprietary dominance
</div>

</v-click>

<div class="abs-br m-6 text-sm opacity-50 font-bold">WE</div>

<!--
Vendor lock-in isn't new — it has been a recurring pattern across every major technology transition. In the mainframe era, you were locked to IBM's hardware and software. Client-server brought Microsoft and Oracle dominance through proprietary protocols. Enterprise software like SAP created lock-in through deep customization. Cloud computing repeated the pattern with proprietary APIs. Each wave, vendors found new ways to make switching prohibitively expensive. The question is: what makes the current AI wave different?
-->

---

# What Does Lock-In Look Like Today?

Key Vulnerabilities in Modern AI Architectures

<div class="grid grid-cols-2 gap-6 mt-4">

<div>

### <span style="color: #6b21a8;">Deeper Than Before</span>

<v-clicks>

- AI creates dependencies beyond software interfaces — into **intellectual property and algorithmic competence**
- Models trained on proprietary platforms can become **inseparable** from their training environments
- Vendor-specific optimization means performance degrades on migration

</v-clicks>

</div>

<div>

### <span style="color: #6b21a8;">The Cloud AI Ecosystem Trap</span>

<v-clicks>

- **AWS**: Bedrock, SageMaker, Rekognition
- **Azure**: OpenAI Service, Azure ML, Cognitive Services
- **Google**: Vertex AI, AutoML, specialized NLP APIs
- Each integrates seamlessly *within* its ecosystem while creating friction for cross-platform migration

</v-clicks>

</div>

</div>

<v-click>

<div class="bg-blue-100 dark:bg-blue-900 p-4 rounded mt-4 text-center text-xl">
Unlike previous waves, AI lock-in extends into models themselves — not just infrastructure
</div>

</v-click>

<div class="abs-br m-6 text-sm opacity-50 font-bold">WE</div>

<!--
What makes AI lock-in fundamentally different from previous technology waves? It's deeper. Previous lock-in was about interfaces, APIs, file formats. AI lock-in goes into the models themselves — into intellectual property and algorithmic competence. A model trained on a proprietary platform may literally not work the same way when you move it. And every major cloud provider has built comprehensive AI ecosystems designed to work beautifully together — but only within their own platform. Moving between them creates enormous friction.
-->

---

# Four Types of AI Vendor Lock-In

<div class="grid grid-cols-2 gap-4 mt-6">

<div class="border-2 border-blue-500 p-4 rounded">

### <span style="color: #6b21a8;">Platform Lock-In</span>

Training, inference, and deployment tied to a specific cloud ecosystem (Azure OpenAI, AWS Bedrock/SageMaker, Google Vertex AI)

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

<div class="bg-blue-100 dark:bg-blue-900 p-4 rounded mt-4 text-center text-xl">
These four types compound each other — together, they create lock-in
</div>

</v-click>

<div class="abs-br m-6 text-sm opacity-50 font-bold">WE</div>

<!--
In our paper we identify four distinct types of AI vendor lock-in, and they compound each other. Platform lock-in is the most visible — your whole pipeline depends on one cloud. Data lock-in is often more insidious — your training data is structured around vendor-specific storage. Model lock-in means your trained models can't easily move. And expertise lock-in means your people only know one vendor's tools. Each alone creates friction; together, they create a trap. I'll now hand it over to Michael to discuss the solutions.
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

<div class="abs-br m-6 text-sm opacity-50 font-bold">WE</div>

<!--
The defense environment makes all four types of lock-in worse. Classification limits your ability to evaluate alternatives. Clearances shrink the vendor pool. Mission-critical reliability makes everyone risk-averse. And long procurement cycles mean decisions made years ago still constrain you today. Even the DoW's own open source memo acknowledges that lock-in can happen with open-source software.

But there is good news. The Chief Digital and AI Office proved this is solvable with their Global Information Dominance Experiments — GIDE. CDAO built vendor-agnostic data integration layers that work across all operational systems regardless of platform, pulling from over 50 different data sources through standardized interfaces. Their architecture uses open standard APIs for data ingestion, containerized processing pipelines that run across different cloud providers, and open output formats consumable by multiple tools. The results: 99.5% availability across multiple vendor environments, processing latencies within tactical decision-making bounds, and improved cost efficiency through competitive sourcing. GIDE proves that vendor independence does not mean compromising operational effectiveness.

And with that, I'll hand it over to Michael to discuss the policy mandates and technical solutions.
-->

---

# Policy Mandate: Sec Hegseth Acquisition Reforms

November 7, 2025 — Secretary Hegseth, National War College

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

<div class="text-2xl italic text-left mt-6" style="color: #2E7D32; border-left: 4px solid #2E7D32; padding-left: 16px;">
"Maintain at least two qualified sources for critical program content" — Secretary Hegseth
</div>

</v-click>

<div class="abs-br m-6 text-sm opacity-50 font-bold">MS</div>

<!--
Thanks William. So now that we understand the problem, what's being done about it? In November 2025, Secretary Hegseth made vendor lock-in avoidance a mandatory structural requirement — not just a nice-to-have. The key is requirement number three: maintain at least two qualified sources for critical program content. The new PAE structure ties executive compensation to competition and speed. This means the strategies I'm about to discuss aren't optional — they're what the policy now demands.
-->

---

# Technical Strategies for Platform Independence

<div class="grid grid-cols-3 gap-4 mt-6">

<div class="border-2 border-blue-500 p-4 rounded">

### <span style="color: #6b21a8;">Containerization</span>

- OCI-compliant containers + Kubernetes
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

<div class="bg-blue-100 dark:bg-blue-900 p-4 rounded mt-6 text-center text-xl">
These are mature, production-ready technologies — not research projects
</div>

</v-click>

<div class="abs-br m-6 text-sm opacity-50 font-bold">MS</div>

<!--
Here are the technical building blocks. OCI-compliant containers — whether you use Docker, Podman, or containerd — running on Kubernetes give you portable ML environments. Train on one platform, deploy on another. ONNX provides a universal model format so your trained models aren't locked to PyTorch or TensorFlow. MLflow handles experiment tracking without vendor tie-in. Apache Iceberg gives you vendor-neutral data lakes. Terraform lets you define your infrastructure once and deploy it anywhere. These aren't exotic — they're mature, production-ready technologies.

ANTICIPATED Q&A — "If AI coding assistants can refactor an entire AWS stack to Azure in a day, why bother with Terraform?"
Great question. Three reasons. First, AI-assisted refactoring still needs a well-structured starting point — Terraform and IaC give you that declarative, diffable, reviewable structure that an AI tool can reason about. A tangled mess of CloudFormation scripts is harder for a human or an AI to migrate. Second, AI assistants reduce the cost of switching but don't eliminate the need to plan for it — you still need portable data formats, model export rights, and contractual exit provisions that no amount of code refactoring can solve. Third, and most importantly, AI coding tools actually strengthen the case for open standards: Terraform, ONNX, and containerization give AI assistants a common vocabulary to translate between platforms. The combination of open standards plus AI-assisted migration is more powerful than either alone.
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

<div class="abs-br m-6 text-sm opacity-50 font-bold">MS</div>

<!--
The technical strategies only work if your contracts support them. Modular contracting breaks big AI projects into pieces — so you're not locked into one vendor for the whole thing. Data rights are critical — you MUST retain unlimited rights to training data, model weights, and source code. And performance-based contracting focuses on outcomes — accuracy and availability — not on which vendor's platform you use.
-->

---

# Five Things to Require in Your Next AI Solicitation

<!--
This is the slide I want you to remember. If you take nothing else away from this talk, put these five requirements into your next AI solicitation.
-->

<v-clicks>

<div class="border-l-4 border-blue-500 pl-3 py-1 mb-2">
<strong>1. Containerized Delivery</strong> — OCI-compliant containers on any Kubernetes cluster, not tied to one cloud
</div>

<div class="border-l-4 border-yellow-500 pl-3 py-1 mb-2">
<strong>2. Open Model Formats</strong> — ONNX or equivalent, so models run on alternative inference engines
</div>

<div class="border-l-4 border-green-500 pl-3 py-1 mb-2">
<strong>3. Government Data Rights</strong> — Unlimited rights to training data, model weights, and source code
</div>

<div class="border-l-4 border-purple-500 pl-3 py-1 mb-2">
<strong>4. Infrastructure-as-Code</strong> — Terraform or equivalent, reproducible on any provider
</div>

<div class="border-l-4 border-red-500 pl-3 py-1 mb-2">
<strong>5. Demonstrated Portability</strong> — Must deploy and pass tests on at least two environments
</div>

</v-clicks>

<div class="abs-br m-6 text-sm opacity-50 font-bold">MS</div>

<!--
If you take nothing else away from this talk, put these five requirements into your next AI solicitation. Containerized delivery. Open model formats. Government data rights. Infrastructure-as-code. And demonstrated portability — make the vendor prove it works on at least two environments before you accept delivery. These are concrete, enforceable, and directly enable compliance with the dual-source mandates.
-->

---

# Lessons from DoW Programs

Vendor Independence Works at Operational Scale

<div class="grid grid-cols-3 gap-4 mt-6">

<div class="border-2 border-blue-500 p-4 rounded">

### <span style="color: #6b21a8;">CDAO GIDE</span>

- Vendor-agnostic data integration across **50+ sources**
- Availability **>99.5%** across multiple vendor environments
- Tactical decision-making latencies are met

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

<div class="abs-br m-6 text-sm opacity-50 font-bold">MS</div>

<!--
These aren't hypothetical strategies — they're working in production today. The CDAO's GIDE program integrates data from over 50 sources using vendor-agnostic layers, achieving 99.5% availability. The Army runs a true multi-cloud strategy across all three major providers. And the Navy's approach of buying outcomes rather than platforms has kept follow-on competition robust.
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

<div class="abs-br m-6 text-sm opacity-50 font-bold">MS</div>

<!--
To wrap up: vendor independence in AI procurement is both technically achievable and now mandated by policy. The tools are mature — containerization, ONNX, Terraform, open data formats. The policy is clear — dual-source requirements, PAEs with competition incentives. Remember the five things for your next solicitation. We're happy to take questions.
-->
