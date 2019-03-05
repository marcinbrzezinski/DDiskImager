# DDiskImager
Skrypt w języku Python wspomagający obrazowanie nośników w system Linux, wykorzystuje w tym celu linuxowe narzędzie dd.

## Funkcjonalność
* obrazowanie całych nośników
* obliczanie sum kontrolnych (sha256 i MD5) i ich porównywanie
* zapisywanie informacji w logu

## Instrukcja

* Skrypt należy uruchomić z uprawnieniami root'a (sudo ./DDiskImager.py)
* Nie należy zmieniać położenia pliku "DDiskImager.py" a także folderu "Files", w którym będą zapisywane logi.
