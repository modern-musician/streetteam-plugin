# StreetTeam

**Your artists. Your people.**

Bring your tasks, calls, leads, and artist community into ChatGPT, Claude, and Codex. This package
uses one hosted StreetTeam service, with the same tools and workflow guidance in every assistant. It
needs no local server, runtime, or credentials file. The assistant renews access using OAuth when
the connection includes offline access; revocation or expiry can still require signing in again.

## Install

Installing the plugin connects StreetTeam for you: it brings the hosted server, the StreetTeam
workflow guidance and the starter prompts in one step. There is nothing else to add.

### Claude Code

```sh
/plugin install streetteam --marketplace modern-musician/streetteam-plugin
```

That one step adds the marketplace and installs the plugin on Claude Code 2.1.275 or later. On
2.1.150 through 2.1.274, add the marketplace first:

```sh
/plugin marketplace add modern-musician/streetteam-plugin
/plugin install streetteam@streetteam-hosted
```

Versions before 2.1.150 refuse the plugin's listing fields; update Claude Code first (`claude update`).

Start a new session and sign in to StreetTeam when Claude Code asks (or run `/mcp`).

### Codex (desktop, CLI, and IDE extension)

```sh
codex plugin marketplace add modern-musician/streetteam-plugin
codex plugin add streetteam@streetteam-hosted
```

Codex asks you to sign in to StreetTeam when the plugin installs. Start a new conversation after.

### Claude and ChatGPT apps

Find **StreetTeam** in the app's connector or app directory and choose **Connect**. Until the
listing is available in yours, use the manual connection below. Your workspace owner may need to
allow connectors for your plan or organization.

## Connect manually

Use this only when you cannot install the plugin. Do not add it alongside the plugin: both use the
same hosted tools, and two connections show every tool twice.

Server URL: **https://streetteam.fm/api/mcp**

- **Claude web, desktop and mobile:** Settings → Connectors → Add custom connector, then enter the
  server URL and connect your StreetTeam account.
- **Claude Code:** `claude mcp add --transport http --scope user streetteam-hosted
https://streetteam.fm/api/mcp`, then `/mcp` to sign in.
- **Codex:** `codex mcp add streetteam-hosted --url https://streetteam.fm/api/mcp`, then
  `codex mcp login streetteam-hosted`.

Step-by-step instructions for every assistant, including the ChatGPT web app, live at
<https://streetteam.fm/docs/mcp>.

## Sign in and verify

1. Sign in on the StreetTeam authorization page opened by your assistant.
2. Review the requested permissions on the StreetTeam consent screen; uncheck any you do not want.
   Explicitly approve any additional permissions before connecting. When adding access, keep the
   permissions you still need and Stay connected selected.
3. Return to your assistant and start a new conversation.
4. Ask “List the StreetTeam artists I can manage.” Confirm the expected account and artists.

Your current StreetTeam role is checked on each request. The integration never asks you to paste a
password, authentication token, or cookie into chat. Changes should follow your explicit instruction
or approval; read the changed item back to verify success.

## Try it

- “Plan my week and recommend my top three priorities.”
- “Review my overdue follow-ups and draft the next steps.”
- “Summarize my latest call and suggest action items.”

## Updates and recovery

- **Tools missing:** check `codex mcp list` or Claude Code's `/mcp`, enable the connection, and start
  a new conversation. For a plugin update, use the marketplace that installed it.
- **Sign-in expired:** use `codex mcp login streetteam-hosted` for the manual connection above,
  Claude Code's `/mcp`, or reconnect in Claude's connector settings. Plugin connections use the
  host's plugin sign-in flow. Report recurring sign-in failures rather than repeatedly reinstalling.
- **Access denied:** verify the account, artist role, and granted OAuth permissions. Reconnecting
  cannot grant a role your StreetTeam account does not have.
- **Interrupted read:** retry once after a brief pause, respecting any retry delay.
- **Interrupted write:** inspect the affected task, deal, or post before retrying. Sending a message
  or completing a task may have succeeded even when the response was lost. Reuse an idempotency key
  only where the tool supports it; never blindly repeat a send.

Hosted tool updates are applied on StreetTeam. Packaging and instruction updates arrive through your
installed plugin marketplace. For support, send the assistant name/version, time, tool name and
sanitized error text. Leave out credentials and private customer content.

## Disconnect

Open [Account → AI Connections](https://streetteam.fm/account/connections) and revoke the connection.
The assistant must reconnect before accessing StreetTeam again.

## Privacy and support

- [Setup and troubleshooting](https://streetteam.fm/docs/mcp)
- [Privacy](https://streetteam.fm/legal/privacy-policy) · [Terms](https://streetteam.fm/legal/terms)
- Support and security reports: support@modernmusician.me
