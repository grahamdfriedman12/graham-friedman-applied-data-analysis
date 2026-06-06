# Automate the Intake. Preserve the Thinking.

![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Type](https://img.shields.io/badge/Type-Philosophy%20%2B%20Applied%20System-blue)

**Key takeaway:** A framework for deploying AI without losing human judgment. The Automate, Amplify, Preserve model governs which decisions should be delegated to AI, which should be amplified by it, and which need to stay fully human. Developed independently through building and failing, tested in production throughout a full recruiting cycle, and validated against published work in the field.

**Role:** Author, System Designer  
**Tools:** Claude, Claude Code, Anthropic API, Python, PowerPoint

---

## Overview

This project exists in two parts.

**The paper** is a 23-page personal account of what it actually takes to work with AI well, written from inside the first recruiting cycle meaningfully affected by AI at scale. It argues that context architecture is the core skill in AI-assisted knowledge work, not prompt engineering alone. It traces the origin of the Automate, Amplify, Preserve framework, arrived at independently and later found to match a 2016 practitioner framework by Murray and Kopen at SapientNitro. It comments on the AI bubble debate, the physical infrastructure limits most people are ignoring, the disconnection crisis, and why the human moments worth preserving are exactly the ones most at risk of being automated away.

**The presentation** is a 18-slide work showcase delivered live to Prophet's AI Foundry consulting team, using the firm itself as the case study. It walks through the full system in practice: the 8-file context architecture loaded permanently in every session, the JD Analyzer script calling the Anthropic API directly through Claude Code, the complete 25-step workflow categorized by Automate, Amplify, and Preserve tier, and the philosophy behind every design decision. The pitch: the system is sitting in the room applying to the company it was used to apply to.

The paper is the philosophy. The presentation is the applied system.

---

## The Framework

| Tier | Definition |
|---|---|
| **Automate** | Rule-based and mechanical. No personal voice or human judgment required. Output would be identical regardless of who built the system. Examples: tracker updates, portal formatting, basic research. |
| **Amplify — Technology Leading** | Claude drafts following structured rules, human reviews and revises where output does not sound right. |
| **Amplify — Human Leading** | Human provides raw reasoning and voice first. Claude structures and refines what the human brings. |
| **Preserve** | Human element so essential technology should not touch the moment itself. Relationship, trust, empathy, real-time judgment. Claude assists only in preparation and debrief. |

The critical distinction within Amplify is who starts. Resume tailoring is Technology Leading. Outreach to a specific person is Human Leading. Getting that backwards is what produces messages that feel like templates, and people can feel a template instantly.

---

## The System

The applied system is a 25-step AI-assisted workflow covering every stage of a complex multi-source research and decision process. Its foundation is a Claude Project loaded with 8 permanent files simultaneously in every session:

- Master background and pre-screening document
- Full pipeline and company interaction tracker
- Writing rulebook governing voice
- First-person AI experience and reasoning file
- Full LinkedIn description
- Full GitHub description
- Base resume PDF
- Running learnings and advice document

On top of that sits a JD Analyzer script built in Claude Code calling the Anthropic API directly, returning a structured 5-section brief covering top skills emphasized, core themes, best projects to lead with, recommended framing angle, and red flags or gaps. One script call replaces 20 minutes of careful manual reading.

The first version failed. Seven automated steps calling the API directly. Structurally correct, completely generic. Scrapped entirely after diagnosing the failure as architectural rather than technical. The system did not know the person it was supposed to represent. Rebuilt from scratch around the Claude Project architecture.

**The key insight:** the quality of AI output never exceeds the quality of the context it is working from.

---

## Key Argument from the Paper

Most AI use worldwide is a more conversational version of Google. The people building systems, designing context, and thinking carefully about where the tool should and should not be trusted are a small minority. The real work is rarer than the usage numbers suggest.

Context engineering, not prompt engineering, is the core skill. A 2026 arXiv paper on 200 documented interactions found the same pattern: failures were caused by incomplete context, not by poorly constructed prompts.

The framework applies equally to individuals and organizations. The companies getting AI deployment right are loading their systems with the specific context of the client they are serving. The ones getting it wrong are producing statistically plausible outputs that could have come from anywhere, and calling it personalization.

---

## Contents

- **Paper:**  
  [`paper/automate_intake_preserve_thinking_paper.pdf`](./paper/automate_intake_preserve_thinking_paper.pdf)  
  *(Large file — click the link above, if it does not immediatley show, then use the Download button left of the pencil button on the righthand side of the screen to view)*

- **Presentation:**  
  [`presentation/Automate_The_Intake_Preserve_The_Thinking_Presentation.pdf`](./presentation/Automate_The_Intake_Preserve_The_Thinking_Presentation.pdf)  
  *(Large file — click the link above, if it does not immediatley show, then use the Download button left of the pencil button on the righthand side of the screen to view)*

---

## How to Navigate

- Read the **paper** for the full philosophy, framework, and broader AI commentary
- Read the **presentation** for the applied system, workflow walkthrough, and live showcase structure
- Both are standalone. The paper assumes no prior knowledge of the presentation. The presentation assumes no prior knowledge of the paper.
