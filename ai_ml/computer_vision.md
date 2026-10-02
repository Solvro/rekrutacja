# Computer Vision — od wykresu do danych

## Twoje zadanie

Napisz program, który przyjmuje **obraz pojedynczego wykresu** i zapisuje odczytane punkty `(x, y)` do CSV lub JSON. Przygotuj również wizualizację pozwalającą porównać wynik z obrazem wejściowym.

W podstawowej wersji skup się na wykresach z **jedną serią, widocznymi markerami punktów i liniowymi osiami liczbowymi**. Mogą to być punkty połączone linią. Opisz, jakie obrazy obsługuje Twoje rozwiązanie i gdzie przestaje działać.

Program powinien:

1. Zlokalizować punkty na obrazie i oddzielić je od osi, siatki oraz tekstu.
2. Przeliczyć położenie punktów w pikselach na wartości na osiach.
3. Zapisać wynik i pokazać wykryte punkty na oryginalnym obrazie lub odtworzonym wykresie.

Żeby ograniczyć zakres, możesz ręcznie wskazać obszar wykresu i podać kalibrację: położenia oraz wartości dwóch znaczników podziałki na każdej osi. Zapisz te informacje w konfiguracji i opisz udział pracy ręcznej. **Współrzędne szukanych punktów muszą pochodzić z analizy obrazu.** Automatyczne znajdowanie osi i odczytywanie podziałki przez OCR to rozszerzenie.

## Dane

Proponujemy [PlotQA](https://github.com/NiteshMethani/PlotQA). [Dokumentacja datasetu](https://github.com/NiteshMethani/PlotQA/blob/master/PlotQA_Dataset.md) zawiera linki do obrazów i adnotacji. Adnotacje obejmują m.in. wartości `x` i `y` serii, a zbiór uwzględnia wykresy typu `dot_line`.

Wybierz niewielki podzbiór pasujący do Twoich założeń, np. **30 obrazów: 10 do opracowania rozwiązania i 20 do końcowej oceny**. Zapisz identyfikatory, oryginalny podział zbioru i kryteria wyboru. Wybór ustal przed oceną, a w wynikach uwzględnij również nieudane przypadki. Pliki z pytaniami i odpowiedziami nie są potrzebne.

Możesz użyć innego zbioru z wartościami referencyjnymi lub wygenerować mały zestaw w Matplotlib, zapisując obrazy i odpowiadające im dane. Jeśli wybierzesz wygenerowanie własnego zestawu weź uwagę, że powinieneś: zróżnicować kolory, zakresy osi, liczbę punktów i obecność siatki; przykłady testowe powinny zawierać nowe dane. Podaj sposób odtworzenia zbioru. Wyniki na własnych obrazach syntetycznych nie dowodzą jeszcze skuteczności na wykresach z jakichś publikacji, uwzględnij to we wnioskach.

## Jak sprawdzić jakość

Zacznij od poniższych miar. Wyjaśnij, jak je liczysz i co mówią o Twoim rozwiązaniu.

- **Precision, recall i F1 wykrywania punktów.** Dopasuj przewidywane punkty do referencyjnych jeden do jednego. Jako początkową tolerancję możesz przyjąć 2% rozpiętości każdej osi: para jest poprawna, jeśli oba błędy mieszczą się w tolerancji. Każdy punkt może należeć najwyżej do jednej pary; dodatkowe i pominięte punkty muszą pogarszać wynik. Podaj sposób dopasowania.
- **Błąd współrzędnych.** Dla dopasowanych par policz MAE osobno dla `x` i `y`, dzieląc błędy przez rozpiętość odpowiedniej osi. Dzięki temu porównasz wykresy o różnych skalach. Raportuj ten wynik razem z F1 i liczbą dopasowań — mały błąd kilku wykrytych punktów nie oznacza odzyskania całej serii. Gdy nie ma dopasowań, błąd jest nieokreślony, a nie zerowy.

Pokaż co najmniej kilka sukcesów i porażek. Czy największy problem stanowią markery, siatka, rozdzielczość, czy przeliczanie współrzędnych? Co zmienił(a)byś w kolejnym podejściu?

## Jeśli chcesz pójść dalej

Wybierz interesujący Cię kierunek, nie trzeba realizować wszystkich:

- Automatyczna kalibracja osi z OCR; dodatkowo CER, czyli odsetek błędów znakowych, dla odczytywanych etykiet.
- Kilka serii, przypisanie punktów do legendy lub osie logarytmiczne.
- Odporność na mniejszą rozdzielczość, kompresję i zmianę stylu wykresu.
- Porównanie dwóch metod albo analiza wpływu jednego etapu pipeline'u na wynik.
- Odtwarzanie linii bez markerów. Wyjaśnij wtedy różnicę między próbkowaniem przebiegu krzywej a odzyskaniem oryginalnych punktów: wiele zestawów punktów może dać ten sam obraz linii. Dobierz metrykę oceniającą przebieg, zamiast zakładać znajomość oryginalnego próbkowania.

Zachęcamy do znalezienia dodatkowej metryki lub publikacji i wyjaśnienia, czego można się dzięki niej dowiedzieć. Trafna analiza ograniczeń jest równie wartościowa jak bardziej rozbudowany algorytm.
