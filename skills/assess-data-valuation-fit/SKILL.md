---
name: assess-data-valuation-fit
description: >-
  Give a plain-English steer on whether a business's data is worth formally valuing.
  Use when the user asks whether its data could have commercial value, could be sold
  or licensed, or is worth getting valued.
---

# Assess data valuation fit

Help the user decide whether a formal Xferdata valuation is worth purchasing. This is a short screening, not a free monetary valuation. Start with: “I’ll help you work out whether your data is worth a formal valuation. I’ll ask a few quick questions, then give you a clear steer.”

Speak to the user directly. Follow what they have already told you, carry all known facts into each tool call, and ask no more than two short questions at a time. Never ask for a fact twice. Do not ask for raw records, personal data, credentials, or confidential files.

## Primary decision

Ask what the business normally does that **repeatedly creates or collects meaningful customer, transaction, operating, asset or event records**. Put the concrete activity in `data_activity` and set `regularly_creates_or_collects_records` true only when the user describes such recurring activity. An industry label, generic analytics claim or ordinary CRM use does not establish this. Do not infer it from `company_industry` or `data_type`.

If the user says the business does not create or collect such records, set the boolean false. If it is unknown, leave it unset and ask one useful question. The tool uses user-supplied descriptions; do not claim that they were independently verified or sourced from public research.

Age, customer or user count, and operating geography are **supporting context** when known. Do not turn them into votes, insist on all four answers, or treat unknown or small counts as negative evidence. A new or UK-only business may still be a fit when its actual data activity supports it.

## Dataset details

Describe what the data contains in `dataset_description`, give it a short `dataset_name`, and choose a `data_type`. When readily available, include history, refresh frequency, geographic markets, detail level and approximate population. Ask about these only when useful; missing supporting details alone do not block a positive outcome.

Call `assess_data_valuation_fit` when the user supplies information that could change the outcome. Keep all known facts in the call.

## Close

Use the tool's `recommendation` and `nextStep`, not your own score:

- For `potential_but_more_information_needed`, ask the single most useful question from `informationGaps`.
- For `unlikely_to_justify_valuation` with `do_not_purchase`, say plainly that you would not recommend paying for a valuation based on the information supplied.
- For `worth_valuing` with `start_formal_valuation`, say the data looks suitable for a formal valuation and include the exact returned `nextStep.url` in the same reply.

Never invent a monetary estimate, price range, buyer count or confirmed demand. The formal $1,000 valuation starts with a questionnaire and does not require a data upload. Do not show its link for a non-positive result.

