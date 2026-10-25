# Security Policy

ContextFirewall sits on the path between an AI agent and its memory, and its job is to keep secrets
and untrusted facts out of the model's context. We take security reports seriously.

## Supported versions

The project is pre-1.0. Only the latest commit on `main` (and the hosted demo built from it) receives
security fixes.

## Reporting a vulnerability

**Please do not open a public issue, discussion, or pull request for a security problem.**

Report it privately instead:

1. Use GitHub's **[Report a vulnerability](https://github.com/himanshu748/ContextFirewall/security/advisories/new)**
   form (Security tab → Advisories), or
2. if that form is unavailable, contact the maintainer, [@himanshu748](https://github.com/himanshu748),
   privately on GitHub and ask for a secure channel.

Please include:

- the affected component (`backend/`, `frontend/`, `mcp/`, `supabase/`) and commit SHA,
- steps to reproduce or a proof of concept,
- the impact you observed (e.g. a secret that survives redaction, a namespace that leaks across
  accounts, a firewall check that can be bypassed).

You can expect an acknowledgement within **5 working days** and a status update at least every
**14 days** until the issue is resolved. We will credit you in the advisory unless you prefer otherwise.

## Scope

In scope:

- Secret redaction bypasses in `backend/app/firewall/secrets.py` (credentials persisted to the graph,
  vector store, or returned by any read path).
- Cross-namespace data access (one account reading or deleting another account's memories).
- Authentication or API-key handling flaws in `backend/app/identity.py` / `backend/app/auth.py`.
- Supabase RLS or privilege mistakes in `supabase/migrations/`.
- Firewall bypasses that let a stale, contradicted, secret-bearing, or unsupported memory into the
  trusted pack.

Out of scope:

- Findings that need a compromised machine, a malicious MCP client you configured yourself, or
  physical access.
- Denial of service against the free hosted demo (Hugging Face Space / Vercel) by volume alone.
- Vulnerabilities in third-party services (Hugging Face, Supabase, Neo4j, Vercel) — report those
  upstream.

## Handling secrets while testing

Never paste a real credential into an issue, a test fixture, or the public demo. Use obviously fake
values such as the AWS documentation example key `AKIAIOSFODNN7EXAMPLE`.
