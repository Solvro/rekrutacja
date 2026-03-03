# Zadanie rekrutacyjne - research
# AI/ML - Research - Computer Vision

## Cel zadania
Twoim zadaniem jest wytrenowanie sieci neuronowej, która będzie klasyfikowała proste rysunki wykonane ręcznie i ich cyfrowe odpowiedniki. To zadanie pozwoli nam zobaczyć, jak radzisz sobie z przetwarzaniem obrazów, trenowaniem modeli oraz analizą danych - pokaż nam co umiesz!

## Dataset
Wykorzystaj dataset [Simple hand-drawn and digitized images](https://www.kaggle.com/datasets/gergvincze/simple-hand-drawn-and-digitized-images/data) do klasyfikacji. Znajduje się tam 10 klas. Każda klasa zawiera trzy rodzaje obrazów:
- obrazy rysowane ręcznie i fotografowane
- obrazy rysowane ręcznie i skanowane
- obrazy tworzone za pomocą pieczątek i fotografowane

## Wymagania

- Pamiętaj, żeby dobrze **opisać proces i podjęte decyzje**. Idealne do tego będą komórki tekstowe (markdownowe) w Jupyter notebook. Będzie to bardzo istotna część oceny.
- Pisz **czysty i zwięzły kod**, korzystaj z dobrych praktyk programowania.
- Zadbaj o **reprodukowalność** kodu, tak, żeby np. sprawdzający mógł wszystko uruchomić. W tym celu np. zamieść plik `requirements.txt`.
- **Nie dopuść do wycieku danych**, w szczególności dokonaj podziału i wyłącz zbiór testowy z analizy danych oraz trenowania modelu.
- Zrealizuj każdy z czterech poniższych **etapów**. 


### 1. Eksploracja danych
Załaduj i przeanalizuj dataset, przedstaw statystyki i właściwości zbioru np. liczba klas, rozkłady wartości danych i przykładowe dane, a także zidentyfikuj potencjalne problemy typu niezbalansowanie klas czy jakość obrazów.

### 2. Preprocessing
Odpowiednio przygotuj obrazy do treningu, np. przeprowadź normalizację lub standaryzację danych. Wprowadź augmentację danych.

### 3. Model
Wybierz co najmniej jeden pretrenowany model (np. ResNet, MobileNet) i dostosuj jego architekturę do zadania klasyfikacji. Porównaj dwa podejścia: fine-tuning z zamrożonymi warstawami ekstrakcji cech (frozen backbone) oraz pełne trenowanie wszystkich warstw (full fine-tuning). Postaw sobie pytanie badawcze: *które podejście lepiej sprawdza się jako metoda ekstrakcji cech w klasyfikacji dla tego zbioru danych?* i odpowiedz na nie.

### 4. Ewaluacja
Oceń skuteczność modelu poprzez podanie wyników (wybranych metryk klasyfikacji, ich wybór uzasadnij). Przeanalizuj również błędy (modelu jak i swoje w trakcie implementacji), wskaż miejsca do poprawy. Podsumuj badanie i przedstaw wnioski.

#### Dodatkowo
Jeśli masz czas i ochotę, możesz przeprowadzić dodatkowo:
- porównanie kilku różnych architektur
- analizę osiągów modelu po wprowadzeniu różnych augmentacji danych
- analizę, jak model radzi sobie z rysunkami odręcznymi vs cyfrowymi
- wizualizację tego, co model "widzi" - activation maps, GradCAM lub inne XAI
- optymalizację hiperparametrów (na zbiorze walidacyjnym!)
- implementację wybranych narzędzi wspierających pracę z danymi i modelami ML, np. DVC albo MLflow 
- wdrożenie modelu - prosta aplikacja webowa czy API

Wykonanie kilku wybranych punktów z powyższej listy wpłynie pozytywnie na ocenę zadania :)

## Forma oddania
Link do repozytorium ze skryptami, Jupyter notebookami i plikiem `README.md` opisującym jak odpalić repozytorium.

## Sugerowane techologie :
- język programowania Python 
- narzędzie Jupyter Notebook
- frameworki deep learningu PyTorch lub Lightning
- biblioteki `scikit-learn`, `pandas`, `numpy`, `matplotlib`, `seaborn`

Powyższy zestaw to raczej standard, używamy go też w kole. Jeśli jednak czujesz się lepiej w innych technologiach to śmiało z nich korzystaj, nie wpłynie to na ocenę zadania.

**Autorzy zadania**: Julia Farganus, Karolina Nowacka i Daniel Borkowski.

**Masz pytanie? Napisz do nas kn.solvro@pwr.edu.pl lub otwórz issue na repozytorium.**