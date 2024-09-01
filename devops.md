# Devops


### Opis zadania
Twoim zadaniem jest produkcyjny deploy aplikacji na domenę. Aplikacją jest REST API koktajli,a twoim zadaniem jest zaprojektowanie i wdrożenie rozwiązania, tak aby API było publicznie dostępne. 

### Aplikacja
Przygotowaliśmy REST API w którym możemy odczytywać koktajle. Repozytorium jest dostępne tu: https://github.com/Solvro/backend-cocktail-api, a przykładowy deploy tu: https://cocktails.solvro.pl/. Aplikację da się zdeployować na kilka sposobów, bez zmian w kodzie. Jeśli mimo to chcesz wykonać jakieś zmiany zapraszamy do forkowania. 

### Server
Możesz użyć dowolnego rozwiązania chmurowego lub czystego VPS. W przypadku, gdy nie masz dostępu do żadnego serwera skontaktuj się z nami, a damy ci tymczasowy dostęp do skrawka naszej infrastruktury. 

### Domena
Aplikacja może być dostępna pod dowolną domeną. Jeśli nie masz dostępu do własnej domeny, skontaktuj się z nami, a wydzielimy ci subdomenę w rekrutacja.solvro.pl

### Rezultat
Jako efekt twojej pracy oczekujemy dokumentu tekstowego (najlepiej link do google docs) w którym opiszesz co wykonałeś, aby tą aplikację zdeployować i oczywiście link do domeny końcowej. 

### Nice to have
- automatic deployment
- skalowanie horyzontalne
- cache
- wspólny wolumen dla folderu public/images, gdzie po uruchomieniu synchronizacji przechowywane są pliki
- cron pełnej synchronizacji koktajki i składników
- wskazówki co można jeszcze zamplementować w przyszłości pod względem devopsowym

**W razie problemów zapraszamy do kontaktu i powodzenia!**