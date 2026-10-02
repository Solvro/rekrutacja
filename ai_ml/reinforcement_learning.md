# AI RL: Sterowanie sygnalizacją świetlną
Twoim zadaniem będzie napisanie modelu, którego zadaniem będzie sterowanie sygnalizacją świetlną na skrzyżowaniach w taki sposób, aby jak najszybciej  opróżniać skrzyżowania i tym samym minimalizować częstotliwość oraz wielkość korków na drodze.

Do wytrenowania tego modelu, wykorzystaj uczenie ze wzmocnieniem, a środowiskiem do trenowania niech będzie [SUMO](https://github.com/eclipse-sumo/sumo) (jeżeli znasz i umiesz obsługiwać inne też będzie ok, ale SUMO jest wystarczające) 
Nie jest to problem wizyjny, więc informacje o samochodach czekających na skrzyżowaniu możesz pobierać prosto ze środowiska, do ciebie należy wybranie odpowiedniego algorytmu, stworzenie przykładowej sieci skrzyżowań, zbudowanie całego pipeline'u i przeprowadzenie treningu

Ograniczenia: nie używaj gotowych Rl'owych algorytmów, zbuduj je sam przy użyciu torchowych sieci neuronowych
Wynikiem końcowym powinien być wytrenowany model, który radzi sobie zarówno przy niskim jak i wysokim ruchu drogowym, zalecane jest zrobienie wizualizacji działania modelu a nie same metryki
