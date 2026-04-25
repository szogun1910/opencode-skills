---
name: opencode-contexty
description: Context Engineering dla OpenCode - HSCMM AASM ACPM zarządzanie kontekstem z wizualizacją real-time
user-invocable: true
---

# OpenCode Contexty

Context Engineering dla OpenCode - zarządzanie kontekstem na profesjonalnym poziomie.

**GitHub:** https://github.com/ttalkkak-lab/opencode-contexty

## Główne Systemy

### AASM (Active Agent-supervised Architecture)
- Interwencja na poziomie promptu przed rozpoczęciem zadania
- Wykrywanie anty-patternów (monolityczne pliki, God Objects)
- Korekta złych kierunków w rozwoju projektu

### HSCMM (Human-supervised Context Management)
- **Context Explorer** - wizualizacja plików w kontekście AI (tree format)
- **Manual Context Injection** - drag & drop kontekstu
- **Blacklist** - `/ban @src/legacy` blokowanie ścieżek

### ACPM (Active Context Permission Management)
- Restrykcje narzędzi (file-read, file-write, shell, lsp, web)
- Hierarchiczne uprawnienia ścieżek (denied, read-only, read-write)
- Presety sesji (Safe Mode, Aggressive Refactoring Mode)

### TLS (Terminal Log Supervision)
- Klasyfikacja Success/Failure/Warning
- Ekstrakcja kluczowych błędów z setek linii logów

### DCP (Dynamic Context Pruning)
- Automatyczna kompresja niskowartościowych danych
- Optymalizacja token efficiency

## Instalacja

```bash
bunx @ttalkkak-lab/opencode-contexty init
```

## Konfiguracja

```json
{
  "aasm": {
    "mode": "active",
    "model": "openai/gpt-5.3-codex-spark"
  },
  "dcp": {
    "enabled": true,
    "strategies": {
      "deduplication": { "enabled": true },
      "purgeErrors": { "enabled": true, "turns": 4 }
    }
  }
}
```