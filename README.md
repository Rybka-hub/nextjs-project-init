# Praca agentowa nad aplikacjami Next.js

Skill **`nextjs-project-init`** inicjalizuje nową aplikację Next.js i przygotowuje uporządkowaną strukturę plików oraz `.gitignore`. Jego celem jest powtarzalny początek dalszej pracy z agentem.

## Co robi

- Tworzy projekt przez oficjalny generator `create-next-app`.
- Domyślnie wybiera TypeScript, App Router, Tailwind CSS, ESLint, npm i kod w `src/`.
- Dodaje dokumentację oraz katalogi `data/input/` i `data/output/`.
- Uzupełnia `.gitignore` dla zależności, plików generowanych, sekretów i danych.
- Uwzględnia prostszy układ dla małego prototypu.

Skill realizuje inicjalizację. Funkcje aplikacji, jej architektura i integracje wynikają z osobnego zakresu zlecenia. Wymagania użytkownika mogą zmienić domyślne wybory.

## Co zawiera zestaw

| Plik | Zawartość |
| --- | --- |
| [SKILL.md](SKILL.md) | Punkt wejścia: nazwa, zakres i instrukcje wykonania skilla. |
| [Nextjs.md](Nextjs.md) | Sposób inicjalizacji, struktura projektu i wzór `.gitignore`. |
| [Agent.md](Agent.md) | Pomocniczy wzór zasad pracy i opisów dokumentacji. |
| [CHANGELOG.md](CHANGELOG.md) | Historia opublikowanych wersji i ich zmian. |
| `README.md` | Cel zestawu, instalacja i przykłady użycia. |

Nie kopiuj samego `SKILL.md` — korzysta on z pozostałych materiałów w folderze.

## Wersjonowanie

Numer zainstalowanej wersji znajduje się w `metadata.version` w [SKILL.md](SKILL.md). Każde wydanie ma tag Git `vX.Y.Z` i odpowiadające mu [wydanie na GitHubie](https://github.com/Rybka-hub/nextjs-project-init/releases). Historię zmian opisuje [CHANGELOG.md](CHANGELOG.md).

Stosujemy SemVer:

- `PATCH`, np. `1.0.1`: poprawki i doprecyzowania bez zmiany przyjętego standardu.
- `MINOR`, np. `1.1.0`: rozszerzenia zgodne z dotychczasowym sposobem użycia.
- `MAJOR`, np. `2.0.0`: zmiany zasad lub struktury wymagające dostosowania dotychczasowego sposobu użycia.

Oba skille są wersjonowane niezależnie. Opublikowanego tagu nie zmieniamy; kolejne poprawki otrzymują nowy numer. Gałąź `main` może zawierać zmiany jeszcze niewydane — do instalacji wybieraj konkretne wydanie. Aktualizacja skilla nie modyfikuje wcześniej utworzonych projektów.

## Instalacja w Codexie

1. Pobierz wybraną wersję ze strony [wydań](https://github.com/Rybka-hub/nextjs-project-init/releases) przez „Source code (zip)” i rozpakuj archiwum. Możesz też użyć całego folderu z lokalnego zestawu.
2. Skopiuj go do `~/.agents/skills/nextjs-project-init/`. `~` oznacza katalog użytkownika; na Windows jest to `%USERPROFILE%`.
3. Sprawdź, czy plik wejściowy ma ścieżkę `~/.agents/skills/nextjs-project-init/SKILL.md`, bez dodatkowego zagnieżdżenia folderu.
4. Jeśli skill nie pojawi się na liście, uruchom Codexa ponownie.

Instalację ograniczoną do jednego projektu wykonasz, umieszczając ten sam folder w `.agents/skills/nextjs-project-init/` w jego katalogu. Lokalizacje opisuje [oficjalna dokumentacja skilli Codexa](https://learn.chatgpt.com/docs/build-skills).

## Użycie

Po instalacji wywołaj skill w Codexie, np.:

```text
$nextjs-project-init Przygotuj nowy projekt Next.js dla panelu raportów w katalogu wskazanym w tej rozmowie. Użyj domyślnych ustawień i na razie utwórz tylko szkielet.
```

```text
$nextjs-project-init Zainicjalizuj mały prototyp Next.js do prezentowania wyników automatyzacji. Zastosuj uproszczony układ i uzasadnij wybór.
```

Podaj cel projektu i katalog docelowy. Skill jest przeznaczony do nowych projektów; zwykłe poprawki w istniejącej aplikacji nie wymagają jego ponownego uruchamiania.

## Globalne instrukcje i dokumentacja

Opisy dokumentów projektu są utrzymywane w globalnym `AGENTS.md`. Jeśli użytkownik ich nie ma, skill korzysta z odpowiedniej części dołączonego `Agent.md`, bez powielania opisów w swoim punkcie wejścia.

Instalacja skilla nie instaluje globalnych zasad. Opcjonalnie przejrzyj `Agent.md`, dopasuj go do własnych preferencji i włącz wybrane zasady do `~/.codex/AGENTS.md`. Zachowaj istniejące instrukcje. Domyślną lokalizację opisuje [dokumentacja AGENTS.md](https://learn.chatgpt.com/docs/agent-configuration/agents-md).

## Udostępnianie na GitHubie

Publikuj cały folder z powyższymi plikami. Może być osobnym repozytorium albo częścią repozytorium zawierającego również skill Python. Użytkownik instaluje folder pod nazwą `nextjs-project-init`.

Zestaw składa się z instrukcji i materiałów Markdown; nie zawiera automatycznego instalatora ani wymagań związanych z kluczami API. Do wykonania inicjalizacji potrzebne są zgodne z Next.js Node.js i npm, Git oraz dostęp do pobrania generatora i zależności.
