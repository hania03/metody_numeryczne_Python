# metody_numeryczne_Python
# Laboratorium 1
## Opis projektu:
Projekt skupia się na analizie wartości własnych macierzy poprzez implementację różnych metod numerycznych. Wykorzystano Okręgi Gershgorina do oszacowania wartości własnych oraz zastosowano metody iteracyjne do ich dokładniejszego obliczenia. Dodatkowo, zwizualizowano okręgi na płaszczyźnie zespolonej i porównano wyniki metod iteracyjnych z rzeczywistymi wartościami własnymi.

## Funkcjonalności
### 1. Obliczanie Okręgów Gershgorina
      - Dla danej macierzy kwadratowej obliczamy okręgi Gershgorina.
      - Środek okręgu to elementy diagonalne macierzy, a promień to suma wartości bezwzględnych pozostałych elementów w danym wierszu.
      - Wynikiem jest lista krotek zawierających informacje o środkach i promieniach okręgów.

### 2. Metoda Iteracji Potęgowej
      - Przybliża dominującą (największą) wartość własną oraz odpowiadający jej wektor własny.
      - Algorytm iteracyjnie mnoży macierz przez losowy wektor początkowy, a następnie normalizuje wynik.
      - Proces powtarza się, aż osiągnięta zostanie wymagana dokładność.

### 3. Metoda Iteracji Odwrotnej
      - Oblicza wartości własne bliskie określonej wartości (przesunięcie spektralne).
      - Zamiast mnożenia macierzy przez wektor, rozwiązuje układ równań liniowych, aby znaleźć przybliżony wektor własny.
      - Iteracyjnie aktualizuje wynik i zwraca wartość własną wraz z wektorem własnym.

### 4. Wizualizacja Okręgów Gershgorina
      - Rysuje okręgi Gershgorina na płaszczyźnie zespolonej, co pozwala na intuicyjne zobrazowanie rozmieszczenia wartości własnych.
      - Porównuje rzeczywiste wartości własne z okręgami.

### 5. Testowanie i porównanie metod
      - Przeprowadzamy testy na macierzach o znanych wartościach własnych.
      - Porównujemy wyniki metod iteracyjnych (potęgowej i odwrotnej) z rzeczywistymi wartościami własnymi obliczonymi za pomocą funkcji NumPy.
      - Analizujemy różnice w dokładności i efektywności każdej metody.



