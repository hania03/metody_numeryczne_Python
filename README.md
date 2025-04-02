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



# Laboratorium 2
## Opis projektu
Projekt zawiera implementacje różnych metod numerycznych do obliczania wartości własnych macierzy. Zastosowane metody obejmują iteracyjne podejścia, takie jak metoda potęgowa i metoda iteracji odwrotnej, a także algorytmy bardziej zaawansowane, takie jak metoda bisekcji dla macierzy trójprzekątnej oraz iteracja QR dla macierzy Hessenberga. Celem jest porównanie dokładności oraz efektywności tych metod na przykładzie różnych macierzy.

## Funkcjonalności
### 1. Metoda iteracji potęgowej (power_method)
      - Oblicza dominującą wartość własną oraz odpowiadający jej wektor własny.
      - Algorytm iteracyjny, który mnoży macierz przez wektor początkowy i normalizuje wynik.
      - Parametry wejściowe: macierz kwadratowa A, tolerancja tol, maksymalna liczba iteracji max_iter.
      
### 2. Metoda iteracji odwrotnej (reverse_iteration)
      - Oblicza wartość własną najbliższą danemu przybliżeniu mu.
      - Wykorzystuje algorytm iteracyjny, rozwiązując układ równań liniowych w każdej iteracji.
      - Może wykorzystywać przesunięcie spektralne (iloraz Rayleigha) dla szybszej zbieżności.
      - Parametry wejściowe: macierz A, przybliżenie mu, tolerancja tol, maksymalna liczba iteracji max_iter.

### 3. Metoda bisekcji dla macierzy trójprzekątnej (bisection_tridiagonal)
      - Oblicza wszystkie wartości własne symetrycznej macierzy trójprzekątnej.
      - Wykorzystuje metodę bisekcji, analizując zmiany znaku wielomianu charakterystycznego.
      - Parametry wejściowe: diagonalne elementy diag, elementy poza przekątną off_diag, tolerancja tol, max_iter.

### 4. Obliczanie wartości własnych macierzy Hessenberga (eigenvalues_hessenberg)
      - Wykorzystuje iterację QR do znajdowania wartości własnych górnej macierzy Hessenberga.
      - Wykorzystuje dekompozycję QR oraz redukcję macierzy do stabilizacji numerycznej.
      - Parametry wejściowe: macierz Hessenberga H, tolerancja tol, max_iter.

### 5. Porównanie metod obliczania wartości własnych
      - Losowo generuje macierze symetryczne i macierze Hessenberga.
      - Stosuje wszystkie zaimplementowane metody do obliczenia wartości własnych.
      - Porównuje dokładność i szybkość konwergencji każdej metody.
      - Wizualizuje wyniki na wykresach, analizując efektywność metod.



# Laboratorium 3
## Opis projektu
Celem projektu jest implementacja oraz analiza metod opartych na algorytmie QR do obliczania wartości własnych różnych typów macierzy. Projekt obejmuje zarówno podstawowe techniki, jak i bardziej zaawansowane podejścia, takie jak przesunięcia spektralne oraz transformacje Householdera.

## Funkcjonalności
### 1. Metoda QR dla macierzy trójdiagonalnej symetrycznej
      - Funkcja: eigenvalues_qr_tridiagonal(diag, off_diag, tol, max_iter)
      - Opis:
            - Oblicza wartości własne symetrycznej macierzy trójprzekątnej przy użyciu iteracji QR.
            - Korzysta z dekompozycji QR, gdzie macierz A jest aktualizowana w każdej iteracji jako A = R * Q.
            - Warunek stopu: elementy poza przekątną są mniejsze od tol.
      - Zastosowanie: Efektywne dla dużych macierzy, szczególnie macierzy o strukturze pasmowej.

### 2. Metoda QR dla dolnej macierzy Hessenberga (wersja odwrotna)
      - Funkcja: eigenvalues_qr_hessenberg_reverse(H, tol, max_iter)
      - Opis:
            - Stosuje iterację QR w odwrotnym kierunku (H = Q * R).
            - Używa macierzy Hessenberga, co przyspiesza obliczenia.
            - Warunek stopu: suma wartości poza diagonalą < tol.
      - Zastosowanie: Szybsza konwergencja niż klasyczny QR.

### 3. Metoda QR dla dolnej macierzy Hessenberga z przesunięciem
      - Funkcja: eigenvalues_qr_hessenberg_shift(H, shift, tol, max_iter)
      - Opis:
            - Wykorzystuje przesunięcie spektralne (shift) dla poprawy zbieżności.
            - W każdej iteracji przesuwa macierz przed dekompozycją QR (H - shift*I).
            - Zwiększa dokładność i przyspiesza konwergencję.
      - Zastosowanie: Redukuje liczbę iteracji w metodzie QR.

### 4. Metoda QR z przekształceniem Householdera
      - Funkcja: householder_transform(matrix): Redukuje macierz do postaci trójkątnej.
                 qr_algorithm(matrix, iterations): Stosuje iteracyjny algorytm QR.
      - Opis:
            - Redukuje macierz do postaci trójkątnej przy użyciu transformacji Householdera.
            - W kolejnych iteracjach stosuje dekompozycję QR, aż do osiągnięcia zbieżności.
      - Zastosowanie: Bardziej stabilne numerycznie niż klasyczny QR.

### 5. Metoda QR dla macierzy rzeczywistych
      - Funkcja: qr_algorithm_real(matrix, tol, max_iter)
      - Opis:
            - Zastosowanie metody QR do macierzy rzeczywistych.
            - Znajduje zarówno wartości, jak i wektory własne.
            - Testowanie na rzeczywistych macierzach dla analizy dokładności.
      - Zastosowanie: Obliczanie wartości własnych w zastosowaniach inżynieryjnych.

### 6. Implementacja rozkładu QR przy użyciu transformacji Householdera
      - Funkcja: qr_decomposition_householder(matrix)
      - Opis:
            - Implementacja transformacji Householdera do rozkładu QR.
            - Zwraca macierze ortogonalną Q i górną trójkątną R.
      - Zastosowanie: Poprawia stabilność numeryczną i dokładność.

### 7. Iteracyjny algorytm QR do wartości własnych
      - Funkcja: iterative_qr_eigenvalues(matrix, tol, max_iter)
      - Opis:
            - Iteracyjne stosowanie rozkładu QR do macierzy aż do zbieżności.
            - Wartości własne odczytywane z diagonalnych elementów.
      - Zastosowanie: Obliczanie wartości własnych dowolnych macierzy.

### 8. Testowanie i analiza wydajności metod QR
      - Funkcja: test_qr_methods()
      - Opis:
            - Generowanie macierzy różnych rozmiarów.
            - Porównanie dokładności, liczby iteracji i czasu wykonania dla różnych metod QR.
            - Wizualizacja wyników.
      - Zastosowanie: Wybór optymalnej metody dla różnych typów macierzy.



# Laboratorium 4
## Opis projektu
Projekt obejmuje implementację oraz analizę metod numerycznych do rozwiązywania równań różniczkowych pierwszego rzędu. Skupiamy się na metodzie Eulera, metodzie Taylora drugiego rzędu oraz ich porównaniu pod kątem dokładności i wpływu kroku całkowania.

## Funkcjonalności
### 1. Implementacja metody Eulera
      - Funkcja: euler_method(f, x0, y0, h, x_end)
      - Opis:
            - Implementacja podstawowej metody Eulera do rozwiązywania równań różniczkowych.
            - Zwraca wartość y(1) dla kroku h = 0.1.
      - Zastosowanie: Metoda prosta, ale mało dokładna dla dużych wartości h.

### 2. Implementacja metody Taylora drugiego rzędu
      - Funkcja: taylor_method(f, df_dx, x0, y0, h, x_end)
      - Opis:
            - Stosuje rozwinięcie Taylora drugiego rzędu
            - Używa zarówno pochodnej pierwszego, jak i drugiego rzędu.
            - Dokładniejsza niż metoda Eulera.
      - Zastosowanie: Poprawia dokładność, ale wymaga obliczania pochodnych.

### 3. Porównanie dokładności metod Eulera i Taylora
      - Funkcja: compare_methods(f, df_dx, x0, y0, h_values, x_end, exact_solution)
      - Opis:
            - Porównuje wartości uzyskane metodą Eulera i Taylora drugiego rzędu dla różnych kroków całkowania
            - Tworzy tabelę wyników i wykres porównawczy względem rozwiązania analitycznego.
      - Zastosowanie: Analiza wpływu kroku h na dokładność metody.

### 4. Iteracyjne rozwiązanie na całym przedziale
      - Funkcja: solve_iteratively(f, df_dx, x0, y0, h, x_end, method='taylor')
      - Opis:
            - Iteracyjnie oblicza wartości funkcji dla x ∈ [0, 1].
            - Możliwość wyboru metody Eulera lub Taylora.
            - Wyniki zapisywane w tabeli i wykresie.
      - Zastosowanie: Praktyczne zastosowanie metod dla całego przedziału.

### 5. Wpływ kroku całkowania na dokładność
      - Funkcja: analyze_step_size(f, df_dx, x0, y0, h_values, x_end, exact_solution)
      - Opis:
            - Testowanie różnych wartości h
            - Analiza błędu globalnego.
            - Wnioski dotyczące wpływu kroku h na dokładność rozwiązania.
      - Zastosowanie: Dobór optymalnego kroku całkowania.

### 6. Implementacja ogólnej metody Taylora
      - Funkcja: taylor_method_general(f, derivatives, x0, y0, h, x_end, order_n)
      - Opis:
            - Rozbudowana wersja metody Taylora do dowolnego rzędu n.
            - Korzysta z iteracyjnego obliczania kolejnych pochodnych
            - Możliwość wyboru rzędów 1–4.
      - Zastosowanie: Bardzo dokładna metoda dla równań różniczkowych.



# Laboratorium 5
## Opis projektu
Projekt obejmuje implementację i analizę metod numerycznych Rungego-Kutty drugiego (RK2 - Heuna) i czwartego rzędu (RK4). Celem jest porównanie tych metod z metodą Eulera oraz analiza błędów obliczeniowych.

## Funkcjonalności
### 1. Implementacja metody Heuna (RK2)
      - Funkcja: rk2_heun(f, x0, y0, h, x_end)
      - Opis:
            - Zaimplementowana metoda RK2 (Heuna) do rozwiązywania równań różniczkowych.
            - Wykorzystuje dwie oceny wartości pochodnej w danym kroku.
            - Jest dokładniejsza od metody Eulera.
      - Zastosowanie: Szybsza zbieżność niż metoda Eulera, ale nieco bardziej skomplikowana obliczeniowo.

### 2. Implementacja metody RK4
      - Funkcja: rk4(f, x0, y0, h, x_end)
      - Opis:
            - Implementacja metody RK4, jednej z najdokładniejszych metod do rozwiązywania równań różniczkowych.
            - Wykorzystuje cztery punkty oceny pochodnej, co poprawia dokładność obliczeń.
      - Zastosowanie: Bardzo dokładna metoda, często stosowana w obliczeniach numerycznych.

### 3. Porównanie metod Eulera, RK2 i RK4
      - Funkcja: compare_methods(f, x0, y0, h, x_end, exact_solution)
      - Opis:
            - Porównuje metody Eulera, RK2 (Heuna) i RK4 dla określonego równania różniczkowego.
            - Oblicza wartości przybliżone i zestawia je z rozwiązaniem analitycznym.
            - Tworzy tabelę wyników oraz wykres porównawczy.
      - Zastosowanie: Analiza skuteczności różnych metod numerycznych.

### 4. Analiza błędów metody Heuna (RK2)
      - Funkcja: analyze_errors_rk2(f, exact_solution, x0, y0, h, x_end)
      - Opis:
            - Oblicza błędy lokalne i globalne metody Heuna (RK2).
            - Porównuje wartości numeryczne z dokładnym rozwiązaniem.
            - Tworzy tabelę wartości dokładnych, przybliżonych oraz błędów.
      - Zastosowanie: Sprawdzenie dokładności metody Heuna i analiza jej potencjalnych niedokładności.



# Laboratorium 6
## Opis projektu
Projekt obejmuje implementację i analizę metod Adamsa-Bashfortha (AB2) oraz predyktor-korektor (AB2-AM2). Celem jest porównanie ich z metodą RK4 i ocena dokładności numerycznych rozwiązań.

## Funkcjonalność
### 1.  Implementacja metody Adamsa-Bashfortha (rzędu 2 - AB2)
      - Funkcja: adams_bashforth_2(f, x0, y0, h, n)
      - Opis:
            - Implementacja dwukrokowej metody AB2, wykorzystującej dwie poprzednie wartości do przewidywania nowego punktu.
            - Pierwszy krok obliczany metodą RK4 w celu uzyskania drugiego punktu startowego.
            - Metoda efektywna, ale wymaga wcześniejszej znajomości wartości w dwóch punktach.
      - Zastosowanie: Szybsza niż RK4, ale mniej dokładna; dobra do zastosowań, gdzie wymagane są metody wielokrokowe.

### 2. Implementacja metody Predyktor-Korektor (AB2-AM2)
      - Funkcja: predictor_corrector(f, x0, y0, h, n)
      - Opis:
            - Predyktor: metoda Adamsa-Bashfortha (AB2) do wstępnego oszacowania wartości w kolejnym kroku.
            - Korektor: metoda Adamsa-Moultona (AM2) poprawiająca wartość predykcji, uwzględniając informację z następnego kroku.
            - Pierwszy krok wyznaczany metodą RK4.
      - Zastosowanie:
            - Lepsza dokładność niż czysta metoda AB2.
            - Stosowana w problemach wymagających iteracyjnej korekcji wyników.

### 3. Porównanie z metodą RK4
      - Funkcja: compare_methods(f, x0, y0, h, x_end, exact_solution)
      - Opis:
            - Porównuje AB2, predyktor-korektor oraz RK4 dla wybranego równania różniczkowego.
            - Tworzy tabelę błędów dla każdego punktu siatki.
            - Generuje wykres rozwiązań przybliżonych w zestawieniu z rozwiązaniem analitycznym.
      - Zastosowanie: Sprawdzenie skuteczności metod AB2 i predyktor-korektor względem RK4.

















