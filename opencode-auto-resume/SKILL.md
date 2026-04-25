---
name: opencode-auto-resume
description: Auto-resume sesji OpenCode - auto-save sesji resume po crashu stan sesji backup
user-invocable: true
---

# OpenCode Auto Resume

Plugin do automatycznego wznawiania sesji OpenCode po awarii.

**GitHub:** https://github.com/Mte90/opencode-auto-resume

## Funkcje

- **Auto-save** - automatyczny zapis stanu sesji
- **Resume po crashu** - przywróć sesję po nagłym zamknięciu
- **Stan sesji backup** - trwała kopia stanu

## Jak działa

1. Sesja jest periodystycznie zapisywana
2. Przy nagłym zamknięciu - ostatni stan jest zachowany
3. Przy kolejnym uruchomieniu - pytanie o resume
4. Opcja przywrócenia do ostatniego punktu

## Konfiguracja

```json
{
  "autoResume": {
    "enabled": true,
    "interval": 60,
    "maxBackups": 5
  }
}
```

| Opcja | Domyślne | Opis |
|-------|---------|------|
| enabled | true | Włącz auto-resume |
| interval | 60 | Sekundy między zapisami |
| maxBackups | 5 | Max kopii zapasowych |

## Użycie

Plugin działa automatycznie. Opcjonalnie wymuś:

```bash
/resume           # Lista dostępnych sesji
/resume last     # Przywróć ostatnią
/resume 5m       # Przywróć sprzed 5 minut
```

## Ograniczenia

- Tylko stan textowy (nie pliki na dysku)
- Ograniczony do ostatniego save'a