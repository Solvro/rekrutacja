# Mobile
Zadanie rekrutacyjne do sekcji aplikacji mobilnych Koła Naukowego Solvro. 

## Termin wykonania zadania:
<!-- Dodaj termin wykonania zadania -->

## Opis projektu
Aplikacja mobilna wyświetlająca listę drinków wraz ze składnikami, zdjęciami oraz innymi szczegółami. Umożliwia przeglądanie drinków, ich filtrowanie oraz sortowanie.

## API
- Dokumentacja API, z którego polecamy korzystać jest dostępna [tutaj](https://cocktails.solvro.pl/).

## MVP (Minimum Viable Product) - Must have
- Wyświetlanie listy koktajli (zdjęcie, tytuł).
- Wyświetlanie szczegółów wybranego drinka (składniki i inne dane). 
- Wyszukiwanie drinków na liście (conajmniej po nazwie). 


## Wymagania
- Aplikacja musi korzystać z naszego [Coctail API](https://cocktails.solvro.pl/) lub z innego o zbliżonych możliwościach
- Kod aplikacji musi być czytelny i dobrze podzielony na komponenty/widgety/warstwy.
- Responsywność i dostosowanie do różnych urządzeń (w zakresie urządzeń mobilnych + tablety dobrze widziane).
- Funkcjonalny i intuicyjny design. Nie musi być ekstremalnie wystylizowany :-) 
- Korzystanie z gotowych komponentów lub bibliotek z komponentami jest dopuszczalne i mile widziane.
- Dołącz dobrze napisane README z krótkim opisem technologii, funkcji aplikacji oraz kilkoma screenshotami. 

## Technologie
- **Flutter** (rekomendowane)
- **Kotlin**, **Swift**, **Kotlin Multiplatform** (alternatywy)

Do wykonania zadania możesz wykorzystać dowolnie wybrane biblioteki i paczki. 

**DISCLAIMER:** większość naszych mobilnych projektów jest we Flutterze, ale zadanie można wykonać też w natywnych technologiach, które są bardzo dobrym backgroundem do pracy z Flutterem. 

## Nice to have (opcjonalne funkcje)
_Aby zbodyć "dodatkowe punkty" możesz wykonać dowolnie wybrane opcjonalne funckjonalności z poniższej listy. Pamiętaj, żeby je wypisać w README projektu._

- Filtrowanie koktajli.
- Sortowanie wyników.
- Użyj do tego dowolnie wybranych pól, które udostępnia API i uważasz je za przydatne dla użytkownika.
- Paginacja w wersji `Infinite Scroll`
- Debouncing zapytań przy wyszukiwaniu 
- Zadbaj o podstawy dla prostego wsparcia wielu języków (np. polski, angielski). Nie musisz faktycznie dodawać wielu tłumaczeń. 
- Cache danych dla mniejszego obciążenia serwera i zwiększenia wydajności w słabych warunkach internetowych. W dowolnej funkcjonalnej formie - nie musisz wymyślać zaawansowanych strategii inwalidacji cache'u.
- Mechanizm ulubionych - oznaczanie (serduszkowanie, lajkowanie, itd.) poszczególnych pozycji z zapisem stanu w "local storage" 


**Masz pytanie? Napisz do nas kn.solvro@pwr.edu.pl lub otwórz issue na repozytorium.**


Pull Requesty z propozycją zmian treści zadania również mile widziane.
