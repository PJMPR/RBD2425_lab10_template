# 📘 MongoDB: Dokumentacja funkcji `aggregate`

Funkcja `aggregate` w MongoDB umożliwia przetwarzanie danych w wielu etapach (tzw. pipeline). Każdy etap reprezentowany jest jako obiekt z operatorem (np. `$match`, `$group`, `$project`, `$unwind`). Agregacja pozwala wykonywać zaawansowane operacje analityczne, transformacje i filtrowanie danych.

---

## 🔧 Składnia podstawowa

```js
db.collection.aggregate([ etap1, etap2, ... ])
```

Każdy etap to dokument zawierający operator agregujący, np.:

```js
{ $match: { ... } }
{ $group: { ... } }
```

---

## 🔍 Najczęściej używane operatory

### 📂 `$unwind`

Rozbija tablicę na wiele dokumentów – po jednym na każdy element tablicy.

**Przykład:**

```js
db.orders.aggregate([
  { $unwind: "$items" }
]);
```

> 🔎 *Rozdziela dokumenty na podstawie tablicy `items` — każdy element tablicy staje się osobnym dokumentem.*
> Jeśli dokument zawiera pole `items: ["A", "B"]`, po `$unwind` otrzymujemy dwa dokumenty z `items: "A"` i `items: "B"`.

**Opcje dodatkowe:**

```js
{ $unwind: { path: "$items", preserveNullAndEmptyArrays: true } }
```

---

### 🧮 `$group`

Grupuje dokumenty według pola lub wyrażenia, umożliwia wykonywanie operacji agregujących (np. `$sum`, `$avg`, `$max`, `$min`).

**Składnia:**

```js
{ $group: {
    _id: "$poleDoGrupowania",
    suma: { $sum: "$wartość" },
    srednia: { $avg: "$wartość" }
} }
```

**Przykład:**

```js
db.orders.aggregate([
  { $unwind: "$items" },
  { $group: {
      _id: "$items.name",
      totalQuantity: { $sum: "$items.qty" }
  } }
]);
```

> 🔎 *Zlicza całkowitą liczbę sztuk (`qty`) sprzedanych dla każdego produktu (`items.name`).*

---

### 🔬 `$project`

Pozwala określić, które pola mają być widoczne w wyniku oraz tworzyć nowe pola na podstawie istniejących.

**Składnia:**

```js
{ $project: {
    nowePole: "$istniejące_pole",
    stala: { $literal: "wartość" },
    rok: { $substr: ["$data", 0, 4] },
    _id: 0
} }
```

**Przykład:**

```js
db.users.aggregate([
  { $project: {
      fullName: { $concat: ["$first_name", " ", "$last_name"] },
      email: 1,
      _id: 0
  } }
]);
```

> 🔎 *Tworzy nowe pole `fullName` jako połączenie `first_name` i `last_name`, pozostawiając tylko email i usuwając `_id`.*

---

## 📚 Inne popularne operatory

* `$match` – filtruje dokumenty na wzór `find()`
* `$sort` – sortuje wyniki
* `$limit` / `$skip` – ogranicza ilość danych
* `$addFields` – dodaje nowe pola
* `$replaceRoot` – zamienia cały dokument na wartość z pola

---

## 🧠 Przykład pełnego pipeline'u

```js
db.customers.aggregate([
  { $unwind: "$invoices" },
  { $match: { "invoices.total": { $gt: 10 } } },
  { $group: {
      _id: "$source_id",
      totalSpent: { $sum: "$invoices.total" }
  } },
  { $sort: { totalSpent: -1 } }
]);
```

> 🔎 *Filtruje faktury o wartości powyżej 10, grupuje według klienta i sortuje ich całkowite wydatki malejąco.*

---

## 📌 Uwagi końcowe

* Kolejność etapów ma znaczenie!
* `$unwind` może znacznie zwiększyć liczbę dokumentów — warto używać go z rozwagą.
* Agregacje można testować w MongoDB Compass, shellu, albo w kodzie Node.js za pomocą metody `.aggregate()`.

---

Masz pytania? Zerknij na oficjalną dokumentację MongoDB: [https://www.mongodb.com/docs/manual/aggregation/](https://www.mongodb.com/docs/manual/aggregation/)

