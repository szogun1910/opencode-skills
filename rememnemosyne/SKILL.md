---
name: rememnemosyne
description: Trwała pamięć dla OpenCode - persistent memory cross-session recall zarządzanie pamięcią projektową
user-invocable: true
---

# RemeMnemosyne

Trwała pamięć dla OpenCode - memory that persists across sessions.

**GitHub:** https://github.com/jph-value/RemeMnemosyne

## Funkcje

- **Persistent Memory** - pamięć która przetrwa restarty sesji
- **Cross-session Recall** - dostęp do wiedzy z poprzednich sesji
- **Memory Management** - zarządzanie wspomnieniami projektowymi

## Architektura

```
crates/              # Rust crates
configs/             # Konfiguracje
evaluation/          # Ewaluacja embeddings
```

## Storage

SQLite database z:
- Memory embeddings dla semantic search
- Session facts
- Cross-project memories

## Użycie

Wiedza projektowa (architektura, konwencje, decyzje) jest automatycznie zachowywana i dostępna w nowych sesjach.

## Konfiguracja

和环境变量:
- Database path
- Embedding provider
- Recall thresholds