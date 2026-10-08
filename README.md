# Xferdata Data Value Advisor for Claude

This repository contains the Claude plugin package: instructions, connection configuration and branding.
Xferdata's hosted assessment API and valuation implementation are maintained separately.

![Xferdata mark](assets/logo.png)

Get a quick, free steer on whether the data a business creates or collects is worth a formal valuation.
Describe the recurring activity and dataset. The advisor returns a qualitative recommendation, potential value drivers and information gaps.
It uses your descriptions and does not independently verify them. Industry, operating history, scale and geography are supporting context.

The plugin does not provide a monetary valuation, buyer count, offer or confirmation of demand.
Only a positive screening includes the returned link to start a $1,000 formal Xferdata valuation on Xferdata's website.
Payments happen separately there; this plugin does not charge cards or place orders.
The formal valuation starts with a questionnaire and does not require a data upload.

## Connect

The remote MCP endpoint is https://api.prod.xferdata.com/mcp/public.
The public screening requires no sign-in or credentials.

- Claude.ai: in Settings, Connectors, add this URL as a custom connector. This tests the connector; it does not install the skill bundle.
- Claude Code: clone this repository and run `claude --plugin-dir .` from its root.
- Public directory installation: pending Anthropic review and publication.

The package has one skill and one read-only tool, `assess_data_valuation_fit`.
The skill guides the conversation, preserves known facts and displays the exact returned recommendation and conditional next-step link.

## Example prompts

These are preparation examples, not yet certified as tested in Claude:

1. Our business records freight shipments and delivery events daily. Assess our Freight events B2B dataset. It contains granular shipment and delivery records. Could it be worth formally valuing?
2. Assess our Transactions B2B dataset containing anonymized transaction records. I do not know whether we regularly create or collect those records. What information do you need?
3. Our dataset is an ordinary CRM contact list. Our business does not repeatedly create or collect meaningful records. Should we pay for a valuation?

## Data handling and support

Business and dataset descriptions supplied to the tool are sent to Xferdata's hosted API for processing.
Do not provide raw records, personal data, passwords or confidential files.
Stateless transport does not establish backend logging, storage or retention practices; the published privacy policy must accurately cover actual processing before submission.

- Website: https://www.xferdata.com
- Support: https://www.xferdata.com/contact-us
- Privacy: https://www.xferdata.com/privacy (coverage and accuracy review outstanding)

If the connector cannot be reached, check its URL and tool discovery, retry later, or contact support.
A failed call is not a completed screening. No local database, executable server, hooks or dependency installation are provided by this package.

## Submission status

This is a private preparation repository. Production alignment, privacy/documentation review,
actual Claude testing and portal validation remain outstanding.
See [submission preparation](SUBMISSION.md) for the portal fields and remaining steps.

## License

The plugin instructions, configuration and documentation are licensed under MIT; see [LICENSE](LICENSE).
The Xferdata logo files in assets/ are excluded from the MIT grant and remain proprietary to Xferdata. No trademark rights are granted.
This license does not cover the separately hosted API, backend source, valuation implementation or business data.
