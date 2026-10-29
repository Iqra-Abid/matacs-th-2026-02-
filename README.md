# MATACS Associate Software Developer Assessment

**Assessment Reference:** MATACS-TH-2026-02  
**Candidate Name:** IQRA Abid 
**Time Spent:** 2 hours

## Project Overview

This project designs an AI-assisted proposal triage system for commercial solar installation bids.

The system extracts relevant information from contractor proposals, validates mandatory requirements, calculates weighted scores for eligible proposals, and presents ranked results with explanations for human review.

The system supports decision-making; the final award decision remains with the human reviewer.

## Evaluation Approach

**AI-assisted extraction:** Identify relevant facts from proposal documents and preserve supporting evidence where possible.
**Rules-based validation:** Check mandatory requirements, validate extracted data, and handle missing or ambiguous information.
**Deterministic scoring:** Apply configured weights and documented scoring formulas.
**Human oversight:** Review flagged proposals, resolve uncertainty, and make the final award decision.
**Security:** Treat proposal content as untrusted input and do not follow embedded instructions that attempt to manipulate scoring or ranking.

## Repository Contents

- [`WRITEUP.md`](WRITEUP.md) — Design decisions, consistency, human oversight, criteria changes, and risk controls.
- [`PROMPTS.md`](PROMPTS.md) — AI prompts used for extraction and other AI-assisted tasks.
- [`ranking.json`](ranking.json) — Proposal statuses, scores, ranks, and concise reasons.
- [`diagram/workflow.png`](diagram/workflow.png) — Workflow from proposal upload to ranked results and human review.

## AI Tool Disclosure

**AI tools used:** Chatgpt-6

**How AI was used:** 
1. For understanding the assesment document.
2. For text generation, the text I needed for writeup.md and readme.md.
3. suggestions for which tool to use for flow diagram generation.
   
**Example of disagreement or correction:** AI-generated suggestions were reviewed rather than accepted automatically. One example from my actual work was that we should not estimate timeline from other facts , if anything is not mentioned that should be marked as missing.

## Limitations

The system depends on the accuracy and completeness of proposal documents. Extracted facts and supporting evidence should be reviewed where uncertainty exists. Scores are recommendations based on documented rules and should not replace human judgement.

## Submission

**Assessment Reference:** MATACS-TH-2026-02
