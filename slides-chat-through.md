# Slides Chat-Through Notes

## Slide 8 — Policy Mandate: Sec Hegseth Acquisition Reforms

The idea of vendor lock-in is conceptually simple; but the implementation of a strategy to mitigate vendor lock-in is technically difficult. We have a white paper with all the details and references; please ask me if you would like a copy.

## Slide 9 — Technical Strategies for Platform Independence

There are three technical strategies to mitigate vendor lock-in. And by the way, some vendor lock-in is unavoidable. The point is to have as much control as possible; the point is not to be an open source purist (which also carries risks of vendor lock-in) but to keep future options in place if possible. It is a matter of degree not of yes/no.

## Slide 10 — Procurement Strategies

An SBOM — a Software Bill of Materials — is essentially a complete ingredient list for your software: every library, framework, and dependency your AI system relies on. Without one, you don't even know what you're locked into until you try to leave. The Army already mandates SBOMs for all new software contracts as of February 2025.

Background IP vs. foreground IP — this distinction is critical in defense contracting. Background IP is what the vendor brings to the table: their pre-existing frameworks, libraries, and tools they developed on their own dime before the contract. Foreground IP is what gets created *during* the contract using government funding. The government should retain unlimited rights to foreground IP — the models trained on your data, the code written for your mission. Background IP is where it gets tricky: vendors legitimately own it, but if your system depends on it, that's a lock-in vector. The contract needs to clearly separate the two so you know exactly what you own and what you're licensing.
