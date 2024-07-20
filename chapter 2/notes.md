# Lista kontrolna projektu uczenia maszynowego

Poniższa lista stanowi pomoc podczas tworzenia projektów uczenia maszynowego. Na proces ten składa  się osiem etapów:
1. Określenie problemu i przeanalizowanie go w szerszej perspektywie.
2. Pozyskanie danych.
3. Analiza danych w celu wykrycia dodatkowych informacji.
4. Przygotowanie danych w sposób uwidaczniający wzorce wykorzystywane przez algorytmy uczenia maszynowego.
5. Sprawdzenie wielu modeli i stworzenie krótkiej listy najwydajniejszych z nich.
6. Dostrojenie modeli i połączenie ich w zespoły uzyskujące jeszcze lepsze wyniki.
7. Zaprezentowanie rozwiązania.
8. Uruchomienie, monitorowanie i utrzymywanie systemu.

# RMSE

Średni błąd kwadratowy (RMSE) to miara odległości pomiędzy prognozami modelu a rzeczywistymi wartościami. Im niższa wartość RMSE, tym lepszy model.

Używany głównie do zadań regresji, RMSE jest miarą odchylenia standardowego reszt (błędów) modelu.

# Wyrażenia lambda

Wyrażenia lambda to krótkie funkcje anonimowe zdefiniowane za pomocą słowa kluczowego lambda. Mogą przyjmować dowolną liczbę argumentów, ale mogą zawierać tylko jedno wyrażenie.

Przykłady:
```python
add = lambda x, y: x + y
add(5, 3)
```
```python
(lambda x, y: x + y)(5, 3)
```

# Wartości Haszy

## Co to jest wartość hasza?

Wartość hasza, w kontekście podanego kodu, jest generowana przez funkcję `crc32`, która jest funkcją skrótu. Funkcje skrótu biorą dane wejściowe i przekształcają je w unikalną wartość wyjściową o stałej długości, znaną jako wartość hasza.

W przypadku funkcji `is_id_in_test_set`, wartość hasza jest obliczana dla `identifier`, który jest unikalnym identyfikatorem dla każdego rekordu w zestawie danych. 

```python
crc32(np.int64(identifier))
```

## Przedział wartości hasza

Wartości skrótu CRC32, które są obliczane w funkcji `is_id_in_test_set`, są 32-bitowymi liczbami całkowitymi. To oznacza, że mogą one przyjmować wartości od 0 do `2**32 - 1`, czyli od 0 do 4294967295.

```python
def is_id_in_test_set(identifier, test_ratio):
    return crc32(np.int64(identifier)) < test_ratio * 2**32
```

## Przyznawanie wartości hasza

Wartości skrótu CRC32 są generowane na podstawie danych wejściowych, w tym przypadku jest to `identifier`. CRC32 to algorytm, który bierze dane wejściowe i generuje z nich 32-bitową liczbę. Algorytm ten jest deterministyczny, co oznacza, że dla tych samych danych wejściowych zawsze generuje tę samą wartość skrótu.

```python
crc32(np.int64(identifier))
```

## Zależność wartości hasza od danych wejściowych

Wartość skrótu CRC32 dla danego indeksu nie jest równa temu indeksowi. Algorytm CRC32 generuje 32-bitową liczbę na podstawie danych wejściowych, ale ta liczba nie jest bezpośrednio związana z wartością danych wejściowych. Dla różnych wartości wejściowych, CRC32 zwróci różne wartości skrótu, ale nie ma prostej zależności między wartością wejściową a wartością skrótu. 

Sposobem na zapewnienie tej samej wartości hasza dla tego samego wiersza w przypadku zmiany kolejności danych jest wyznaczenie jej na podstawie np. szerokości i długości geograficznej, które są niezmienne

```python
housing_with_id['id'] = housing['longitude'] * 1000 + housing['latitude']
train_set, test_set = split_data_with_id_hash(housing_with_id, 0.2, 'id')
```

## Determinizm wartości hasza

Algorytm CRC32 jest deterministyczny, co oznacza, że dla tych samych danych wejściowych zawsze generuje tę samą wartość skrótu. Więc jeśli podasz do funkcji `crc32` liczbę 1, zawsze otrzymasz tę samą wartość skrótu.

```python
from zlib import crc32
print(crc32(np.int64(1)))
```



