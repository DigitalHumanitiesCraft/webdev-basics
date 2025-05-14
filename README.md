# Web-Entwicklung für Forscher\*innen

## Grundlagen & KI-gestützte Entwicklung mit **Vibe Coding**

*Ein praxisorientierter Workshop für Forscher\*innen ohne Web-Entwicklungserfahrung*

---

## Inhaltsverzeichnis

1. [Web-Vokabular](#das-web-vokabular)
2. [Einfache Entwicklungswerkzeuge](#werkzeuge-einrichten)
3. [Markdown](#markdown)
4. [Effektives Vibe Coding mit KI](#effektives-vibe-coding-mit-ki)
5. [Vom Code zur Website: Einfaches Deployment](#vom-code-zur-website---deployment)
6. [Praxis: Digitale Geisteswissenschaften](#praktisches-beispiel---digitale-geisteswissenschaften)
7. [Barrierefreiheit (a11y) Basics](#barrierefreiheit-a11y-basics)
8. [Vibe Working in der Forschung](#vibe-working-in-der-forschung)
9. [Praktische Tipps & Tricks](#praktische-tipps--tricks)
10. [Weiterführende Ressourcen](#weiterführende-ressourcen)
11. [Zusammenfassung](#zusammenfassung)
12. [Web-Vokabular für Geisteswissenschaftler\*innen](#web-vokabular-für-geisteswissenschaftlerinnen)

---

## Das Web-Vokabular

### Warum Vokabular für KI-gestützte Entwicklung entscheidend ist

- KI benötigt **präzise Fachbegriffe** um bessere Ergebnisse zu liefern (Wir erinnern uns: _Embeddings_, _Multidimensionales Universum_).

### Die drei Grundpfeiler des Webs

1. **HTML** – Struktur & Inhalt (Was wird angezeigt?)
2. **CSS** – Gestaltung (Wie sieht es aus?)
3. **JavaScript** – Interaktion (Was passiert bei Nutzer-Aktionen?)

### Grundlagen HTML – Schlüsselbegriffe

- **HTML-Dokument** (`<!DOCTYPE html>`)
- **Tags** (z.B. `<h1>`, `<section>`, `<article>`)
- **Attribute** (z.B. `class="timeline"`)
- **Semantik** (`<article>`, `<nav>`, `<figure>`)

Beispiel: Grundaufbau für eine digitale Edition

```html
<!DOCTYPE html>
<html lang="de">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Digitale Edition: Briefe von Hannah Arendt</title>
    <link rel="stylesheet" href="css/style.css" />
  </head>
  <body>
    <header>
      <h1>Briefe von Hannah Arendt (1933-1940)</h1>
      <p class="institution">Universität Wien – Philosophisches Institut</p>
    </header>
    <main>
      <section class="manuscript">
        <h2>Brief vom 12. März 1935</h2>
        <figure>
          <img
            src="images/brief_1935.jpg"
            alt="Scan des handschriftlichen Briefes von 1935"
          />
          <figcaption>Originalbrief an Karl Jaspers, 1935</figcaption>
        </figure>
        <article class="transcription">
          <p>Sehr geehrter Herr Professor,</p>
          <p>
            die Zeit in
            <span class="place" data-coordinates="48.2082,16.3738">Wien</span>
            ist...
          </p>
        </article>
        <aside class="annotations">
          <h3>Anmerkungen</h3>
          <ol>
            <li id="note1">
              Die Erwähnung von Wien bezieht sich auf Arendts Aufenthalt im
              Winter 1935.
            </li>
          </ol>
        </aside>
      </section>
    </main>
    <footer>
      <p>© 2025 Digitale Editionen • <a href="methodik.html">Methodik</a></p>
    </footer>
    <script src="js/script.js"></script>
  </body>
</html>
```

### Grundlagen CSS – Schlüsselbegriffe

- **Selektor**, **Eigenschaft**, **Wert**
- **Responsive Design** (für Mobilgeräte)
- **Klassen** vs. **IDs**

Beispiel: CSS für eine digitale Edition

```css
/* Grundlayout */
body {
  font-family: "Palatino", "Georgia", serif;
  line-height: 1.6;
  max-width: 800px;
  margin: 0 auto;
  padding: 1rem;
  color: #333;
}

/* Spezifische Stile für Manuskripte */
#manuscript {
  border: 1px solid #e0e0e0;
  padding: 2rem;
  margin-bottom: 2rem;
  background-color: #f9f9f9;
}

.transcription {
  font-family: "Courier New", monospace;
  background-color: #fff;
  padding: 1rem;
  border-left: 3px solid #6b4c35;
}

/* Hervorhebungen für Orte, Personen etc. */
.place {
  color: #2c5282;
  font-style: italic;
  cursor: help;
}

/* Responsives Design für mobile Geräte */
@media (max-width: 600px) {
  .manuscript {
    padding: 1rem;
  }

  figure img {
    width: 100%;
    height: auto;
  }
}
```

### Grundlagen JavaScript

- Interaktivität hinzufügen (z.B. Zeitstrahl, Bildergalerie)
- Meist können Sie **fertige Komponenten** verwenden oder mit KI generieren

Beispiel: Einfache Interaktivität für Annotationen

```javascript
// Warten, bis das Dokument vollständig geladen ist
document.addEventListener("DOMContentLoaded", function () {
  // Alle Elemente mit der Klasse 'place' auswählen
  const placeElements = document.querySelectorAll(".place");

  // Für jedes Element einen Event-Listener hinzufügen
  placeElements.forEach(function (element) {
    element.addEventListener("click", function () {
      // Koordinaten aus dem data-Attribut lesen
      const coordinates = this.dataset.coordinates;

      // Einfache Infobox anzeigen
      alert("Koordinaten: " + coordinates);
    });
  });
});
```

---

## Werkzeuge einrichten

### Visual Studio Code (VS Code)

1. **Download**: [https://code.visualstudio.com/](https://code.visualstudio.com/)
2. **Empfohlene Extensions**
   - **Live Server** (lokale Vorschau)
   - **Prettier** (Code-Formatierung)
   - **Markdown All in One** (Markdown ist wichtig!)
   - **Web Accessibility** (a11y-Checker)
   - **HTML CSS Support**

   ![alt text](image-1.png)

### Einfaches GitHub-Setup

- Erstellen Sie ein kostenloses Konto auf [GitHub](https://github.com/)
- Installieren Sie [GitHub Desktop](https://desktop.github.com/) für einfaches Veröffentlichen
![alt text](image-2.png)
- Veröffentichen Sie ihre Seite mit [GitHub Pages](https://pages.github.com/)

### Browser DevTools – einfache Nutzung
![alt text](image-3.png)
- **Inspektor**: HTML & CSS anschauen
- **Zugänglichkeitsprüfung**: Kontrast, Screenreader-Kompatibilität
- **Hard Refresh**: `Ctrl+F5` (Windows) oder `Cmd+Shift+R` (Mac) – wichtig bei Caching-Problemen

> **Tipp**: Öffnen mit `F12` oder Rechtsklick → _Untersuchen_

---

## Markdown

> https://www.markdownguide.org/cheat-sheet/

### Was ist Markdown?

- Leichte **Auszeichnungssprache**
- Perfekt für **README**, **Paper Drafts**, **Forschungsnotizen** und unverzichtbar im Umgang mit LLMs
- Direkt auf GitHub, GitLab, und vielen weiteren Plattformen gerendert

Grundlegende Syntax

```markdown
# Hauptüberschrift

## Unterüberschrift

- Listenpunkt
- **Fett** und _Kursiv_

| Jahr | Ereignis         | Quelle      |
| ---- | ---------------- | ----------- |
| 1942 | Brief an Jaspers | Archiv Wien |
```

> **MathJax**: $E = mc^2$ • Fußnoten: `[^1]`
>
> **Zitationssysteme**: [@Smith2022, p. 45]

### Richtiges Kopieren und Einfügen

- **Einfaches Einfügen**: `Ctrl+V` (behält Formatierung)
- **Einfügen ohne Formatierung**: `Ctrl+Shift+V` (nur Text)
- **Als Markdown kopieren**: In Google Docs → Rechtsklick → "Als Markdown kopieren/einfügen"
- **Formatierungsprobleme vermeiden**: Texte immer zunächst in einem einfachen Texteditor (z.B. Notepad | _nicht Word benutzen!!_) zwischenspeichern

---

## **Vibe Coding**

> https://dhcraft.org/excellence/blog/Vibe-Coding

### Was ist Vibe Coding?

> "Vibe Coding (oder Vibecoding) ist eine Programmiertechnik, welche sich ganz auf > Künstliche Intelligenz (KI) zum Generieren des Quellcodes verlässt und somit > Programmierung auch für Unerfahrene zugänglich macht."
> -- <cite>Wikipedia</cite>

Der Begriff wurde von Andrej Karpathy (ehemaliger KI-Leiter bei Tesla und Gründer von OpenAI) im Februar 2025 geprägt und beschreibt einen Paradigmenwechsel in der Softwareentwicklung.

### Charakteristiken des Vibe Codings

- **Natürliche Sprache:** Programmieren durch Beschreibung statt manuellem Coden
- **Schnelle Iteration:** Rasches Prototyping und Experimentieren
- **Abstraktion:** Fokus auf die Absicht statt auf technische Details
- **Kollaboration mit KI:** Mensch und Maschine als Team

### Konzept

1. **Absicht beschreiben** (Prompt) – kein manueller Code nötig
2. **KI liefert** Vorschlag + Erklärung
3. **Testen und Anpassen** in kleinen Schritten

> **Tipp**: Beschreiben Sie Ihr Vorhaben in klaren Fachbegriffen (z.B. "digitale Edition", "annotierte Bibliographie").

### Typischer Vibe Coding Workflow

![alt text](image.png)

1. **Konzeptualisierung:** Beschreibung des Ziels in natürlicher Sprache --> [Promptotyping](https://dhcraft.org/excellence/blog/Promptotyping) Markdown Documents!
2. **KI-Generierung:** Erzeugung eines ersten Code-Entwurfs
3. **Iterative Verfeinerung:** Feedback und Anpassungen
4. **Überprüfung und Finalisierung:** Tests und Optimierungen

---

## Vom Code zur Website - Deployment

### Frontend vs. Backend

- **Frontend-Only**: Statische Daten, einfache Präsentation - **meist ideal**
- **Backend**: Nur nötig für komplexe Datenbanken oder interaktive Nutzereingaben

### GitHub Pages (kostenlos)

1. Repo → **Settings → Pages**
2. Branch `main` wählen + **Save**
3. URL: `https://<user>.github.io/<repo>/`
![alt text](image-4.png)

Alternative: **Netlify** (mit einfachem Drag-and-Drop Upload)

---

### Beispielprojekte für Geisteswissenschaften

- **Digitale Edition**: Historische Texte mit Annotationen
- **Interaktiver Zeitstrahl**: Kulturelle oder historische Ereignisse
- **Literarisches Netzwerk**: Beziehungen zwischen Autoren visualisieren
- **Digitale Ausstellung**: Artefakte mit Kontext präsentieren

### Projektstruktur

```text
digitale-edition/
├── index.html
├── css/
│   └── style.css
├── js/
│   └── script.js
├── images/
│   └── archiv-foto.jpg
└── README.md
```

---

## Barrierefreiheit (a11y) Basics

- **Warum?** Inklusion, Forschungszugang für alle
- Verwenden Sie **semantische Tags** (z.B. `<article>`, `<section>`).
- Jedes Bild benötigt **`alt`-Text**.
- Stellen Sie **guten Kontrast** sicher.
- Machen Sie Navigation **tastaturzugänglich**.

---

## Vibe Working in der Forschung

> https://blog.google/technology/ai/thomas-story-alexander-disease/

### Von Vibe Coding zu Vibe Working

Während Vibe Coding sich auf Programmierung konzentriert, beschreibt "Vibe Working" einen breiteren Ansatz der KI-gestützten Ideenentwicklung und Kreativarbeit in der Forschung.

### Kernaspekte des Vibe Working

- **Ideenfindung:** Umwandlung vager Gedanken in strukturierte Konzepte
- **Kollaboration mit KI:** KI als Forschungspartner, nicht nur als Werkzeug
- **Iterativer Prozess:** Kontinuierliche Verfeinerung durch Dialog
- **Interdisziplinarität:** Verbindung verschiedener Fachgebiete

### Anwendungen in der Forschung

- **Literaturrecherche:** Zusammenfassung und Analyse von Papers --> *Deep Research*
- **Datenanalyse:** Explorative Untersuchung und Visualisierung
- **Hypothesenbildung:** Generierung neuer Forschungsfragen
- **Methodenentwicklung:** Planung experimenteller Designs

### Gefahren

- **Halluzinationen!**

---

## Praktische Tipps & Tricks

### Browser-Tipps

- **Hard Refresh**: Löscht den Cache für die aktuelle Seite
  - Windows: `Ctrl+F5` oder `Shift+F5`
  - Mac: `Cmd+Shift+R`
  - Unverzichtbar bei Änderungen an CSS/JS, die nicht sofort sichtbar werden

### Kopieren und Einfügen

- **Probleme mit Code-Formaten**: Achten Sie auf versteckte Formatierungen
- **Einfügen ohne Formatierung**:
  - Windows: `Ctrl+Shift+V`
  - Mac: `Cmd+Shift+V`
- **Als Markdown kopieren**:
  - In Google Docs: Rechtsklick → "Als Markdown kopieren"
  - Verhindert Probleme mit inkonsistenter Formatierung

### Dateiverwaltung

- **Konsistente Dateinamen**: Keine Umlaute oder Leerzeichen in Datei- und Ordnernamen
- **Bilder optimieren**: Große Bilder vor dem Upload komprimieren (z.B. mit [TinyPNG](https://tinypng.com/)) oder .webP nutzen

---

## Weiterführende Ressourcen

- [Programming Historian](https://programminghistorian.org/de/) - Tutorials für digitale Geisteswissenschaften
- [MDN Web Docs](https://developer.mozilla.org/) - Web-Dokumentation
- [The A11y Project](https://www.a11yproject.com/) - Barrierefreiheit
- [Zotero Web Library API](https://www.zotero.org/support/dev/web_api/v3/start) - Bibliographien einbinden

### Browser-basierte Tools
- **Bolt.new**: https://bolt.new/
- **Lovable**: https://lovable.ai/
- **Replit**: https://replit.com/
- **Tempo Labs**: https://www.tempo.new/
- **v0 by Vercel**: https://v0.dev/

### Desktop-Tools
- **Cursor**: https://www.cursor.com/
- **Windsurf (Codeium)**: https://codeium.com/windsurf
- **Devin AI**: https://devin.ai/

### Agentic Tools
- **Claude Code (Anthropic)**: https://www.anthropic.com/claude-code
- **Devin AI**: https://devin.ai/
- **Cursor Composer**: https://www.cursor.com/composer

### Ressourcen zum Thema Vibe Coding
- **Andrej Karpathy's Tweet zu Vibe Coding**: https://twitter.com/karpathy/status/1753203762513936495
- **Vibe Coding Tools Vergleichsseite**: https://www.vibecodingtools.com/
---

## Zusammenfassung

1. **Präzise Beschreibungen ("Vokabl lernen")** führen zu besseren KI-Ergebnissen.
2. **Markdown** ist unverzichtbar in der Arbeit mit LLMs.
3. **GitHub Pages** bietet kostenloses Hosting für Forschungsergebnisse.
4. **Barrierefreiheit** ist essenziell für inklusive Geisteswissenschaften.
5. **Vibe Coding und Vibe Working** bieten neue Wege, mit KI zu kollaborieren.

---

# Umfassendes Web-Entwicklungsvokabular

## HTML-Grundlagen

| Begriff                  | Erklärung                                                                                                                                                                                                                                                                |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **HTML**                 | Hypertext Markup Language - Grundsprache des Webs, die die Struktur und den Inhalt einer Webseite definiert. HTML besteht aus Elementen, die durch Tags markiert werden und dem Browser mitteilen, wie der Inhalt darzustellen ist.                                      |
| **Tag**                  | Auszeichnungselement in HTML, das in spitzen Klammern steht (z.B. `<p>` für Absatz, `<h1>` für Hauptüberschrift, `<article>` für einen eigenständigen Inhaltsbereich). Tags treten meist paarweise auf (öffnend und schließend), können aber auch selbstschließend sein. |
| **Attribut**             | Zusätzliche Informationen innerhalb eines Tags, die dessen Verhalten oder Erscheinungsbild modifizieren (z.B. `class="highlight"`, `id="kapitel1"`, `lang="de"`). Attribute stehen immer im öffnenden Tag.                                                               |
| **DOCTYPE**              | Deklaration am Anfang eines HTML-Dokuments, die dem Browser mitteilt, welche HTML-Version verwendet wird. In HTML5 einfach als `<!DOCTYPE html>` definiert.                                                                                                              |
| **Meta-Tags**            | Spezielle Elemente im `<head>`-Bereich einer Webseite, die Metadaten wie Zeichensatz, Beschreibung, Viewport-Einstellungen oder Autor definieren. Wichtig für Suchmaschinen und korrekte Darstellung.                                                                    |
| **Semantische Elemente** | HTML5-Elemente, die ihre Bedeutung direkt im Namen tragen und so den Inhalt sinnvoll strukturieren, z.B. `<article>`, `<section>`, `<nav>`, `<header>`, `<footer>`. Verbessern Zugänglichkeit und SEO.                                                                   |
| **Verschachtelung**      | Hierarchische Struktur in HTML, bei der Elemente ineinander verschachtelt werden. Die korrekte Verschachtelung (z.B. Listen in Abschnitten, Absätze in Artikeln) ist entscheidend für valides HTML.                                                                      |
| **Block vs. Inline**     | Grundlegende Anzeigetypen von HTML-Elementen: Block-Elemente (wie `<div>`, `<p>`, `<h1>`) erzeugen einen Zeilenumbruch und nehmen die volle verfügbare Breite ein. Inline-Elemente (wie `<span>`, `<a>`, `<em>`) fügen sich in den Textfluss ein ohne Zeilenumbruch.     |

## CSS-Grundlagen

| Begriff                    | Erklärung                                                                                                                                                                                                              |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **CSS**                    | Cascading Style Sheets - Sprache zur Gestaltung von HTML-Dokumenten. CSS definiert, wie Elemente auf dem Bildschirm aussehen sollen (Farben, Schriften, Abstände, Layout).                                             |
| **Selektor**               | Teil einer CSS-Regel, der bestimmt, auf welche HTML-Elemente die Stile angewendet werden. Kann Elementnamen (`p`), Klassen (`.note`), IDs (`#header`), Attribute oder Kombinationen davon enthalten.                   |
| **Eigenschaft (Property)** | Gestaltungsmerkmal, das durch CSS definiert wird, wie `color` (Textfarbe), `font-size` (Schriftgröße), `margin` (Außenabstand), `padding` (Innenabstand) oder `border` (Rahmen).                                       |
| **Wert (Value)**           | Konkrete Ausprägung einer CSS-Eigenschaft, z.B. Farbwerte (`#f5f5f5`, `rgb(255,0,0)`), Größenangaben (`16px`, `1.2rem`, `50%`) oder Schlüsselwörter (`bold`, `italic`).                                                |
| **Box-Modell**             | Fundamentales CSS-Konzept, das jeden HTML-Baustein als "Box" mit Content (Inhalt), Padding (Innenabstand), Border (Rahmen) und Margin (Außenabstand) beschreibt. Wichtig für das Verständnis von Layoutberechnungen.   |
| **Flexbox**                | Modernes CSS-Layout-System für eindimensionale Anordnungen (Zeilen oder Spalten). Ermöglicht flexible, responsive Designs mit einfacher Ausrichtung, Verteilung und Reihenfolge von Elementen.                         |
| **CSS Grid**               | Leistungsstarkes zweidimensionales Layoutsystem in CSS, das sowohl Zeilen als auch Spalten gleichzeitig kontrolliert. Ideal für komplexe Rasterstrukturen und responsive Designs.                                      |
| **Responsive Design**      | Ansatz zur Webgestaltung, bei dem Layouts sich automatisch an verschiedene Bildschirmgrößen anpassen (vom Smartphone bis zum Desktop). Grundlegend für nutzerfreundliche Webseiten.                                    |
| **Media Queries**          | CSS-Technik, die es ermöglicht, unterschiedliche Stile für verschiedene Geräteeigenschaften zu definieren (z.B. Bildschirmbreite, Auflösung). Basis für responsive Designs: `@media (max-width: 600px) { ... }`        |
| **Spezifität**             | Regelsystem in CSS, das bestimmt, welche Stile Vorrang haben, wenn mehrere Regeln auf ein Element zutreffen. ID-Selektoren haben höhere Spezifität als Klassenselektoren, diese wiederum höher als Element-Selektoren. |
| **Vererbung**              | Mechanismus in CSS, bei dem bestimmte Eigenschaften (wie Schriftart oder Textfarbe) von Elternelemente an ihre Kindelemente weitergegeben werden, sofern nicht explizit überschrieben.                                 |

## JavaScript-Grundlagen

| Begriff             | Erklärung                                                                                                                                                                                                                                 |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **JavaScript**      | Programmiersprache für das Web, die Interaktivität ermöglicht. Mit JavaScript können Webseiten auf Benutzereingaben reagieren, Inhalte dynamisch ändern und mit Servern kommunizieren.                                                    |
| **Variablen**       | Speicherplätze für Daten in JavaScript. Werden mit `const` (unveränderlich), `let` (veränderlich) oder `var` (ältere Variante) deklariert. Variablen können Text, Zahlen, Objekte oder andere Datentypen enthalten.                       |
| **Funktionen**      | Wiederverwendbare Codeblöcke, die bestimmte Aufgaben ausführen. Können Parameter entgegennehmen und Werte zurückgeben. Ermöglichen eine strukturierte, modulare Programmierung.                                                           |
| **Arrow Functions** | Moderne, kompakte Schreibweise für Funktionen in JavaScript: `(parameter) => { /* Code */ }`. Bieten kürzere Syntax und behalten den `this`-Kontext bei.                                                                                  |
| **DOM**             | Document Object Model - Programmierschnittstelle, die HTML als Baumstruktur darstellt. Ermöglicht JavaScript, auf HTML-Elemente zuzugreifen und sie zu manipulieren (Inhalte ändern, Stile anpassen, Elemente hinzufügen oder entfernen). |
| **Event Listener**  | Mechanismus, der auf bestimmte Ereignisse (wie Klicks, Tastatureingaben, Laden der Seite) reagiert. Mit `element.addEventListener('click', function() { /* Reaktion */ })` werden Interaktionen ermöglicht.                               |
| **fetch API**       | Moderne JavaScript-Methode zum Abrufen von Ressourcen (wie Textdateien, JSON-Daten oder API-Anfragen) über das Netzwerk. Nutzt Promises für asynchrone Operationen und ersetzt das ältere XMLHttpRequest.                                 |
| **JSON**            | JavaScript Object Notation - leichtgewichtiges Datenformat, das für Menschen lesbar und für Maschinen leicht zu verarbeiten ist. Standardformat für den Datenaustausch im Web.                                                            |
| **async/await**     | Syntax-Erweiterung für asynchrone Programmierung in JavaScript, die komplexe Abläufe lesbarer macht. `async` kennzeichnet Funktionen, die Promises zurückgeben; `await` pausiert die Ausführung, bis ein Promise erfüllt ist.             |
| **Module**          | Organisationseinheiten in JavaScript, die Code in separate Dateien aufteilen. Mit `import` und `export` können Funktionen, Klassen und Variablen zwischen Dateien ausgetauscht werden, was die Wartbarkeit verbessert.                    |

## Webentwicklung mit Frameworks und Bibliotheken

| Begriff        | Erklärung                                                                                                                                                                                                                                              |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Bibliothek** | Sammlung vorgefertigter Funktionen und Komponenten, die spezifische Aufgaben erleichtern (z.B. jQuery für DOM-Manipulation, Chart.js für Diagramme). Bibliotheken fügen sich in bestehende Projekte ein, ohne die gesamte Architektur zu bestimmen.    |
| **Framework**  | Umfassendes System mit vorgegebener Struktur und Workflows für die Webentwicklung. Frameworks wie React, Vue oder Angular bieten komplette Lösungen für die Erstellung komplexer Anwendungen mit eigenen Konventionen und Paradigmen.                  |
| **jQuery**     | Verbreitete JavaScript-Bibliothek, die DOM-Manipulation, Event-Handling und Animation vereinfacht. Trotz modernerer Alternativen noch häufig in bestehenden Projekten zu finden. Die jQuery-Syntax beginnt typischerweise mit dem $-Zeichen.           |
| **Bootstrap**  | Populäres CSS-Framework, das fertige Komponenten und ein Raster-System für responsive Layouts bietet. Ermöglicht schnelle Entwicklung von ansprechenden Benutzeroberflächen ohne tiefgreifende CSS-Kenntnisse.                                         |
| **Chart.js**   | JavaScript-Bibliothek zur Erstellung interaktiver Diagramme und Visualisierungen. Bietet verschiedene Diagrammtypen (Balken, Linien, Torten) mit responsivem Design und Animation. Besonders geeignet für Datenvisualisierung in Forschungsprojekten.  |
| **D3.js**      | Leistungsstarke Bibliothek für datengesteuerte Visualisierungen. Ermöglicht hochgradig anpassbare, interaktive Grafiken durch direkte DOM-Manipulation. Komplexer als Chart.js, aber flexibler für spezialisierte oder ungewöhnliche Visualisierungen. |
| **Leaflet**    | Kompakte Open-Source-Bibliothek für interaktive Karten. Ideal für die Darstellung geografischer Daten, historischer Karten oder räumlicher Beziehungen in Forschungsprojekten. Unterstützt verschiedene Kartenebenen und Marker.                       |
| **GSAP**       | GreenSock Animation Platform - professionelle JavaScript-Bibliothek für hochwertige Webanimationen. Bietet präzise Kontrolle über Timing, Sequenzierung und komplexe Bewegungsabläufe für interaktive Präsentationen.                                  |
| **TimelineJS** | Spezialisiertes Open-Source-Tool für die Erstellung interaktiver, medienreicher Zeitleisten. Besonders geeignet für historische, kulturelle oder biografische Chronologien in geisteswissenschaftlichen Projekten.                                     |

## Allgemeine Webkonzepte

| Begriff                  | Erklärung                                                                                                                                                                                                                                               |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Frontend**             | Der Teil einer Website oder Webanwendung, den Benutzer direkt sehen und mit dem sie interagieren. Besteht aus HTML (Struktur), CSS (Design) und JavaScript (Interaktivität). Verantwortlich für die Benutzererfahrung und Präsentation von Inhalten.    |
| **Backend**              | Die serverseitige Komponente einer Webanwendung, die für Nutzer unsichtbar ist. Verarbeitet Anfragen, interagiert mit Datenbanken und führt Geschäftslogik aus. Programmiersprachen wie Python, PHP, Node.js oder Ruby kommen hier zum Einsatz.         |
| **Statische Website**    | Website ohne dynamische Serververarbeitung, bei der alle Seiten als fertige HTML-Dateien ausgeliefert werden. Einfach zu hosten, schnell und sicher. Ideal für Inhalte, die sich selten ändern oder keine Benutzerdatenverarbeitung erfordern.          |
| **Dynamische Website**   | Website, die Inhalte bei jeder Anfrage individuell generiert, oft unter Einbeziehung von Datenbanken. Ermöglicht personalisierte Inhalte, Benutzerkonten und komplexere Funktionen, erfordert jedoch serverseitige Programmierung.                      |
| **API**                  | Application Programming Interface - Schnittstelle zum Datenaustausch zwischen verschiedenen Softwaresystemen. Ermöglicht Webseiten, externe Dienste oder Datenquellen anzubinden (z.B. Bibliothekskataloge, Museumsdatenbanken, Forschungsdatenbanken). |
| **REST API**             | Representational State Transfer - standardisierter Architekturstil für Web-APIs mit definierten Endpunkten und HTTP-Methoden (GET, POST, PUT, DELETE). Weit verbreitet für den Datenaustausch zwischen Webanwendungen und Services.                     |
| **Client-Server-Modell** | Grundlegende Architektur des Webs: Der Client (Browser) sendet Anfragen an den Server, der diese verarbeitet und Antworten zurücksendet. Die Aufgabenteilung ermöglicht spezialisierte Optimierung auf beiden Seiten.                                   |
| **CRUD**                 | Create, Read, Update, Delete - die vier grundlegenden Datenbankoperationen. Beschreibt den Lebenszyklus von Datensätzen in vielen Anwendungen, von einfachen Notizsammlungen bis zu komplexen Forschungsdatenbanken.                                    |
| **HTTP/HTTPS**           | Hypertext Transfer Protocol (Secure) - Kommunikationsprotokolle für Datenübertragung im Web. HTTPS bietet verschlüsselte Verbindungen, was besonders für sensible akademische Daten oder Zugriffskontrollen wichtig ist.                                |
| **URL**                  | Uniform Resource Locator - die Adresse einer Webressource. Besteht aus Protokoll (https://), Domain (beispiel.de), Pfad (/sammlung/dokument) und optionalen Parametern (?jahr=1920). Wichtig für die Organisation digitaler Sammlungen.                 |

## Entwicklungswerkzeuge und Workflow

| Begriff           | Erklärung                                                                                                                                                                                                                                             |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **VS Code**       | Visual Studio Code - beliebter, kostenloser Code-Editor von Microsoft mit breiter Sprachunterstützung und Erweiterbarkeit. Bietet Syntaxhervorhebung, Autovervollständigung, integriertes Terminal und zahlreiche Extensions für die Webentwicklung.  |
| **Git**           | Verteiltes Versionskontrollsystem, das Änderungen an Dateien nachverfolgt. Ermöglicht die Zusammenarbeit mehrerer Personen an einem Codebase, das Experimentieren mit verschiedenen Lösungsansätzen und die Wiederherstellung früherer Versionen.     |
| **GitHub/GitLab** | Web-Plattformen für Git-Repositories mit zusätzlichen Kollaborationsfunktionen wie Issue-Tracking, Pull Requests und Projektmanagement. Bieten auch einfaches Hosting für Webprojekte (GitHub Pages, GitLab Pages).                                   |
| **DevTools**      | In Browser eingebaute Entwicklerwerkzeuge, die Inspektion und Debugging von Webseiten ermöglichen. Erlauben das Analysieren von HTML-Struktur, CSS-Stilen, JavaScript-Ausführung, Netzwerkanfragen und Performance.                                   |
| **Hard Refresh**  | Vollständiges Neuladen einer Webseite, das den Browser-Cache umgeht. Mit Tastenkombinationen wie Ctrl+F5 (Windows) oder Cmd+Shift+R (Mac) ausführbar. Wichtig bei der Entwicklung, um sicherzustellen, dass die neuesten Änderungen angezeigt werden. |
| **Inspektor**     | Teil der Browser-DevTools, der die HTML-Struktur und CSS-Stile einer Webseite anzeigt und die Bearbeitung im Browser ermöglicht. Hilfreich zum Experimentieren mit Layoutänderungen, bevor sie im Code implementiert werden.                          |
| **Console**       | JavaScript-Debugging-Werkzeug in Browser-DevTools, das Fehler anzeigt und das Ausführen von Code erlaubt. Über `console.log()` können Programmierer Werte zur Fehlerbehebung ausgeben und den Programmfluss nachvollziehen.                           |
| **Lighthouse**    | Automatisiertes Auditing-Tool von Google für Webseiten, das Performance, Zugänglichkeit, SEO und Best Practices prüft. Gibt konkrete Verbesserungsvorschläge und misst die Ladezeiten auf verschiedenen Geräten.                                      |
| **npm/yarn**      | Paketmanager für JavaScript, die Installation und Verwaltung von Bibliotheken und Tools vereinfachen. Verwenden eine zentrale Konfigurationsdatei (package.json) und ermöglichen reproduzierbare Entwicklungsumgebungen.                              |
| **Bundler**       | Tools wie Webpack oder Parcel, die viele separate Dateien (JavaScript, CSS, Bilder) zu optimierten Paketen zusammenfassen. Reduzieren die Anzahl der Netzwerkanfragen und ermöglichen moderne JavaScript-Features auch in älteren Browsern.           |

## Deployment und Hosting

| Begriff          | Erklärung                                                                                                                                                                                                                                                       |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Deployment**   | Prozess der Veröffentlichung einer Website oder Anwendung auf einem Server, sodass sie öffentlich zugänglich wird. Umfasst die Übertragung von Dateien, Konfiguration und ggf. Datenbankmigration.                                                              |
| **GitHub Pages** | Kostenloser Hosting-Dienst für statische Websites direkt aus GitHub-Repositories. Besonders einfach für Forschungsprojekte oder persönliche Websites, da keine separate Serverinfrastruktur benötigt wird. Unterstützt HTML, CSS, JavaScript und Jekyll.        |
| **Netlify**      | Moderne Hosting-Plattform für statische Websites mit fortgeschrittenen Funktionen wie automatischen Builds, Formularverarbeitung und einfacher Veröffentlichung direkt aus Git-Repositories. Bietet eine großzügige kostenlose Stufe für akademische Projekte.  |
| **Vercel**       | Hosting-Plattform, optimiert für moderne JavaScript-Frameworks wie Next.js oder React. Bietet globale Verteilung, automatische Vorschauen für jeden Git-Branch und serverlose Funktionen für einfache Backend-Logik.                                            |
| **Domain**       | Die eindeutige Adresse einer Website im Internet (z.B. "universität-wien.ac.at"). Besteht aus dem Namen und einer Top-Level-Domain (.com, .org, .edu). Kann bei Domain-Registraren gekauft und dann mit Hosting-Diensten verbunden werden.                      |
| **DNS**          | Domain Name System - übersetzt benutzerfreundliche Domainnamen in IP-Adressen, die Computer im Internet identifizieren. DNS-Einstellungen verknüpfen Ihre Domain mit Ihrem Webserver und konfigurieren Subdomain-Weiterleitungen oder E-Mail-Services.          |
| **SSL/TLS**      | Sicherheitsprotokolle, die verschlüsselte Verbindungen zwischen Browsern und Webservern ermöglichen (erkennbar am HTTPS und Schlosssymbol). Schützen übertragene Daten vor Abhören und sind besonders für Login-Bereiche oder sensible Forschungsdaten wichtig. |
| **CDN**          | Content Delivery Network - verteiltes Servernetzwerk, das Kopien Ihrer Website an verschiedenen geografischen Standorten speichert. Beschleunigt die Ladezeit für internationale Besucher und reduziert die Serverlast bei hohem Trafficaufkommen.              |

## Barrierefreiheit (a11y) und Best Practices

| Begriff                     | Erklärung                                                                                                                                                                                                                                                                           |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Barrierefreiheit (a11y)** | Gestaltungsprinzip, das sicherstellt, dass Websites für alle Menschen nutzbar sind, einschließlich Personen mit Behinderungen. "a11y" ist eine Abkürzung (Accessibility hat 11 Buchstaben zwischen A und Y). Umfasst technische, inhaltliche und designbezogene Aspekte.            |
| **ARIA**                    | Accessible Rich Internet Applications - Satz von HTML-Attributen, die zusätzliche Informationen für Screenreader und andere Hilfstechnologien bereitstellen. Verbessert die Navigation und das Verständnis komplexer Webkomponenten für Menschen mit Behinderungen.                 |
| **Alt-Text**                | Alternative Textbeschreibung für Bilder (über das `alt`-Attribut), die Screenreader vorlesen können. Besonders wichtig für historische Dokumente, Kunstwerke oder Diagramme in wissenschaftlichen Projekten. Sollte den Inhalt und die Bedeutung des Bildes präzise beschreiben.    |
| **Semantische Struktur**    | Verwendung von HTML-Elementen entsprechend ihrer Bedeutung (z.B. `<nav>` für Navigation, `<article>` für eigenständige Inhalte), anstatt alles mit generischen `<div>`-Elementen zu bauen. Verbessert Zugänglichkeit, SEO und Wartbarkeit.                                          |
| **Farbkontrast**            | Unterschied zwischen Text- und Hintergrundfarbe, gemessen in Kontrastverhältnis. Die WCAG-Richtlinien empfehlen mindestens 4.5:1 für normalen Text und 3:1 für große Überschriften. Entscheidend für Lesbarkeit, besonders für Menschen mit Sehschwächen.                           |
| **Tastaturnavigation**      | Möglichkeit, eine Website vollständig ohne Maus zu bedienen, nur mit Tastatur. Wichtig für Menschen mit motorischen Einschränkungen. Beinhaltet logische Tab-Reihenfolge, sichtbaren Fokus und Zugriff auf alle interaktiven Elemente.                                              |
| **Screen Reader**           | Hilfstechnologie, die Bildschirminhalte in Sprache oder Braille-Ausgabe umwandelt. Anwendungen wie JAWS, NVDA oder VoiceOver ermöglichen blinden oder sehbehinderten Menschen die Nutzung digitaler Inhalte. Websites sollten mit diesen Tools kompatibel sein.                     |
| **Responsive Images**       | Techniken zur Optimierung von Bildern für verschiedene Bildschirmgrößen und Auflösungen. Verwendet `srcset`- und `sizes`-Attribute oder das `<picture>`-Element, um unterschiedliche Bildversionen für verschiedene Geräte bereitzustellen. Verbessert Ladezeit und Datenverbrauch. |
| **Semantische Formulare**   | Zugängliche Gestaltung von Eingabeformularen mit korrekter Beschriftung (`<label>`), sinnvoller Gruppierung (`<fieldset>`), aussagekräftigen Fehlermeldungen und klarer Navigationsstruktur. Vereinfacht die Dateneingabe für alle Nutzer.                                          |

## Daten und Formate für Geisteswissenschaften

| Begriff         | Erklärung                                                                                                                                                                                                                                                                                                                    |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **CSV**         | Comma-Separated Values - einfaches, tabellarisches Dateiformat, in dem Werte durch Kommata getrennt sind. Leicht zu erstellen, zu bearbeiten (auch in Excel oder Google Sheets) und mit verschiedenen Programmiersprachen zu verarbeiten. Ideal für strukturierte Datensätze wie Bibliographien oder historische Zeitreihen. |
| **XML**         | Extensible Markup Language - hierarchisches, strukturiertes Dateiformat mit Tags ähnlich wie HTML. Ermöglicht komplexe, verschachtelte Datenstrukturen mit Attributen. Weit verbreitet in digitalen Geisteswissenschaften für Textauszeichnung und Datenaustausch zwischen Systemen.                                         |
| **JSON**        | JavaScript Object Notation - leichtgewichtiges, für Menschen lesbares Datenformat. Besteht aus Schlüssel-Wert-Paaren und unterstützt verschachtelte Strukturen. Ideal für Webanwendungen, da es direkt in JavaScript verarbeitbar ist und weniger Overhead als XML hat.                                                      |
| **TEI**         | Text Encoding Initiative - XML-basierter Standard zur Kodierung und Auszeichnung von Texten in den Geisteswissenschaften. Bietet spezialisierte Tags für literarische Texte, historische Dokumente, Manuskripte und kritische Editionen mit wissenschaftlichem Apparat.                                                      |
| **RDF**         | Resource Description Framework - Standard zur Beschreibung von Ressourcen im Semantic Web. Strukturiert Daten als Tripel (Subjekt-Prädikat-Objekt) und ermöglicht komplexe Beziehungsnetzwerke zwischen Entitäten. Grundlage für Linked Data in Archiven und Bibliotheken.                                                   |
| **Linked Data** | Ansatz zur Verknüpfung strukturierter Daten im Web durch standardisierte URIs und RDF. Ermöglicht die Vernetzung verschiedener Datenquellen (z.B. Personen, Orte, Konzepte) über Institutionsgrenzen hinweg. Wichtig für die interdisziplinäre Forschung und offene Wissenschaft.                                            |
| **IIIF**        | International Image Interoperability Framework - Standard für den Zugriff, die Anzeige und den Austausch von Bildern hoher Qualität. Ermöglicht Zoom, Rotation und Annotation von Bildern sowie die Integration von Bildressourcen aus verschiedenen digitalen Sammlungen.                                                   |
| **Zotero API**  | Programmierschnittstelle der freien Literaturverwaltungssoftware Zotero. Ermöglicht den programmatischen Zugriff auf bibliographische Daten, Sammlungen und Tags. Kann für die dynamische Einbindung von Literaturlisten in Forschungswebsites genutzt werden.                                                               |

## KI-Zusammenarbeit (Vibe Coding)

| Begriff                   | Erklärung                                                                                                                                                                                                                                                                                                            |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Vibe Coding**           | KI-gestützte Softwareentwicklung, bei der eine Person ein Problem in natürlicher Sprache beschreibt und die KI daraufhin funktionierenden Code erzeugt. Ermöglicht auch Nicht-Programmierern, komplexe digitale Projekte umzusetzen. Der Begriff wurde von Andrej Karpathy (ehemaliger KI-Leiter bei Tesla) geprägt. |
| **Promptengineering**     | Kunst und Wissenschaft, Anweisungen (Prompts) für KI-Systeme so zu formulieren, dass sie präzise und nützliche Antworten liefern. Umfasst die Verwendung klarer Fachbegriffe, spezifischer Anweisungen und strukturierter Anfragen.                                                                                  |
| **Promptotyping**         | Iterativer Prozess, bei dem durch schrittweise Verbesserung von Prompts ein digitaler Prototyp entwickelt wird. Beginnt oft mit konzeptionellen Fragen und wird zunehmend spezifischer, bis der gewünschte Code oder das gewünschte Design erreicht ist.                                                             |
| **Prompt-Vorlage**        | Standardisierte Struktur für KI-Anfragen zu bestimmten Aufgabentypen. Enthält Platzhalter für projektspezifische Details und sorgt für konsistente, effektive Kommunikation mit der KI. Hilfreich für wiederkehrende Aufgaben wie Datenvisualisierungen oder Komponenten.                                            |
| **Chain-of-Thought**      | Methode, bei der die KI durch mehrere logische Schritte geführt wird, um komplexe Probleme zu lösen. Der Nutzer bricht ein Problem in kleinere Teilaufgaben auf und lässt die KI diese nacheinander bearbeiten, wobei jeder Schritt auf dem vorherigen aufbaut.                                                      |
| **Saubere Code-Übergabe** | Praktiken zur Optimierung des von KI generierten Codes für die direkte Verwendung. Umfasst klare Formatierung, sinnvolle Kommentare, konsistente Namenskonventionen und die Organisation in kopierbare Blöcke, die direkt in ein Projekt übernommen werden können.                                                   |
| **KI-Debugging**          | Prozess, bei dem KI hilft, Fehler in Code zu identifizieren und zu beheben. Durch präzise Beschreibung des Problems, Fehlermeldungen und des erwarteten Verhaltens kann die KI gezielte Lösungsvorschläge anbieten.                                                                                                  |
| **Prompt-Iteration**      | Schrittweise Verfeinerung von KI-Anfragen basierend auf erhaltenen Antworten. Durch gezielte Rückmeldungen und Anpassungen wird die Qualität der KI-Ausgabe kontinuierlich verbessert. Ähnlich dem redaktionellen Prozess beim Schreiben.                                                                            |
| **KI-Code-Erklärung**     | Funktion von KI-Systemen, generierten Code in natürlicher Sprache zu erläutern. Besonders wertvoll für Lernende oder Fachexperten ohne tiefe Programmierkenntnisse, um Funktionsweise und Logik des Codes zu verstehen.                                                                                              |
| **Code-Refactoring**      | Umstrukturierung bestehenden Codes mit KI-Unterstützung, um Lesbarkeit, Effizienz oder Wartbarkeit zu verbessern, ohne die Funktionalität zu ändern. KI kann komplexe Codeabschnitte vereinfachen, Redundanzen beseitigen und moderne Best Practices einführen.                                                      |

## Datensicherheit und Datenschutz

| Begriff                     | Erklärung                                                                                                                                                                                                                                                                           |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **HTTPS**                   | Hypertext Transfer Protocol Secure - verschlüsselte Version des Webkommunikationsprotokolls. Schützt die Datenübertragung zwischen Browser und Server vor Abhören oder Manipulation. Für alle Websites empfohlen, besonders für solche mit Formularfeldern oder persönlichen Daten. |
| **GDPR/DSGVO**              | Datenschutz-Grundverordnung - EU-Verordnung zum Schutz personenbezogener Daten. Regelt Erhebung, Verarbeitung und Speicherung von Nutzerdaten. Für wissenschaftliche Projekte besonders relevant bei der Sammlung von Forschungsdaten, Interviews oder Umfragen.                    |
| **Cookie-Hinweis**          | Rechtlich vorgeschriebene Information über die Verwendung von Cookies oder ähnlichen Tracking-Technologien auf einer Website. Muss Nutzern die Möglichkeit geben, nicht-essentielle Cookies abzulehnen. Relevant für alle öffentlichen Websites in der EU.                          |
| **Content Security Policy** | Sicherheitsmechanismus, der festlegt, welche Ressourcen (Scripts, Stylesheets, Bilder) eine Webseite laden darf und von welchen Quellen. Schützt vor Cross-Site-Scripting (XSS) und anderen Injection-Angriffen. Wird als HTTP-Header oder Meta-Tag implementiert.                  |
| **SRI**                     | Subresource Integrity - Sicherheitsfeature, das überprüft, ob externe Ressourcen (wie JavaScript-Bibliotheken) verändert wurden, bevor sie ausgeführt werden. Verwendet Hashwerte zur Validierung. Wichtig bei Einbindung von Code aus CDNs oder anderen externen Quellen.          |
| **Anonymisierung**          | Prozess, bei dem personenbezogene Daten so verändert werden, dass Einzelpersonen nicht mehr identifizierbar sind. Essentiell für die Veröffentlichung von Forschungsdaten, Umfrageergebnissen oder historischen Dokumenten, die sensible Informationen enthalten könnten.           |
| **Firewall**                | Sicherheitssystem, das unerwünschten Netzwerkverkehr filtert und blockiert. Schützt Webserver vor unautorisierten Zugriffen und potenziellen Angriffen. Für die meisten statischen Forschungswebsites wird dies vom Hosting-Anbieter bereitgestellt.                                |
