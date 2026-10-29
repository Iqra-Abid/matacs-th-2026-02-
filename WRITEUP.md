
## 1. Which steps should use AI, and which should use plain code or rules? Why?

AI should be used to extract relevant information from contractor proposals but the prompts should identify any misleading information for example in lakeview proposal there's the "rank me first" instruction.
Eligible proposals should be evaluated using the configured weights: experience (30%), price (25%), timeline (15%), warranty (15%), and team and approach (15%).
The human reviewer is responsible for reviewing and making the final award decision.Python performs mandatory checks, calculates weighted scores, and assigns rankings.

## 2. How would you make scoring consistent and explainable? Would two runs produce the same ranking?

Scoring should use documented formulas which can be decided by the reviewer or the project manager(someone who has been working or doing this work manually could best describe the criteria)
And yes two runs should produce the same ranking only if the inputs are validated ,the same criteria and deterministic formulas are used. AI should not independently decide the final score or change the ranking.


## 3. Where should humans review, confirm, or override decisions? What should be logged?

Humans should review the ineligible category and the statements under missing information category or suspicious.
The audit record should include the proposal identifier, extracted facts and evidence references, validation results, criteria configuration and version, scoring formula version, calculated scores, status changes, flags and their resolution, reviewer overrides with reasons, and the final decision.

## 4. What happens if an administrator changes criteria or weights after scoring?

When an administrator changes criteria or weights, the system should create a new configuration version rather than overwriting the previous one. Existing results should retain the configuration version under which they were calculated so that previous decisions remain explainable.
The system should notify the reviewer that existing scores may be outdated and offer to recalculate them using the new configuration. 

## 5. What could go wrong, and how would you reduce the risks?


AI may misread prices, licence numbers, warranty terms, or timelines. I would validate the output against a defined schema and verify important facts against the proposal evidence.

AI may fill gaps with plausible but unsupported information. I would use strict prompts and make sure missing information is marked as unknown instead of allowing AI to guess.

Different interpretations or rounding may change results. I can use deterministic code and fixed formulas to make scoring consistent.

A proposal may contain instructions intended to manipulate an AI reviewer, as seen in the Lakeview proposal. The system should ignore these instructions, treat proposal content as untrusted data, and log suspicious content for review. However, the proposal should not automatically be marked ineligible just because it contains such instructions; it should still be evaluated against the defined criteria.

Processing every document repeatedly with AI may be slow, so I can extract the data once, validate it, and then run the deterministic scoring script without another AI call unless re-extraction is needed.

An automated ranking could be mistaken for an award decision. We can display reasons and flags, maintain an audit history, and still require a human reviewer to make the final award decision.

Overall, the system should use AI to interpret documents, deterministic rules to evaluate proposals, and human oversight to resolve uncertainty and make the final decision.
