# Security

Report suspected vulnerabilities or credential exposure privately to
<support@modernmusician.me>.

Please include the affected StreetTeam endpoint or workflow, the observed behavior, the expected
behavior, and safe reproduction steps. Do not include access tokens, session credentials, customer
data, payment details, or other secrets in the report.

If you believe credentials or customer data are actively exposed, revoke the StreetTeam connection
under **Account → AI Connections** and identify the report as urgent.

## Team permissions and payout preparation

Every artist operation is intersected with current named team permissions. Custom roles combine grants; active per-person denials take precedence, including over Admin. Broad Read/Write consent cannot bypass a team restriction. Narrow content, community, workspace, commerce and settings consent families are available.

Team onboarding (`streetteam:team`), access management (`streetteam:access`) and payout preparation/reconciliation (`streetteam:payouts`) require separate consent. Bank recipient responses are masked. The shared bank connection is restricted to platform administrators. No MCP tool submits a bank payment. An authenticated human reviews the immutable amount/source/destination in StreetTeam before requesting payment; uncertain results cannot be retried. Recovery remains pending until bank funding matches the review.
