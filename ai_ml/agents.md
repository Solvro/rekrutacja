# RAG i agenci — asystent przeglądu literatury

Zaczynasz poznawać nowy temat w machine learningu. Publikacji jest dużo, a sam abstrakt nie zawsze pozwala ocenić, czy dana praca będzie przydatna. Recenzje mogą uzupełnić ten obraz o pytania dotyczące metod, eksperymentów i ograniczeń.

Twoim zadaniem jest przygotowanie **asystenta przeglądu literatury**, który pomaga znaleźć prace związane z pytaniem użytkownika i zestawia informacje od autorów z uwagami recenzentów. Każda odpowiedź powinna pozwalać dotrzeć do materiałów, na których się opiera.

## Twoje zadanie

Zbuduj system RAG, czyli rozwiązanie, które najpierw wyszukuje materiały, a następnie przekazuje je do modelu jako kontekst odpowiedzi. W tym zadaniu materiałami będą publikacje i ich recenzje pobrane przez API OpenReview.

### Pobranie i przechowanie danych

Wybierz **dwie konferencje**, opcjonalnie trzecią. Na początek proponujemy ICLR 2024 (`ICLR.cc/2024/Conference`) i NeurIPS 2024 (`NeurIPS.cc/2024/Conference`). ICLR udostępnia publiczne recenzje, a polityka NeurIPS 2024 przewiduje publikację recenzji zaakceptowanych prac. Dostępność zależy więc od konferencji i statusu publikacji. Zobacz [zasady ICLR](https://iclr.cc/Conferences/2024/AuthorGuide) i [zasady NeurIPS](https://neurips.cc/Conferences/2024/ReviewerGuidelines).

Pobierz np. **po 30–50 publikacji z publicznymi recenzjami z każdej konferencji**. Możesz ograniczyć się do wspólnej tematyki. Zapisz sposób wyboru próby, identyfikatory i datę pobrania. Duża liczba dokumentów nie jest celem zadania.

Dla publikacji wystarczą tytuł, abstrakt, konferencja, rok, identyfikator i link. Dla recenzji zachowaj treść, identyfikator, powiązanie z publikacją oraz dostępne oceny i nazwy pól. Pełne PDF-y i ich parsowanie są opcjonalne.

Skorzystaj z [dokumentacji pobierania submissions i reviews](https://docs.openreview.net/how-to-guides/data-retrieval-and-modification/how-to-get-all-notes-for-submissions-reviews-rebuttals-etc). Rozróżniaj oficjalne recenzje, komentarze autorów i decyzje; nie każda odpowiedź w wątku jest recenzją. Sprawdź schematy wybranych konferencji i nie zakładaj, że nazwy pól lub skale ocen są identyczne. Zapisuj pobrane dane lokalnie, aby kolejne eksperymenty nie wymagały ponownego pobierania.

**Samodzielnie wybierz sposób przechowywania i wyszukiwania danych.** Baza wektorowa, grafowa, relacyjna z osobnym indeksem albo rozwiązanie hybrydowe są dopuszczalne. Uzasadnij wybór, zachowaj relację publikacja–recenzja oraz możliwość filtrowania po konferencji. Lokalna baza i indeks zapisany na dysku wystarczą.

### Wyszukiwanie i odpowiedzi

Użytkownik podaje temat lub pytanie badawcze, a opcjonalnie zawęża wyniki do konferencji. System wyszukuje pasujące fragmenty i tworzy odpowiedź, wskazując konkretne recenzje lub publikacje, na których się opiera. Zachowaj też sam kontekst przekazany do modelu, żeby dało się sprawdzić, skąd wzięła się odpowiedź.

Przykładowe pytania:

- Chcę poznać metody ograniczania kosztu inferencji modeli językowych. Które prace z bazy warto przeczytać i dlaczego?
- Jakie ograniczenia eksperymentów wskazują recenzenci znalezionych prac?
- Co autorzy dwóch znalezionych publikacji deklarują jako główną zaletę metody, a jakie zastrzeżenia zgłaszają recenzenci?

Dostosuj przykłady do tematyki pobranego zbioru. Rozróżniaj **deklaracje autorów i opinie recenzentów** oraz zachowuj ich powiązanie z właściwą publikacją. Recenzja nie jest nieomylnym opisem pracy. Jeśli źródła się różnią, pokaż tę różnicę; jeśli brakuje danych, zaznacz brak podstaw do odpowiedzi. Przy pracy na samych abstraktach nie przypisuj publikacjom szczegółów, których nie ma w zgromadzonych materiałach.

Możesz użyć modelu lokalnego lub dostępnego Ci API. Oddziel wyszukiwanie od generowania. **Jeśli nie masz zasobów do uruchomienia LLM-a, oddaj działające pobieranie, bazę, retrieval i budowanie końcowego promptu z kontekstem oraz źródłami.** To dopuszczalny wariant podstawowy; jasno oznacz brak generacji i nie raportuj jej jakości na podstawie ręcznie napisanych odpowiedzi.

## Jak sprawdzić jakość

Przygotuj mały zestaw ewaluacyjny, np. **10 pytań z odpowiedzią w bazie i 2 pytania bez wystarczających danych**. Dla tych pierwszych ręcznie wskaż co najmniej jedno trafne źródło i krótko uzasadnij jego trafność. Zapisz pytania i oznaczenia przed końcowym porównaniem. Materiały źródłowe pozostają w indeksie, ale wzorcowych odpowiedzi nie dodawaj jako dokumentów do wyszukiwania.

Proponujemy na początek:

- **Hit@5** — odsetek pytań z odpowiedzią, dla których w pierwszych pięciu wynikach znalazło się przynajmniej jedno oznaczone trafne źródło. Określ, czy oceniasz recenzje, czy fragmenty, i nie licz kilku fragmentów tej samej recenzji jako niezależnych źródeł. To wynik względem Twoich oznaczeń, które mogą nie obejmować wszystkich trafnych materiałów.
- **Zgodność odpowiedzi ze źródłami** — dla wygenerowanych odpowiedzi ręcznie sprawdź, ile sprawdzalnych twierdzeń potwierdzają przywołane fragmenty. Podaj licznik, mianownik i przykłady błędów. Samo istnienie linku nie oznacza, że źródło potwierdza twierdzenie. Osobno opisz zachowanie na pytaniach bez danych.

Porównaj wybrany retrieval z prostym punktem odniesienia, np. TF-IDF albo BM25, na tych samych danych i pytaniach. Jeśli taka metoda jest Twoim rozwiązaniem, porównaj ją z prostym wyszukiwaniem po wspólnych słowach. Opisz przynajmniej jeden przypadek, w którym wynik był nietrafny, i możliwą przyczynę.

## Jeśli chcesz pójść dalej

Wybierz jeden kierunek, który Cię interesuje:

- **Agent korzystający z narzędzi:** na podstawie wyników decyduje, czy doprecyzować zapytanie, pobrać dodatkowe recenzje czy zakończyć odpowiedź. Zapisz przebieg i ustaw limit kroków. Sprawdź, czy poprawia wyniki względem pojedynczego wyszukania.
- Wyszukiwanie hybrydowe, reranking albo porównanie sposobów dzielenia tekstu na fragmenty.
- Metryki takie jak MRR lub nDCG; Recall@k ma sens, jeśli przygotujesz dostatecznie kompletne oznaczenia trafnych źródeł. Uzasadnij, co mierzą ponad Hit@5.
- Sprawdzenie, czy dołączenie recenzji daje bardziej przydatne odpowiedzi niż korzystanie wyłącznie z abstraktów.
- Analiza wpływu doboru próby i dostępności recenzji na różnorodność polecanych publikacji.

Własna metryka, dobrze dobrana publikacja lub rzetelnie opisany nieudany eksperyment będą mile widziane. Nie wymagamy wieloagentowej architektury ani konkretnego frameworka (lecz głównie używamy u nas langgraph bądź pydantic-ai).
