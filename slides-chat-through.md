# Slides Chat-Through Notes

## Slide 8 — Policy Mandate: Sec Hegseth Acquisition Reforms

The idea of vendor lock-in is conceptually simple; but the implementation of a strategy to mitigate vendor lock-in is technically difficult. We have a white paper with all the details and references; please ask me if you would like a copy. Captain Andrew Privette in the first keynote spoke about the PAE replacing PEO. 

## Slide 9 — Technical Strategies for Platform Independence

There are three technical strategies to mitigate vendor lock-in. And by the way, some vendor lock-in is unavoidable. The point is to have as much control as possible; the point is not to be an open source purist (which also carries risks of vendor lock-in) but to keep future options in place if possible. It is a matter of degree not of yes/no.

## Slide 10 — Procurement Strategies

An SBOM — a Software Bill of Materials — is essentially a complete ingredient list for your software: every library, framework, and dependency your AI system relies on. Without one, you don't even know what you're locked into until you try to leave. The Army already mandates SBOMs for all new software contracts as of February 2025.

Background IP vs. foreground IP — this distinction is critical in defense contracting. Background IP is what the vendor brings to the table: their pre-existing frameworks, libraries, and tools they developed on their own dime before the contract. Foreground IP is what gets created *during* the contract using government funding. The government should retain unlimited rights to foreground IP — the models trained on your data, the code written for your mission. Background IP is where it gets tricky: vendors legitimately own it, but if your system depends on it, that's a lock-in vector. The contract needs to clearly separate the two so you know exactly what you own and what you're licensing.

## Slide 11 — Contract Requirements for Vendor Independence

These are the five things that, from the point of view of government contracting, are needed to mitigate vendor lock-in.

## Slide 12 — Lessons from DoW Programs

GIDE — the Global Information Dominance Experiments — is one of the most fascinating programs to come out of the DoW in recent years. NORTHCOM created it in 2020 and it was handed to the Chief Digital and AI Office in 2022. What makes GIDE special is how it works: 90-day sprint cycles where software engineers sit side-by-side with warfighters at combatant commands, getting real-time feedback on live operational networks. It's not a lab experiment — it's iterative development against real mission data. By GIDE 9 in early 2024, they had demonstrated a completely vendor-agnostic data integration layer pulling from over 50 different sources with 99.5% availability. That's the proof that vendor independence doesn't mean sacrificing operational performance. And the timing couldn't be more relevant — when the Anthropic dispute hit in February 2026 and defense contractors were ordered to stop using Claude, organizations built on GIDE-style vendor-agnostic architectures could swap providers with minimal disruption. Those that were locked in faced a six-month scramble.
