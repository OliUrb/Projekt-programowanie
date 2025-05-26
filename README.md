# Badanie Położenia Punktu Względem Prostej i Przynależności Punktu do Odcinka
## Projekt zawiera implementacje dwóch kluczowych operacji geometrycznych w układzie współrzędnych:

1. Badanie położenia punktu względem prostej – określanie, czy punkt znajduje się powyżej, na, czy poniżej prostej o równaniu y=ax+b

2. Sprawdzanie przynależności punktu do odcinka – weryfikacja, czy punkt leży dokładnie na odcinku wyznaczonym przez dwa punkty w przestrzeni dwuwymiarowej.
   
Projekt jest przydatny w analizie geometrycznej, algorytmach komputerowej grafiki i w rozwiązywaniu problemów analizy danych przestrzennych.

# Położenie punktu względem prostej:
Funkcja sprawdz_polozenie_punktu(a, b, punkt) oblicza, czy dany punkt 
(𝑋,𝑌) leży powyżej, na, czy poniżej prostej o równaniu:

**y=ax+b**

1. Jeśli 𝑌 𝑝𝑢𝑛𝑘𝑡𝑢 > 𝑌𝑝𝑟𝑜𝑠𝑡𝑒𝑗 → punkt jest powyżej prostej.
2. Jeśli 𝑌 𝑝𝑢𝑛𝑘𝑡𝑢 == 𝑌𝑝𝑟𝑜𝑠𝑡𝑒𝑗 → punkt leży na prostej.
3. Jeśli 𝑌 𝑝𝑢𝑛𝑘𝑡𝑢 < 𝑌𝑝𝑟𝑜𝑠𝑡𝑒𝑗 → punkt jest poniżej prostej.

## Kod:
```python
def sprawdz_polozenie_punktu(a, b, punkt):
    Xpunktu, Ypunktu = punkt
    Yprostej = a * Xpunktu + b
    if Ypunktu > Yprostej:
        print("Wyznaczony punkt jest powyżej prostej")
    elif Ypunktu == Yprostej:
        print("Wyznaczony punkt jest na prostej")
    else:
        print("Wyznaczony punkt jest poniżej prostej")

a = float(input("Podaj parametr a: "))
b = float(input("Podaj parametr b: "))
Xp = float(input("Podaj współrzędną x punktu: "))
Yp = float(input("Podaj współrzędną y punktu: "))
sprawdz_polozenie_punktu(a, b, (Xp,Yp))
```

# Przykład działania
## Przykład 1 – Położenie punktu względem prostej
### Dane wejściowe:
```python
Podaj parametr a: 2
Podaj parametr b: 3
Podaj współrzędną x punktu: 4
Podaj współrzędną y punktu: 10
```
### Wynik:
```python
Wyznaczony punkt jest powyżej prostej
```


# Przynależność punktu do odcinka
Funkcja sprawdz_czy_punkt_na_odcinku(A, B, punkt) sprawdza, czy punkt (𝑋,𝑌) znajduje się na odcinku pomiędzy punktami 𝐴(𝑋𝑎,𝑌𝑎) i B(Xb,Yb).

### Kroki działania:
1. Sprawdzenie, czy współrzędna 𝑋 punktu mieści się w przedziale między Xa i Xb.
2. Obliczenie równania prostej przechodzącej przez punkty 𝐴 i 𝐵 (jeśli 𝑋𝑎 ≠ 𝑋𝑏):
   
**y=ax+b**

3. Sprawdzenie równości współrzędnej Ypunktu z wartością prostej w danym Xpunkt

## Kod:
```python
def sprawdz_czy_punkt_na_odcinku(A, B, punkt):
    Xa, Ya = A
    Xb, Yb = B
    Xpunkt, Ypunkt = punkt
    if (Xa <= Xpunkt <= Xb):
        a = (Yb - Ya)/(Xb - Xa)
        b = Ya - a * Xa
        Yprostej = a * Xpunkt + b
        if Yprostej == Ypunkt:
            print("Punkt znajduje się na odcinku")
        else:
            print("Punkt nie znajduje się na odcinku")
    else:
        print("NIE znajduje się w przedziale")

Xa = float(input("Podaj współrzędną x począku odcinka: "))
Ya = float(input("Podaj współrzędną y począku odcinka: "))
Xb = float(input("Podaj współrzędną x końca odcinka: "))
Yb = float(input("Podaj współrzędną Y końca odcinka: "))
x = float(input("Podaj współrzędną x sprawdzanego punktu: "))
y = float(input("Podaj współrzędną y sprawdzanego punktu: "))
sprawdz_czy_punkt_na_odcinku((Xa,Ya), (Xb,Yb), (x,y))
```

4. Wprowadź wartości podane w instrukcjach.

## Przykład 2 – Sprawdzenie przynależności punktu do odcinka
### Dane wejściowe:
```python
Podaj współrzędną x początku odcinka: 1
Podaj współrzędną y początku odcinka: 2
Podaj współrzędną x końca odcinka: 5
Podaj współrzędną y końca odcinka: 6
Podaj współrzędną x sprawdzanego punktu: 3
Podaj współrzędną y sprawdzanego punktu: 4
```

### Wynik:
```python
Punkt znajduje się na odcinku
```


# Zadania:
## Zadanie 1: Położenie punktu względem prostej
Napisz program, który sprawdzi, czy punkt (3,5) leży powyżej, na, czy poniżej prostej o równaniu:
y=2x+1
Wykorzystaj funkcję sprawdz_polozenie_punktu().

Oczekiwany wynik:
```python
Punkt znajduje się na prostej / powyżej / poniżej (w zależności od obliczeń)
```

## Zadanie 2: Przynależność punktu do odcinka
Dany jest odcinek o końcach A(1,2) i B(4,5).
Sprawdź, czy punkt P(2,3) należy do tego odcinka, korzystając z funkcji:
sprawdz_czy_punkt_na_odcinku().

Oczekiwany wynik:
```python
Punkt znajduje się na odcinku / nie znajduje się na odcinku
```
