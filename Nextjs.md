# Praca agentowa nad aplikacjami Next.js

## 1. Inicjalizacja i struktura nowego projektu Next.js

### Inicjalizacja Next.js

Domyślnie używaj aktualnej stabilnej wersji Next.js, TypeScript, App Routera, Tailwind CSS, ESLint, npm oraz kodu w `src/`. Jeśli wymagania projektu są inne, dostosuj te wybory.

- Wybierz wspieraną wersję Node.js LTS zgodną z [wymaganiami Next.js](https://nextjs.org/docs/app/getting-started/installation). Zapisz wybraną wersję w `.node-version`.
- Utwórz projekt oficjalnym [generatorem `create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app). Uruchom poniższą komendę w katalogu nadrzędnym; `nazwa-projektu` zastąp właściwą nazwą aplikacji.

```powershell
npx --yes create-next-app@latest nazwa-projektu --typescript --tailwind --eslint --app --src-dir --use-npm --import-alias "@/*" --agents-md --disable-git --yes
```

Generator tworzy podstawowe pliki i instaluje zależności. `--disable-git` wyłącza automatyczną inicjalizację Git; po wygenerowaniu projektu użyj `git init` w jego katalogu, jeśli nie należy już do repozytorium. Nie twórz commita.

Dodaj brakujące pliki i katalogi z poniższej struktury. Zachowaj konfigurację i blokadę zależności wygenerowane przez narzędzie.

Uruchomienie aplikacji:

```powershell
cd nazwa-projektu
npm run dev
```

Mały prototyp może mieć prostszy układ. Uzasadnij uproszczenie zamiast automatycznie tworzyć cały szkielet rozbudowanej aplikacji.

### Struktura podstawowa

```text
projekt/
├── .git/                       # Tworzony przez Git, nie ręcznie
├── node_modules/               # Zależności npm, poza Git
├── .next/                      # Wyniki pracy Next.js, poza Git
├── AGENTS.md                   # Instrukcje projektu; zachowaj treść generatora
├── CLAUDE.md                   # Zawiera wyłącznie: @AGENTS.md
├── PLANS.md
├── PROJECT_CONTEXT.md
├── HANDOFF.md
├── README.md
├── README_SHORT.md
├── ARCHITECTURE.md
├── DECISIONS.md
├── .gitignore
├── .env.example                # Bezpieczny wzór zmiennych środowiskowych
├── .node-version               # Wybrana wersja Node.js
├── package.json                # Zależności i skrypty npm
├── package-lock.json           # Blokada wersji zależności npm
├── tsconfig.json               # Konfiguracja TypeScript i aliasu @/*
├── next.config.ts              # Konfiguracja Next.js
├── next-env.d.ts               # Generowany przez Next.js, poza Git
├── eslint.config.mjs           # Konfiguracja ESLint
├── postcss.config.mjs          # Konfiguracja PostCSS dla Tailwind CSS
├── public/                     # Wyłącznie publiczne zasoby aplikacji
├── data/
│   ├── input/                  # Materiały dostarczane przez użytkownika
│   └── output/                 # Wygenerowane wyniki
└── src/
    ├── app/
    │   ├── layout.tsx          # Główny layout aplikacji
    │   ├── page.tsx            # Strona główna (/)
    │   └── globals.css         # Globalne style
    ├── components/             # Wspólne komponenty interfejsu
    └── lib/                    # Funkcje pomocnicze i integracje
```

- Używaj jednego katalogu routingu: domyślnie `src/app/`. Pliki konfiguracyjne, `.env.*` i `public/` pozostaw w katalogu głównym, zgodnie z [konwencją `src/`](https://nextjs.org/docs/app/api-reference/file-conventions/src-folder).
- Pliki konfiguracji mogą mieć inne rozszerzenia w kolejnych wersjach generatora. Zachowaj wygenerowany wariant; nie dodawaj drugiej konfiguracji tego samego narzędzia.
- `.next/` powstaje podczas uruchamiania lub budowania aplikacji. `next-env.d.ts` generuje Next.js; nie twórz go ręcznie.
- Zachowaj instrukcje Next.js wygenerowane w `AGENTS.md`. Jeśli generator nie utworzy tego pliku, może on pozostać pusty. W `CLAUDE.md` pozostaw wyłącznie import `@AGENTS.md`.
- Pliki dokumentacji uzupełnij zwięzłą treścią dopasowaną do tworzonego projektu.

Opis przeznaczenia i wymaganej zawartości plików dokumentacyjnych `.md` znajduje się w globalnym `AGENTS.md`.

### Dane wejściowe i wyniki

- Stosuj nazwy `data/input/` i `data/output/`, małymi literami.
- `input/` zawiera materiały użytkownika, np. dokumenty, obrazy i assety; `output/` zawiera wygenerowane raporty, pliki i inne rezultaty.
- Utwórz oba katalogi i ignoruj je w Git w całości. Prywatnych materiałów nie umieszczaj w `public/`.
- Zasoby udostępniane przez aplikację przechowuj w `public/`, a bezpieczne dane testowe mogą znajdować się w `tests/fixtures/`.

### Elementy dodawane według potrzeb

```text
src/app/api/nazwa/route.ts      # Endpoint backendowy Next.js
src/lib/server/                # Moduły przeznaczone wyłącznie dla serwera
src/hooks/                     # Wspólne hooki React
src/types/                     # Wspólne typy TypeScript
config/                        # Ustawienia bez sekretów
scripts/                       # Skrypty pomocnicze
docs/                          # Dodatkowa dokumentacja
tests/                         # Testy projektu
tests/fixtures/                # Bezpieczne dane testowe
runtime/                       # Lokalny stan aplikacji, poza Git
.env.local                     # Lokalne ustawienia i sekrety, poza Git
```

`nazwa` oznacza nazwę konkretnego endpointu. Pliki `.env.*` pozostają w katalogu głównym. Prefiks `NEXT_PUBLIC_` stosuj tylko dla wartości przeznaczonych do udostępnienia przeglądarce, zgodnie z [dokumentacją zmiennych środowiskowych](https://nextjs.org/docs/app/guides/environment-variables).

## 2. `.gitignore`

### Domyślna zawartość

Uzupełnij `.gitignore` wygenerowany przez `create-next-app` o brakujące wzorce z poniższego zestawu.

```gitignore
# Zależności npm
node_modules/

# Pliki generowane przez Next.js i TypeScript
.next/
out/
dist/
*.tsbuildinfo
next-env.d.ts

# Sekrety i lokalne pliki środowiskowe
.env
.env.*
!.env.example
!.env.*.example
/secrets/

# Wyniki testów
coverage/
playwright-report/
test-results/

# Logi i pamięć podręczna
*.log
*.log.*
npm-debug.log*
logs/
.cache/
/cache/
/tmp/
/temp/
.vercel/

# Prywatne dane i lokalny stan aplikacji
/data/input/
/data/output/
/runtime/

# Lokalne pliki edytorów
.idea/
.vscode/
*.swp
*.swo
*~

# Osobiste ustawienia Claude Code w projekcie
CLAUDE.local.md
.claude/settings.local.json

# Pliki systemu operacyjnego
.DS_Store
Thumbs.db
Desktop.ini
```
