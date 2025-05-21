# 💾 Zadania MongoDB dla Studentów

Witaj w zestawie praktycznych zadań z MongoDB! Twoim celem jest napisanie skryptu w języku JavaScript (`script.js`), który realizuje opisane poniżej operacje na bazie danych MongoDB.

Dane są już przygotowane w kolekcjach, które zawierają informacje o klientach, fakturach, wykonawcach, albumach i utworach muzycznych. W zadaniach będziesz modyfikować dane, usuwać je lub wyszukiwać informacje na ich podstawie.

## ✏️ Operacje Aktualizacji

### Zadania

1. **Zmień nazwę wykonawcy**
   Zmień `Name` wykonawcy o `source_id: 3` na `Aerosmith (USA)`.

2. **Dodaj pole `active` do wykonawców**
   Dodaj pole `active` o wartości `true` dla wszystkich wykonawców.

3. **Zaktualizuj nazwę albumu**
   Dla wykonawcy `AC/DC` zmień tytuł albumu `Let There Be Rock` na `Let There Be Rock (Remastered)`.

4. **Zmień nazwę klienta**
   Zmień `first_name` klienta o `source_id: 2` na `Jan`.

5. **Dodaj numer telefonu**
   Ustaw pole `phone` na `"+48 123 456 789"` dla klienta z `email: "bjorn.hansen@yahoo.no"`.

6. **Zmień kraj**
   Zmień `country` z `Germany` na `Poland` dla wszystkich klientów.

7. **Dodaj nowe pole `loyalty_points`**
   Dodaj nowe pole `loyalty_points` i ustaw jego wartość na `0` dla wszystkich klientów.

8. **Zmień kod pocztowy**
   Zmień `postal_code` na `"00-001"` dla klientów z miasta `Warsaw`.

## 🗑️ Operacje Usuwania

### Zadania

1. **Usuń klienta po emailu**
   Usuń klienta o adresie e-mail `kara.nielsen@jubii.dk`.

2. **Usuń klientów z Czech**
   Usuń wszystkich klientów, których `country` to `Czech Republic`.

3. **Usuń faktury o wartości 0**
   Usuń faktury (`invoices`) o wartości `total: 0` ze wszystkich klientów.

4. **Usuń klientów bez faktur**
   Usuń klientów, którzy nie mają żadnych faktur (`invoices` to pusta tablica).

5. **Usuń wykonawców z nazwą `Unknown`**
   Usuń wykonawców, których pole `Name` ma wartość `Unknown`.

## 🔍 Operacje Wyszukiwania

### Zadania

1. **Znajdź wykonawcę po nazwie**
   Wyszukaj wykonawcę, którego `Name` to `AC/DC`.

2. **Wykonawcy z co najmniej jednym albumem**
   Pokaż wszystkich wykonawców, którzy mają przypisane albumy (`albums` nie jest pustą tablicą).

3. **Albumy wykonawcy `Alanis Morissette`**
   Znajdź dokument wykonawcy `Alanis Morissette` i wypisz wszystkie jego albumy.

4. **Znajdź klienta po imieniu**
   Wyszukaj klienta o imieniu `Helena`.

5. **Pokaż klientów z Niemiec**
   Znajdź wszystkich klientów z `country: Germany`.

6. **Szukaj po nazwisku**
   Znajdź wszystkich klientów, których nazwisko to `Peeters`.

7. **Faktury z datą w 2023**
   Wypisz wszystkie faktury, które mają `invoice_date` zawierającą `2023`.

8. **Klienci z kodem pocztowym `70174`**
   Pokaż klientów z `postal_code: 70174`.

## 📊 Operacje Agregujące

### Zadania

1. **Zlicz klientów z każdego kraju**
   Pogrupuj klientów według `country` i policz ilu jest w każdym kraju.

2. **Średnia wartość faktury**
   Oblicz średnią wartość (`total`) wszystkich faktur.

3. **Liczba utworów w fakturach**
   Zlicz wszystkie linie utworów (`lines`) we wszystkich fakturach.

4. **Suma wydatków klientów**
   Dla każdego klienta oblicz łączną wartość jego faktur.

5. **Faktury wg roku**
   Pogrupuj faktury według roku z `invoice_date` i policz, ile faktur przypada na każdy rok.

6. **Liczba albumów na wykonawcę**
   Dla każdego wykonawcy (`artists`) policz, ile ma albumów.

7. **Średnia liczba utworów na album wśród wykonawców**
   Dla każdego wykonawcy policz średnią liczbę utworów w jego albumach.

8. **Wykonawcy z najdłuższymi utworami**
   Pogrupuj wykonawców i oblicz średnią długość (w milisekundach) ich utworów. Posortuj malejąco.

9. **Zlicz klientów z każdego kraju**
   Pogrupuj klientów według `country` i policz ilu jest w każdym kraju.

10. **Średnia wartość faktury**
    Oblicz średnią wartość (`total`) wszystkich faktur.

11. **Liczba utworów w fakturach**
    Zlicz wszystkie linie utworów (`lines`) we wszystkich fakturach.

12. **Suma wydatków klientów**
    Dla każdego klienta oblicz łączną wartość jego faktur.

13. **Faktury wg roku**
    Pogrupuj faktury według roku z `invoice_date` i policz, ile faktur przypada na każdy rok.

---

📝 **Instrukcje dla studentów:**

* Wszystkie rozwiązania umieść w jednym pliku o nazwie `script.js`.
* Możesz używać poleceń `mongo` shell lub sterownika Node.js.
* Upewnij się, że kod jest czytelny i odpowiednio komentowany.

Powodzenia! 🚀
