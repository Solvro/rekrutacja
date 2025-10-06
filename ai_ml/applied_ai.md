# AI/ML - Applied AI - NLP

## Opis zadania 
Celem zadania jest implementacja *Model Context Protocol* (MCP) i stworzenie dla niego narzędzia typu RAG (ang. Retrieval-Augmented Generation), które będzie w stanie odpowiedzieć na pytania dotyczące koktajli i ich składników, a także zasugerować koktajle na podstawie podanych składników lub preferencji smakowych.

## Zbiór danych

Zbiór pochodzi z bazy danych *TheCocktailDB*. Składa się on z listy koktajli oraz składników potrzebnych do ich przyrządzenia. Znajduje się on w folderze `data`. Warto przeprowadzić analizę eksploracyjną zbioru danych.

Protip: W kontekście analizy danych i uczenia maszynowego format `json` nie jest zbyt wygodny. Zaleca się np. skorzystanie z funkcji `pd.read_json()` z biblioteki `pandas`.

## Wymagania
- Stworzenie MCP, na przykład za pomocą biblioteki takiej jak [FastMCP](https://gofastmcp.com/getting-started/welcome)
- Stworzenie narzędzia RAG, które będzie w stanie odpowiedzieć na pytania dotyczące koktajli i ich składników, a także zasugerować koktajle na podstawie podanych składników lub preferencji smakowych. Można tutaj skorzystać z bibliotek takich jak [LangChain](https://python.langchain.com/docs/get_started/introduction.html) lub [LlamaIndex](https://gpt-index.readthedocs.io/en/latest/index.html)
- Dobra dokumentacja kodu i prezentacja przygotowanej aplikacji
- Plik `README.md` z instrukcją uruchomienia narzędzia
- Mile widziana będzie integracja z narzędziem takim jak *LMStudio* lub *Claude Desktop* w celu łatwego testowania aplikacji

Standardem jest Python, ale jeśli wybierzesz inny język, to nie będzie to wpływało na ocenę zadania (o ile Twoje rozwiązanie spełni powyższe wymagania).

## Forma oddania
Link do repozytorium ze skryptami, Jupyter notebookami i plikiem `README.md` opisującym jak odpalić projekt.

**Autorzy zadania**: Jakub Gilewicz i Daniel Borkowski.

**Masz pytanie? Napisz do nas kn.solvro@pwr.edu.pl lub otwórz issue na repozytorium.**