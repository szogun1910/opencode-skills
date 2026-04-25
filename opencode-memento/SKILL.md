---
name: opencode-memento
description: Plugin do zachowania kontekstu między sesjami OpenCode - zachowuje wiedzę projektową między sesjami, wstrzykuje kluczowe wzorce podczas kompakcji sesji
user-invocable: true
---

# OpenCode Memento

Plugin do zachowania kontekstu projektu między sesjami OpenCode.

**GitHub:** https://github.com/awdemos/opencode-memento

## Funkcje

- Wykrywa projekty z historią sesji
- Wyszukuje poprzednie sesje pasujące do obecnego kontekstu
- Wstrzykuje kontekst podczas kompakcji sesji
- Zachowuje kluczowe wzorce i konwencje projektu

## Narzędzia

- Wyszukiwanie w poprzednich sesjach
- Wstrzykiwanie wzorców AGENTS.md
- Dynamiczne dostosowywanie do aktywności projektu

## Instalacja

```json
{
  "plugin": ["opencode-memento"]
}
```

## Konfiguracja

Utwórz `.opencode/session-context.json`:

```json
{
  "minSessions": 5,
  "searchLimit": 3,
  "customContext": [
    "Zawsze używaj TypeScript",
    "Nigdy nie commituj .env"
  ]
}
```

## Opcje

| Opcja | Domyślne | Opis |
|-------|---------|------|
| minSessions | 5 | Min sesji przed aktywacją |
| searchLimit | 3 | Max sesji do przeszukiwania |
| maxPatterns | 12 | Max wzorców AGENTS.md |
| maxCustomContextLines | 20 | Max linii kontekstu |
| dbPath | ~/.local/share/opencode/opencode.db | Ścieżka do bazy danych |

## Użycie

Plugin działa automatycznie w tle. Po przekroczeniu `minSessions` aktywuje się i wstrzykuje kontekst podczas kompakcji.