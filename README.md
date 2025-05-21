# 💾 Zadania MongoDB dla Studentów

Witaj w zestawie praktycznych zadań z MongoDB! Twoim celem jest napisanie skryptu w języku JavaScript (`script.js`), który realizuje opisane poniżej operacje na bazie danych MongoDB.

Dane są już przygotowane w kolekcjach, które zawierają informacje o klientach, fakturach, wykonawcach, albumach i utworach muzycznych. W zadaniach będziesz modyfikować dane, usuwać je lub wyszukiwać informacje na ich podstawie.

Zadania zostały podzielone według rodzaju operacji i poziomu trudności:

* 🟢 Łatwe
* 🟡 Średnie
* 🔴 Trudne

---

## ✏️ Operacje Aktualizacji

### 🟢 Łatwe

1. **Aktualizacja adresu e-mail**
   Znajdź klienta z `source_id: 1` i zaktualizuj jego adres e-mail na `leonie.kohler@example.com`.

2. **Uzupełnij pole `phone`**
   Ustaw wartość pola `phone` na wartość pola `Phone` dla wszystkich klientów, gdzie `phone` jest równe `null`.

### 🟡 Średnie

3. **Zmiana miasta**
   Zmień miasto na `Berlin` dla wszystkich klientów z Niemiec, których obecne miasto to inne niż `Berlin`.

4. **Podwyższenie ceny utworów**
   Zwiększ wartość `unit_price` o 10% dla wszystkich utworów z gatunku `Rock` występujących w fakturach.

### 🔴 Trudne

5. **Zastosowanie rabatu**
   Dla wszystkich pozycji faktur (`lines`) o ilości `quantity >= 5` zastosuj 20% rabat na `unit_price`. Zachowaj precyzję do dwóch miejsc po przecinku.

---

## 🗑️ Operacje Usuwania

### 🟢 Łatwe

1. **Usuń nieaktywnych wykonawców**
   Usuń wszystkich wykonawców (`artists`), którzy nie mają przypisanych żadnych albumów.

### 🟡 Średnie

2. **Usuń klientów o niskich wydatkach**
   Usuń klientów, których łączna suma wszystkich faktur jest mniejsza niż 1.00 USD.

3. **Usuń puste faktury**
   Usuń wszystkie obiekty faktur (`invoices`) z dokumentów klientów, gdzie tablica `lines` jest pusta.

---

## 🔍 Operacje Wyszukiwania

### 🟢 Łatwe

1. **Klienci z Kanady**
   Wypisz wszystkich klientów mieszkających w Kanadzie, pokazując ich pełne imię i nazwisko oraz adres e-mail.

2. **Ostatnie zakupy**
   Pokaż 5 najnowszych faktur (według pola `invoice_date`) ze wszystkich faktur.

3. **Faktury o wysokiej wartości**
   Znajdź wszystkie faktury, gdzie `total` jest większe niż 10.00 USD.

### 🟡 Średnie

4. **Najlepsi klienci**
   Wypisz trzech klientów z najwyższą łączną wartością wszystkich faktur.

5. **Średnia cena utworów**
   Dla każdego klienta oblicz średnią wartość `unit_price` dla kupionych przez niego utworów.

6. **Zakupy w wielu krajach**
   Znajdź klientów, którzy byli obciążani fakturami (`billed`) w więcej niż jednym kraju.

### 🔴 Trudne

7. **Najczęściej kupowane utwory**
   Określ 5 najczęściej kupowanych identyfikatorów utworów (`track_id`) w całej bazie. Zwróć `track_id` oraz liczbę zakupów.

---

