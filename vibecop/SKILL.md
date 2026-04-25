---
name: vibecop
description: AI code quality toolkit - 35 detektorów bugów god functions N+1 queries unsafe shell security scanning
user-invocable: true
---

# Vibecop - AI Code Quality Toolkit

Deterministyczny linter dla ery AI coding. 35 detektorów łapie bugi które AI wprowadza.

**GitHub:** https://github.com/bhvbhushan/vibecop

## Detektory (35)

| Kategoria | Ilość | Przykłady |
|-----------|-------|-----------|
| **Quality** | 16 | God functions, God classes, Magic numbers |
| **Security** | 7 | Unsafe shell exec, SQL injection, Hardcoded secrets |
| **Correctness** | 4 | N+1 queries, Type errors |
| **Testing** | 8 | Trivial assertions, Empty tests |

## Komendy

```bash
vibecop scan .                    # Skanuj katalog
vibecop scan src/ --format json  # JSON output
vibecop scan . --diff HEAD       # Tylko zmienione pliki
vibecop init                      # Auto-setup agent integration
vibecop serve                     # Start MCP server
```

## Integracja z Agentami

| Tool | Integracja |
|------|------------|
| Claude Code | PostToolUse hook |
| Cursor | afterFileEdit hook + rules |
| Codex CLI | PostToolUse hook |
| Aider | --lint-cmd |
| GitHub Copilot | Custom instructions |

## MCP Server

```json
{
  "mcpServers": {
    "vibecop": {
      "command": "npx",
      "args": ["vibecop", "serve"]
    }
  }
}
```

4 narzędzia MCP: `vibecop_scan`, `vibecop_check`, `vibecop_explain`, `vibecop_context_benchmark`

## Context Optimization (Beta)

Redukcja tokenów o ~35% na re-readach. Służy AST skeleton zamiast pełnego pliku.

```bash
vibecop context benchmark  # Projekcja oszczędności
vibecop init --context     # Konfiguracja hooków
vibecop context stats      # Statystyki po sesjach
```

## GitHub Action

```yaml
- uses: bhvbhushan/vibecop@main
  with:
    on-failure: comment-only
    severity-threshold: warning
```