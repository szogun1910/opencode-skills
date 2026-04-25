---
name: opencode-search
description: Wyszukiwanie w kontekście sesji OpenCode - semantic search w sesjach i historii konwersacji
user-invocable: true
---

# OpenCode Search

Plugin do wyszukiwania w sesjach i kontekście OpenCode.

**GitHub:** https://github.com/whaaaley/opencode-search

## Funkcje

- **Semantic search** - szukanie po znaczeniu, nie słowach kluczowych
- **Wyszukiwanie w sesjach** - dostęp do poprzednich sesji
- **Indexowanie kontekstu** - automatyczne tagowanie treści

## Narzędzia

- `search_sessions` - Wyszukaj w poprzednich sesjach projektu
- `search_context` - Szukaj w obecnym kontekście sesji
- `index_context` - Ręcznie indexuj kontekst

## Użycie

```bash
/search authentication     # Szukaj o auth
/search "last week"       # Szukaj z daty
```

## Konfiguracja

```json
{
  "search": {
    "limit": 10,
    "threshold": 0.7
  }
}
```

## Indexowanie

Plugin automatycznie indexuje:
- Wiadomości użytkownika
- Odpowiedzi agenta
- Wyniki narzędzi
- Pliki w kontekście