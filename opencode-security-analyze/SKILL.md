---
name: opencode-security-analyze
description: Analiza bezpieczeństwa kodu w OpenCode - vulnerability detection OWASP scanning
user-invocable: true
---

# OpenCode Security Analyze

Plugin do analizy bezpieczeństwa kodu w OpenCode.

**GitHub:** https://github.com/luanweslley77/opencode-security-analyze

## Funkcje

- **Security scanning** - skanowanie pod kątem podatności
- **Vulnerability detection** - wykrywanie common vulnerabilities
- **Safe coding patterns** - enforce bezpiecznych wzorców

## Narzędzia

- `security_scan` - Skanuj kod pod kątem podatności
- `security_report` - Generuj raport bezpieczeństwa
- `check_dependencies` - Sprawdź zależności

## OWASP Top 10

Obejmuje:
1. **Injection** - SQL, NoSQL, Command injection
2. **Broken Auth** - sesje, hasła
3. **Sensitive Data** - ekspozycja danych
4. **XML External Entities** - XXE
5. **Broken Access Control** - IDOR, bypass
6. **Security Misconfig** - błędy konfiguracji
7. **XSS** - Cross-site scripting
8. **Insecure Deserialization** - deserializacja
9. **Vulnerable Components** - stare biblioteki
10. **Insufficient Logging** - brak logowania

## Użycie

```bash
/security_scan src/           # Skanuj katalog
/security_report --format md  # Raport markdown
```

## Integracja

```json
{
  "security": {
    "rules": ["OWASP"],
    "severity": "high"
  }
}
```