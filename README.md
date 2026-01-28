# Website Generator – Kundenformular → SEO- & Google-fertige Website

Dieses Projekt ist ein **vollautomatisierter Website-Generator**, der aus einem **kundenfreundlichen Online-Formular** eine **produktionsreife, SEO-optimierte Website** erstellt.

Ziel:
- Kunden geben **alles selbst online ein**
- **Nichts Wichtiges kann vergessen werden** (SEO, Google, Rechtliches)
- Du erhältst am Ende eine **saubere, sofort deploybare Website**
- Das System ist **beliebig reproduzierbar** für weitere Kunden

---

## 🔁 Gesamt-Workflow

1. Kunde füllt das Online-Formular aus  
2. Formular exportiert ein `intake.zip`  
3. Lokaler Build rendert die Website  
4. Deployment (z. B. GitHub Pages)  
5. Google-Einbindung (Search Console & Google Business)

---

## 🧩 Funktionsübersicht

### 1️⃣ Kunden-Online-Formular (Intake)

Das Formular ist so aufgebaut, dass der Kunde **geführt** wird und bei jedem Feld **Hilfen & Empfehlungen** erhält.

#### Basisdaten
- Firmenname
- Domain
- Kategorie (Google Business)
- Adresse (Straße, PLZ, Ort)
- Telefon & E-Mail
- Google-Maps-URL
- Einzugsgebiet (Orte)

---

### 2️⃣ SEO-Eingaben (mit Live-Empfehlungen)

Der Kunde trägt SEO-Daten ein, mit **Live-Zeichenzähler & Warnungen**:

| Feld | Empfehlung |
|---|---|
| SEO-Title | **50–60 Zeichen** |
| Meta-Description | **150–160 Zeichen** |
| Canonical-URL | Vollständige URL |

➡️ **SEO-Felder sind Pflicht** – Export ist sonst nicht möglich.

---

### 3️⃣ Google-Business-Daten

Alle relevanten Google-Business-Informationen werden strukturiert abgefragt:

- Beschreibung (**250–750 Zeichen empfohlen**)
- Kategorie
- Öffnungszeiten **pro Wochentag**
- Service-Gebiete (strukturiert)
- Attribute (frei definierbar)

➡️ Zusätzlich wird automatisch eine `google-business.txt` erzeugt (Copy & Paste).

---

### 4️⃣ Bild-Uploads (mit festen Vorgaben)

Alle Uploads werden geprüft (Dateigröße & Format).

| Bild | Empfohlene Größe | Max. Größe |
|---|---|---|
| Logo | SVG empfohlen | 300 KB |
| OG-Image | 1200×630 px | 500 KB |
| Hero-Bild | 1600×900 px | 800 KB |
| Service-Bild | frei (WebP/JPG/PNG) | 500 KB |

➡️ Pro Service wird **ein eigenes Bild** hochgeladen  
➡️ Automatisch richtig der Unterseite zugeordnet

---

### 5️⃣ Leistungen (Services) – dynamisch

- Services per **➕ Button** hinzufügen
- **Drag & Drop Reihenfolge**
- Pro Service:
  - Name → URL-Slug
  - Menü-Bezeichnung
  - Teaser & Lead-Text
  - Content
  - Eigenes Bild
  - Optional: SEO-Title & Description
  - **FAQ (bis zu 3 Fragen)**

➡️ Für jeden Service (Leistungen) entsteht automatisch:

Mit:
- Meta-Tags
- Canonical
- Breadcrumb-Schema
- FAQ-Schema (falls FAQs vorhanden)

---

### 6️⃣ Automatische Seiten

Je nach Auswahl werden gebaut:

- Startseite
- Leistungen-Übersicht
- Über uns
- Kontakt
- FAQ (global, aus allen Service-FAQs)

**FAQ-Speziallogik**
- Alle FAQs aller Services werden gesammelt
- Eine zentrale `faq.html` entsteht
- Zusätzliches `FAQPage`-Schema für Google

---

### 7️⃣ Menü- & Footer-Logik

Der Kunde kann im Formular:

#### Menü ausblenden
- Leistungen
- Über uns
- Kontakt
- FAQ

#### Seiten komplett deaktivieren
- Seite wird **nicht gebaut**
- Nicht in `sitemap.xml`
- Menü **und Footer** passen sich automatisch an

➡️ **Keine toten Links möglich**

---

### 8️⃣ Rechtliches (DSGVO & Impressum)

- Vollständig als Templates umgesetzt
- **Alle festen Daten ersetzt** durch Kundendaten
- Automatische Befüllung aus:
  - Firmenname
  - Adresse
  - Kontakt
- Optional: USt-ID, Registerangaben

⚠️ Hinweis integriert: *Vorlage – rechtlich prüfen lassen*

---

### 9️⃣ Build- & Generator-System

**Input**
- `intake.zip` (aus dem Formular)

**Befehle**
```bash
npm install
npm run validate
npm run build -- --intake intake.zip
