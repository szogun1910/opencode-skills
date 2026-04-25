---
name: magic-context
description: Plugin do zarządzania kontekstem, pamięcią między sesjami i kompresji - nieskończony kontekst, pamięć projektowa, narzędzia ctx_reduce ctx_expand ctx_memory ctx_search
user-invocable: true
---

# Magic Context

Najbardziej zaawansowany plugin do zarządzania kontekstem dla OpenCode.

**GitHub:** https://github.com/cortexkit/opencode-magic-context

## Funkcje

1. **Kontekst kompaktowy** - kompresja przez background historian (osobny model)
2. **Pamięć między sesjami** - architektura, preferencje, decyzje persistują
3. **Dreamer** - konsoliduje i promuje wspomnienia nocą
4. **Sidekick** - rozszerza prompty o kontekst projektowy
5. **TUI sidebar** - podgląd zużycia tokenów w czasie rzeczywistym
6. **User Memories** - observacje o stylu pracy użytkownika

## Narzędzia

- `ctx_reduce` - oznacz stare wiadomości do usunięcia
- `ctx_expand` - dekompresuj historię konwersacji
- `ctx_note` - notatki do późniejszego użycia
- `ctx_memory` - trwała wiedza projektowa
- `ctx_search` - wyszukaj wszędzie (memorie, fakty, historia)

## Komendy

- `/ctx-status` - Debug kontekstu, tagi, pending drops, cache TTL
- `/ctx-flush` - Force all queued operations
- `/ctx-recomp` - Rebuild compartments and facts
- `/ctx-aug` - Sidekick augmentation na prompt
- `/ctx-dream` - Uruchom dreamer maintenance

## Instalacja

```bash
curl -fsSL https://raw.githubusercontent.com/cortexkit/opencode-magic-context/master/scripts/install.sh | bash
```

Lub ręcznie w `opencode.json`:

```json
{
  "plugin": ["@cortexkit/opencode-magic-context"]
}
```

## Konfiguracja

```jsonc
{
  "enabled": true,
  "historian": {
    "model": "github-copilot/gpt-5.4",
    "fallback_models": ["opencode-go/glm-5"]
  },
  "dreamer": {
    "enabled": true,
    "schedule": "0 3 * * *"
  }
}
```

## Tagi

Każda wiadomość i tool output ma monotoninczny tag `§N§`. Używaj ich z `ctx_reduce`:
```
ctx_reduce(drop="3-5,12")
```