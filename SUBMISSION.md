# Claude submission preparation

Package version: 0.1.2. Seeded from Xferdata/xferdata-app PR #2207.
No Claude directory submission or publication has been performed by this setup.

## Plugin bundle source fields

- Portal: https://claude.ai/directory/manage
- Submission type: Plugin bundle
- Repository: Xferdata/xferdata-claude-plugin
- Plugin path: leave empty; the package is at the repository root
- Branch or tag: main
- Internal name: xferdata-data-value-advisor
- Publisher in source: Xferdata (confirm the actual publishing organization)

Connect a GitHub account with push access in the intended Claude organization.
For private review, the portal also requires its GitHub App installed on this repository and consent to source scanning.
The repo must become public before the plugin goes live; changing visibility is a separate release action.
Choose a license and add a LICENSE file or license field before directory validation. None has been assumed.

## Separate MCP connector submission

Submit https://api.prod.xferdata.com/mcp/public as an MCP connector from the same Claude organization.
Authentication: none for this public screening. Explain that reviewers need no credentials; do not invent an account.
The connector reads supplied descriptions and returns an assessment. It does not write user accounts or execute purchases.
Use the same URL in both submissions and pair the listings where the portal supports it.

Prepare the company/review contact, name, one-liner, description, categories, icon, public documentation URL,
privacy URL, support contact and at least three working examples. The current private README is not a public documentation URL.
Screenshots for an interactive MCP App carousel do not apply to this headless connector.

## Remaining gates

- License: undecided; do not silently grant open-source rights.
- Production: the last check during ChatGPT packaging still exposed the old schema. Verify tools/list includes data_activity and regularly_creates_or_collects_records after deployment.
- Host testing: all Claude examples remain Not run. Test recurring activity, missing activity, explicit no-fit and small UK-only context, as well as unsupported price, raw-data access and payment requests.
- Policy: verify actual processing, sharing, logs, retention and deletion. Review the published privacy policy's security claims and plugin coverage.
- Public docs: publish accurate setup, usage, limitations, privacy, pricing/conditional CTA and troubleshooting instructions.
- Value: demonstrate a useful screening result independent of purchase. Anthropic disallows software primarily intended as advertising or promotion.
- Portal: confirm the intended organization, run validation, resolve scan findings and complete authorized acknowledgments.
- Public release: make only this plugin repository public after preparation; the backend application repository stays private.

## Maintaining the package

The initial skill, connection and assets match PR #2207. Changes here do not deploy the hosted API.
When updating the shared skill or endpoint, synchronize its counterpart in xferdata-app and bump the Claude manifest version.
Do not commit generated ZIPs, credentials, raw datasets or backend application source here.

## Official references

- https://claude.com/docs/directory/publish
- https://claude.com/docs/plugins/submit
- https://claude.com/docs/plugins/pre-submission-checklist
- https://claude.com/docs/connectors/building/submission
- https://support.claude.com/en/articles/13145358-anthropic-software-directory-policy
