---
name: oh-my-opencode
description: Konfiguracja i pluginy dla OpenCode - prekonfigurowane pluginy rules i skrypty
user-invocable: true
---

# Oh My OpenCode

Kolekcja konfiguracji i pluginów dla OpenCode.

**GitHub:** https://github.com/alvinunreal/oh-my-opencode-slim

## Zawiera

- **Prekonfigurowane pluginy** - gotowe do użycia
- **Konfiguracje** - .opencode/* dla różnych scenariuszy
- **Rules i skrypty** - automation hooks
- **Kompatybilność** z magic-context, opencode-contexty

## Instalacja

```bash
git clone https://github.com/alvinunreal/oh-my-opencode-slim ~/.oh-my-opencode
```

## Struktura

```
~/.oh-my-opencode/
├── rules/           # Globalne rules
├── plugins/         # Pluginy
├── scripts/         # Automatyzacja
└── config/          # Konfiguracje
```

## Wersje

- **oh-my-opencode** - pełna wersja
- **oh-my-opencode-slim** - lekka wersja (używasz)

## Użycie

Po zainstalowaniu, dodaj do `opencode.json`:

```json
{
  "plugin": ["~/.oh-my-opencode/plugins/*"]
}
```