# Nadzorowanie uczenia

### Uczenie nadzorowane

- Model jest uczony na podstawie danych, które zawierają etykiety
- Model przewiduje etykiety dla nowych danych
- Przykłady:
  - Klasyfikacja
  - Regresja

### Uczenie nienadzorowane

- Model jest uczony na podstawie danych, które nie zawierają etykiet
- Model znajduje wzorce w danych
- Przykłady:
  - Klastrowanie
  - Wizualizacja
  - Redukcja wymiarów

### Uczenie półnadzorowane

Uczenie półnadzorowane to technika uczenia maszynowego, która radzi sobie z danymi częściowo oznakowanymi. W praktyce, oznaczanie danych etykietami jest czasochłonne i kosztowne, dlatego często mamy do czynienia z danymi, które składają się z większości nieoznakowanych i tylko odrobiny oznakowanych przykładów. 

Dobrym przykładem zastosowania tego typu metod są usługi przechowywania obrazów, które rozpoznają osoby na zdjęciach. Na początku jest to proces nienadzorowany, ale po dodaniu etykiet do niektórych osób, staje się to procesem półnadzorowanym.

Większość algorytmów półnadzorowanych stanowi kombinację algorytmów uczenia nadzorowanego i nienadzorowanego. Na przykład, algorytm analizy skupień może posłużyć do grupowania podobnych przykładów, a następnie każdy nieoznaczony przykład może być oznakowany za pomocą najczęściej występującej etykiety w skupieniu. Po oznakowaniu całego zestawu danych, można skorzystać z nadzorowanego uczenia maszynowego.

- Model jest uczony na podstawie danych, które zawierają częściowo etykiety
- Przykłady:
  - Klastrowanie z częściowymi etykietami
  - Wizualizacja z częściowymi etykietami

### Uczenie samonadzorowane

Uczenie samonadzorowane to technika uczenia maszynowego, która generuje oznakowane dane z nieoznakowanych. Przykładowo, model może być nauczony na obrazach, gdzie małe obszary są losowo maskowane, a zadaniem modelu jest odtworzenie pierwotnego obrazu. Uzyskany model może być użyteczny do różnych zadań, ale często jest dalej dostosowywany do konkretnego zadania. Przenoszenie wiedzy między zadaniami nazywane jest uczeniem transferowym. Uczenie samonadzorowane jest czasem uważane za część uczenia nienadzorowanego, ale ze względu na użycie wygenerowanych etykiet w trakcie uczenia, jest mu bliżej do uczenia nadzorowanego.

- Model jest uczony na podstawie danych, które nie zawierają etykiet
- Model znajduje wzorce w danych
- Przykłady:
  - Generowanie danych
  - Wizualizacja
  - Redukcja wymiarów

### Uczenie ze wzmocnieniem

Uczenie przez wzmacnianie to technika uczenia maszynowego, w której system uczący, zwany agentem, obserwuje środowisko, wykonuje czynności i odbiera nagrody lub kary. Agent musi samodzielnie nauczyć się najlepszej strategii, nazywanej polityką, aby uzyskać jak największą nagrodę. Polityka definiuje, jakie działanie agent powinien wybrać w danej sytuacji.

Przykładem zastosowania uczenia przez wzmacnianie są modele robotów uczące się chodzić. Inny znany przykład to program AlphaGo firmy DeepMind, który był trenowany przez wzmacnianie i pokonał mistrza świata w grę Go. AlphaGo analizował miliony rozgrywek i rozgrywał wiele partii przeciwko sobie, aby zdefiniować politykę gwarantującą zwycięstwo. Warto zauważyć, że algorytmy uczące były wyłączone podczas partii z ludzkim przeciwnikiem; AlphaGo korzystał jedynie z wyuczonej polityki. Jest to przykład tzw. uczenia offline.

# Uczenie wsadowe i przyrostowe

### Uczenie wsadowe

Uczenie wsadowe to technika uczenia maszynowego, która wymaga wszystkich dostępnych danych do trenowania modelu. Jest to proces czasochłonny i zasobożerny, często przeprowadzany offline. Skuteczność modelu może maleć z czasem, ponieważ dane ewoluują, a model pozostaje niezmienny. Aby uwzględnić nowe dane, musisz wytrenować nową wersję systemu od podstaw, co może być kosztowne i trudne do zrealizowania przy dużych zbiorach danych.

### Uczenie przyrostowe

Uczenie przyrostowe to technika, gdzie system uczy się na bieżąco z nowych danych. Jest szybkie, kosztowo-efektywne i dobrze radzi sobie z dużymi zbiorami danych. Wymaga jednak uważnego monitorowania, aby zapewnić jakość danych i uniknąć szybkiego spadku wydajności.




# Uczenie z przykładów i z modelu

### Uczenie z przykładów

Uczenie z przykładów to technika, gdzie system uczy się na podstawie konkretnych przykładów i porównuje nowe przypadki do nauczonych przykładów, używając miary podobieństwa.

### Uczenie z modelu

Uczenie z modelu to technika uczenia maszynowego, która polega na tworzeniu modelu na podstawie danych uczących i używaniu tego modelu do przewidywania wyników dla nowych danych.

# Ćwiczenia

1. **Podaj definicję uczenia maszynowego.**

- Dziedzina nauki (i sztuki) programowania komputerów w sposób umożliwiający im uczenie się z danych.

2. **Wymień cztery rodzaje zastosowań, w których najlepiej sobie radzi proces uczenia maszynowego.**

- Analizowanie obrazów produktów znajdujących się na taśmie produkcyjnej w celu ich automatycznego klasyfikowania
- Automatyczne oznaczanie obraźliwych komentarzy na forach dyskusyjnych
- Wykrywanie oszustw popełnionych z wykorzystaniem kart kredytowych
- Segmentowanie klientów na podstawie dokonywanych przez nich zakupów, co pozwala wyznaczać odmienne strategie dla poszczególnych segmentów

3. **Czym jest oznakowany zbiór danych uczących?**

- Zbiór danych uczących, który zawiera etykiety.

4. **Jakie są dwa najczęstsze zastosowania uczenia nadzorowanego?**

- Klasyfikacja
- Regresja

5. **Wymień cztery najpowszechniejsze zastosowania uczenia nienadzorowanego.**

- Analiza skupień
- Wizualizacja
- Redukcja wymiarów
- Wykrywanie anomalii

6. **Jakiego rodzaju algorytmu użyłbyś w robocie przeznaczonym do poruszania się po nieznanym terenie?**

- Algorytm uczenia ze wzmocnieniem (system uczy się na podstawie nagród i kar)

7. **Jakiego rodzaju algorytmu uczenia maszynowego użyłbyś do rozdzielenia klientów na kilka różnych grup?**

- Algorytm uczenia nienadzorowanego (analiza skupień)

8. **Czy problem wykrywania spamu stanowi część mechanizmu uczenia nadzorowanego, czy nienadzorowanego?**

- Nadzorowanego, ponieważ system uczy się na podstawie oznakowanych danych.

9. **Czym jest system uczenia przyrostowego?**

- System jest trenowany na bieżąco poprzez sekwencyjne dostarczanie danych, które mogą być pojedyncze lub przyjmować postać tzw.  minipakietów/minigrup (ang. mini-batches), czyli niewielkich zbiorów.

10. **Czym jest uczenie pozakorowe?**

- Uczenie pozakorowe to technika uczenia maszynowego, która polega na tworzeniu modelu na podstawie danych uczących i używaniu tego modelu do przewidywania wyników dla nowych danych.

11. **W jakim algorytmie jest wymagana miara podobieństwa do uzyskiwania prognoz?**

- Uczenie z przykładów

12. **Wyjaśnij różnicę pomiędzy parametrem a hiperparametrem modelu.**

- Parametr to wartość, która jest szacowana przez model na podstawie danych uczących. Hiperparametr to wartość, która jest ustawiana przed trenowaniem modelu i nie jest zmieniana w trakcie trenowania.

13. **Czego poszukują algorytmy uczenia z modelu? Z jakiej strategii najczęściej korzystają? W jaki sposób przeprowadzają prognozy?**

- Algorytmy uczenia z modelu poszukują wzorców w danych uczących i tworzą model na ich podstawie.
- Najczęściej korzystają z strategii minimalizacji błędu, czyli szukają modelu, który najlepiej pasuje do danych uczących. 
- Aby przeprowadzić prognozy, algorytmy uczenia z modelu korzystają z modelu, który wcześniej stworzyły.

14. **Wymień cztery główne problemy związane z uczeniem maszynowym.**

- Niedobór danych uczących
- Niereprezentatywne dane uczące, nieistotne cechy, dane słabej jakości
- Przetrenowanie danych uczących
- Niedotrenowanie danych uczących

15. **Z czym mamy do czynienia, jeżeli model sprawuje się znakomicie wobec danych uczących, ale nie radzi sobie z uogólnianiem wobec nowych próbek? Wymień trzy możliwe rozwiązania.**

- Mamy do czynienia z przetrenowaniem modelu.
- Możliwe rozwiązania:
  - Uproszczenie modelu
  - Zbieranie większej ilości danych uczących
  - Redukcja szumu w danych uczących