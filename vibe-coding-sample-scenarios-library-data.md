## **Datensatz 1: Chicago Public Library Circulation Data**
**Quelle:** [City of Chicago Data Portal](https://data.cityofchicago.org/Education/Libraries-2024-Circulation-by-Location/utjc-493b)

### 📊 **Szenario 1: Ausleih-Dashboard "Wo ist was los?"**
```
Erstelle mir ein Dashboard für Bibliotheksstatistiken.
Nutze diese CSV-Daten: Chicago Public Library Circulation by Location.
Spalten: Standort, Jahr, Monat, Ausleihen, Besucherzahlen
Ich will sehen: Welche Standorte sind am aktivsten? Trends über Zeit?
Mach es interaktiv mit Filtermöglichkeiten.
```

**Sample CSV (vereinfacht):**
```csv
Location,Year,Month,Circulation,Visits
Albany Park,2024,01,2847,1234
Altgeld,2024,01,1205,567
Archer Heights,2024,01,3421,890
Avalon,2024,01,2156,1123
```

---

## **Datensatz 2: Goodbooks-10k (Books Sample)**
**Quelle:** [GitHub Goodbooks-10k](https://github.com/zygmuntz/goodbooks-10k)

### 📚 **Szenario 2: Buchempfehlungs-Tool "Finde dein nächstes Lieblingsbuch"**
```
Baue mir ein Tool für Buchempfehlungen.
Nutze diese Bücherdaten mit Titel, Autor, Rating, Genre, Seiten.
Benutzer soll filtern können: Genre, Bewertung, Seitenzahl
Zeige schöne Buchkarten mit Cover-Platzhaltern.
Sortierung nach Rating oder Titel möglich.
```

**Sample CSV:**
```csv
Title,Author,Rating,Genre,Pages,Publication_Year
The Hunger Games,Suzanne Collins,4.34,Young Adult,374,2008
Harry Potter and the Philosopher's Stone,J.K. Rowling,4.47,Fantasy,309,1997
To Kill a Mockingbird,Harper Lee,4.25,Fiction,281,1960
Pride and Prejudice,Jane Austen,4.28,Romance,279,1813
```

---

## **Datensatz 3: Library Management System Dataset**
**Quelle:** [Kaggle Library Books](https://www.kaggle.com/datasets/bimalgajera/library-books)

### 🏷️ **Szenario 3: Bestandsmanagement "Wo ist mein Buch?"**
```
Erstelle ein Tool für Bibliotheksbestand.
Daten: Buch-ID, Titel, Autor, Kategorie, Status (verfügbar/ausgeliehen), Regal
Features: Suche nach Titel/Autor, Filter nach Status, Regal-Übersicht
Zeige auch: Welche Kategorien haben die meisten ausgeliehenen Bücher?
```

**Sample CSV:**
```csv
Book_ID,Title,Author,Category,Status,Shelf_Location,Due_Date
B001,1984,George Orwell,Fiction,Available,A1-023,
B002,Python Programming,John Smith,Technology,Checked Out,C2-156,2024-02-15
B003,The Great Gatsby,F. Scott Fitzgerald,Fiction,Available,A1-089,
B004,Database Systems,Mary Johnson,Technology,Checked Out,C2-201,2024-02-20
```

---

## **Szenario 4: OHNE Input-Daten - ISBN Lookup Tool**

### 🔍 **"Magic ISBN" - Buch-Metadaten aus der Luft zaubern**
```
Baue mir ein Tool, wo ich eine ISBN eingebe und automatisch Buchinfos bekomme.
Nutze die kostenlose OpenLibrary API.
Input: ISBN-Feld
Output: Titel, Autor, Jahr, Cover, Beschreibung
Mach es schön und benutzerfreundlich.
```

**Keine CSV nötig** - nutzt OpenLibrary API:
- `https://openlibrary.org/api/books?bibkeys=ISBN:9780140328721&format=json&jscmd=details`

**Test-ISBNs für die Übung:**
- `9780140328721` (Fantastic Mr. Fox)
- `9780439708180` (Harry Potter)
- `9780061120084` (To Kill a Mockingbird)
