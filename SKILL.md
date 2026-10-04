---
name: nextjs-project-init
description: "Zainicjalizuj nową aplikację Next.js i przygotuj strukturę oraz .gitignore. Używaj przy tworzeniu projektu Next.js, nie przy zwykłym iterowaniu istniejącej aplikacji."
metadata:
  version: "1.0.0"
---

# Praca agentowa nad aplikacjami Next.js

Przygotuj nowy projekt Next.js zgodnie ze standardem użytkownika. Ten skill obejmuje etap inicjalizacji; dalszy zakres pracy wynika ze zlecenia.

## Przygotowanie projektu

- Przeczytaj [Nextjs.md](Nextjs.md) i zastosuj opisany sposób inicjalizacji, strukturę oraz `.gitignore`.
- Ustal katalog docelowy na podstawie zlecenia. Przed uruchomieniem generatora sprawdź jego zawartość i istniejące repozytorium; zachowaj wcześniejsze pliki i unikaj zagnieżdżania repozytoriów.
- Wygeneruj projekt przez `create-next-app` z ustawieniami ze specyfikacji, chyba że użytkownik wskazał inne. Zachowaj wygenerowaną konfigurację, blokadę zależności i instrukcje Next.js.
- Dodaj brakujące pliki i katalogi. Elementy opcjonalne dobierz do projektu; dla małego prototypu zastosuj dopuszczone uproszczenie.
- Korzystaj z opcji `--disable-git`. Po wygenerowaniu zainicjalizuj lokalny Git, jeśli katalog nie należy do repozytorium. Nie twórz commita ani nie publikuj projektu bez polecenia użytkownika.
- Sprawdź, czy lokalne zależności, pliki generowane i prywatne dane są ignorowane. Zachowaj wyjątki dla bezpiecznych wzorów `.env`; prywatne materiały pozostaw poza `public/`.

## Dokumentacja

Opis przeznaczenia i wymaganej zawartości dokumentów `.md` znajduje się w globalnym `AGENTS.md`. Korzystaj z tych zasad, jeśli są dostępne w obowiązujących instrukcjach.

Jeśli brakuje takich opisów, przeczytaj część „Przeznaczenie dokumentów projektu” w dołączonym [Agent.md](Agent.md), do nagłówka „Nowa aplikacja”. To materiał pomocniczy dla osób korzystających ze skilla bez tych globalnych zasad.

Uzupełnij dokumentację stanem wynikającym z utworzonego projektu. Nie instaluj ani nie podmieniaj globalnych instrukcji automatycznie. Projektowy `AGENTS.md` i `CLAUDE.md` przygotuj zgodnie z `Nextjs.md`.

## Zakończenie

Podaj katalog utworzonego projektu, istotne elementy szkieletu i sposób uruchomienia aplikacji. Wskaż niewykonane elementy, jeśli środowisko lub dostęp do narzędzi uniemożliwił ich przygotowanie.
