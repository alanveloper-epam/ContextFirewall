## Summary

<!-- What does this PR change, and why? Link the issue it closes. -->

Closes #

## Type of change

- [ ] Bug fix
- [ ] New feature / firewall check / MCP tool
- [ ] Refactor or performance
- [ ] Documentation
- [ ] CI / tooling

## How was this tested?

<!-- Commands you ran and what they showed. UI changes: add a screenshot or recording. -->

- [ ] `cd backend && python -m pytest -q`
- [ ] `cd frontend && npm run lint && npx tsc --noEmit`
- [ ] Manually exercised the change (describe below)

## Checklist

- [ ] Tests added or updated for new behaviour
- [ ] Docs updated (`README.md`, `mcp/README.md`, `.env.example`) if behaviour or config changed
- [ ] No real secrets, tokens, or personal data in code, fixtures, or screenshots
- [ ] The six MCP tools stay identical across the hosted (`backend/app/mcp_server.py`) and stdio (`mcp/`) surfaces
