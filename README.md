# R-tree

Implementacja struktury danych R-drzewo przechowującej obiekty danego typu w przestrzeni dwuwymiarowej.


*Algorytm na podstawie publikacji A. Guttmana*
>[R-Trees. A dynamic index structure for spatial searching](http://www-db.deis.unibo.it/courses/SI-LS/papers/Gut84.pdf)

## Dokumentacja API
Funkcje publicznego API opisane zostały za pomocą Scala Doc.
Dokumentację można wygenerować poleceniem
``sbt doc``

## Krótki opis API
#### stworzenie drzewa
``RTree[T](): RTree[T]``
``RTree[T](minEntries: Int, maxEntries: Int): RTree[T]``
#### dodanie elementu
``insert(entry: Entry[T])``
``insert(Rectangle(Coordinates(x, y), Dimensions(w, h), value)``
#### usunięcie elementu
``remove(entry: Entry[T]): RTree[T]``
#### wyszukanie elementów
``search(searchBound: Bound): Vector[Entry[T]]``




## Przykład użycia
utworzenie R-Tree z dwoma elementami
```
val rtree = RTree[String]()
    .insert(Rectangle(Coordinates(-2,1), Dimensions(1,1)), "apple")
    .insert(Rectangle(Coordinates(2,2), Dimensions(2,2)), "orange")

```

## Testowanie
Implementacja testowana jest za pomocą testów jednostkowych, pokrycie wynosi 90%.
