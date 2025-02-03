# Badanie Położenia Punktu Względem Prostej i Przynależności Punktu do Odcinka
## Ten projekt zawiera dwa skrypty w języku Python, które umożliwiają:

1. Sprawdzenie, czy punkt leży powyżej, na, czy poniżej danej prostej.

2. Weryfikację, czy dany punkt należy do zadanego odcinka.

# Jak działają kody?
## Położenie punktu względem prostej:
Funkcja sprawdz_polozenie_punktu(a, b, punkt) oblicza, czy dany punkt 
(𝑋,𝑌) leży powyżej, na, czy poniżej prostej o równaniu:

**y=ax+b**

1. Jeśli 𝑌 𝑝𝑢𝑛𝑘𝑡𝑢 > 𝑌𝑝𝑟𝑜𝑠𝑡𝑒𝑗 → punkt jest powyżej prostej.
2. Jeśli 𝑌 𝑝𝑢𝑛𝑘𝑡𝑢 == 𝑌𝑝𝑟𝑜𝑠𝑡𝑒𝑗 → punkt leży na prostej.
3. Jeśli 𝑌 𝑝𝑢𝑛𝑘𝑡𝑢 < 𝑌𝑝𝑟𝑜𝑠𝑡𝑒𝑗 → punkt jest poniżej prostej.

### Uruchomienie:
    python skrypt1.py

### Przykładowe dane wejściowe:
    Podaj parametr a: 2
    Podaj parametr b: 3
    Podaj współrzędną x punktu: 4
    Podaj współrzędną y punktu: 10

### Przykładowy wynik:
    Wyznaczony punkt jest powyżej prostej

## Przynależność punktu do odcinka
Funkcja sprawdz_czy_punkt_na_odcinku(A, B, punkt) sprawdza, czy punkt (𝑋,𝑌) znajduje się na odcinku pomiędzy punktami 𝐴(𝑋𝑎,𝑌𝑎) i B(Xb,Yb).

### Kroki działania:
1. Sprawdzenie, czy współrzędna 𝑋 punktu mieści się w przedziale między Xa i Xb.
2. Obliczenie równania prostej przechodzącej przez punkty 𝐴 i 𝐵 (jeśli 𝑋𝑎 ≠ 𝑋𝑏):
   
**y=ax+b**

3. Sprawdzenie, czy punkt spełnia to równanie.

### Uruchomienie:
    python skrypt2.py

### Przykładowe dane wejściowe:
    Podaj współrzędną x początku odcinka: 1
    Podaj współrzędną y początku odcinka: 2
    Podaj współrzędną x końca odcinka: 5
    Podaj współrzędną y końca odcinka: 6
    Podaj współrzędną x sprawdzanego punktu: 3
    Podaj współrzędną y sprawdzanego punktu: 4

### Przykładowy wynik:
    Punkt znajduje się na odcinku
