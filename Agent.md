# Praca

- Pisz po polsku, również w dokumentacji dla użytkownika, chyba że poprosi o inny język.
- Realizuj uzgodniony zakres, zachowuj konwencje projektu i wykonuj sprawdzenia odpowiednie do zmiany. Oddzielaj wykonane działania od propozycji; jawnie podawaj pominięte sprawdzenia.
- Zasady dotyczące Git i dokumentacji stosuj podczas tworzenia i rozwijania aplikacji. Sama rozmowa, analiza pomysłu lub ocena materiałów nie wymaga aktualizacji dokumentacji ani pytania o commit.
- Przed zmianami sprawdź stan Git, jeśli katalog należy do repozytorium.
- Nie nadpisuj ani nie cofaj wcześniejszych zmian użytkownika bez wyraźnego polecenia. Cofnięcie zmian z bieżącego zadania nie obejmuje wcześniejszej ani niezwiązanej pracy.
- Nie zapisuj sekretów i prywatnych danych w kodzie, dokumentacji, logach ani commitach.

# Przeznaczenie dokumentów projektu

- W nowych aplikacjach stosuj poniższy podział dokumentacji. W istniejących projektach zachowuj przyjęte nazwy i układ; nie twórz ani nie reorganizuj całego zestawu dokumentów przy drobnej zmianie.
- Przy wznawianiu pracy przeczytaj `PROJECT_CONTEXT.md` i `HANDOFF.md` lub ich projektowe odpowiedniki, jeśli istnieją. Pozostałą dokumentację czytaj według potrzeb zadania.

## README.md

- Główna instrukcja obsługi projektu dla człowieka.

README ma zawierać:

- cel projektu;
- wymagania;
- opis struktury folderów;
- instrukcję przygotowania środowiska;
- instrukcję instalacji bibliotek;
- instrukcję konfiguracji i uruchomienia;
- instrukcję uruchomienia testów;
- instrukcję przeniesienia projektu na inny komputer;
- w projektach Python: instrukcję utworzenia `.venv` i informację, że `.venv` nie wolno kopiować.

## PROJECT_CONTEXT.md

- Stały opis projektu: dla kogo powstaje, jaki problem rozwiązuje i czego nie powinien robić.
- Pomaga zachować podstawowe założenia projektu podczas kolejnych rozmów z AI.

PROJECT_CONTEXT ma zawierać:

- cel projektu;
- odbiorców i ich potrzeby;
- problem, który rozwiązujemy;
- główne zastosowania;
- zakres projektu oraz rzeczy pozostające poza zakresem;
- najważniejsze założenia i ograniczenia;
- kryteria sukcesu.

## HANDOFF.md

- Aktualny punkt wznowienia pracy w kolejnej rozmowie z AI.

HANDOFF ma zawierać:

- aktualny cel;
- co zostało wykonane;
- co nie działa lub pozostaje niesprawdzone;
- ważne pliki i ich przeznaczenie;
- następne kroki;
- ostatnie uruchamiane komendy i ich wyniki;
- wyniki istotnych testów;
- stan Git, w tym zmiany niezapisane commitem;
- datę aktualizacji.

## PLANS.md

- Aktualny plan wykonania większego zadania.

PLANS ma zawierać:

- cel i zakres zadania;
- kroki wykonania;
- postęp: co zakończono, co trwa i co pozostało;
- zależności i przeszkody;
- sposób sprawdzenia rezultatu;
- kryteria zakończenia zadania.

## ARCHITECTURE.md

- Mapa techniczna aplikacji: jak zbudowany jest system i jak przepływają przez niego dane.

ARCHITECTURE ma zawierać:

- najważniejsze komponenty i ich odpowiedzialności;
- punkty uruchomienia aplikacji;
- zależności między komponentami;
- przepływ danych;
- integracje z usługami zewnętrznymi;
- miejsca konfiguracji, odczytu i zapisu danych;
- przeznaczenie `data/input/` i `data/output/`, jeśli aplikacja ich używa.

## DECISIONS.md

- Historia ważnych decyzji technicznych, pomagająca zrozumieć przyjęte rozwiązania.

Każda istotna decyzja ma zawierać:

- datę;
- problem lub potrzebę;
- wybrane rozwiązanie;
- uzasadnienie wyboru;
- rozważane alternatywy, jeśli były istotne;
- konsekwencje i ograniczenia;
- informację o zastąpieniu wcześniejszej decyzji, jeśli nastąpiło.

## CLAUDE.md

- Zawiera wyłącznie import `@AGENTS.md`.

## README_SHORT.md

- Minimalistyczny opis odpowiadający na pytanie: „Co robi ta aplikacja?”.
- Ma zawierać 2–4 proste zdania opisujące główne działanie aplikacji i otrzymywany wynik.
- Ma być zrozumiały dla osoby nietechnicznej.
- Szczegóły instalacji, konfiguracji i obsługi pozostają w README.md.
- Aktualizuj go, gdy zmienia się główne działanie aplikacji. Opis musi odpowiadać jej rzeczywistym możliwościom

## Nowa aplikacja

- Sprawdź docelowy katalog. Dla nowej aplikacji zainicjalizuj lokalny Git, jeśli nie ma repozytorium; unikaj przypadkowego zagnieżdżania repozytoriów. Samo opracowywanie materiałów nie jest inicjalizacją aplikacji.
- Nie twórz commita bez zgody. Po zakończeniu zapytaj: „Czy utworzyć pierwszy commit?”

## Iterowanie aplikacji

- Pracuj w istniejącym repozytorium. Nie twórz commita bez zgody i nie dołączaj niezwiązanych zmian. Po zakończeniu zapytaj: „Czy zatwierdzić zmianę commitem, czy wrócić do ostatniego commita?”
- Publikacja repozytorium i wysłanie zmian wymagają osobnego polecenia użytkownika.
- Prowadź dokumentację projektu w `README.md`, `PROJECT_CONTEXT.md`, `HANDOFF.md`, `PLANS.md`, `ARCHITECTURE.md`, `DECISIONS.md` i `README_SHORT.md` lub ich projektowych odpowiednikach, zgodnie z przeznaczeniem każdego pliku.
- Aktualizacja dokumentacji jest częścią zadania — wykonuj ją bez osobnego polecenia, gdy wprowadzone zmiany wpływają na jej treść.
- Aktualizuj tylko potrzebne dokumenty. Utrzymuj je zwięzłe, bez powielania informacji, i opisuj rzeczywisty stan projektu.
- Po zakończeniu istotnego etapu zaktualizuj `HANDOFF.md` lub projektowy dokument o tej funkcji. Nie aktualizuj go po każdym drobnym poleceniu.
