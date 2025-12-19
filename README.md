# Robin A. Monecke - Portfolio Website

Ein minimalistisches, dark-mode Portfolio mit n8n Workflow-Visualisierung für GitHub Pages.

## ✨ Features

- **Automatic Dark Mode**: CSS Media Queries für systembasiertes Dark Mode
- **Monospace Typography**: JetBrains Mono Font für cleanen, technischen Look
- **Scroll Animations**: Smooth fade-in und slide-in Effekte beim Scrollen
- **Full-Height Sections**: Jede Section nutzt die volle Viewport-Höhe
- **Purple Accent**: Konsistente lila Akzentfarbe (#a855f7)
- **n8n Workflow**: Interaktive Visualisierung des B2B Cross-Selling Workflows
- **Responsive Design**: Vollständig optimiert für Desktop, Tablet und Mobile

## 🚀 Quick Deploy zu GitHub Pages

### Schritt 1: Repository erstellen
```bash
# Erstelle ein neues Repository mit dem Namen: username.github.io
# (ersetze 'username' mit deinem GitHub Username)
```

### Schritt 2: Dateien hochladen
1. Gehe zu deinem neuen Repository
2. Klicke auf "Add file" → "Upload files"
3. Lade die `index.html` Datei hoch
4. Committe die Änderung

### Schritt 3: GitHub Pages aktivieren
1. Gehe zu Repository Settings
2. Scrolle zu "Pages" im Seitenmenü
3. Unter "Source" wähle: Branch `main` und `/root`
4. Klicke "Save"
5. Deine Website ist live unter: `https://username.github.io`

## 📝 Anpassungen

### Workflow austauschen

**Der Workflow wird aus einer separaten `workflow.json` Datei geladen!**

So ersetzt du den Beispiel-Workflow mit deinem eigenen:

1. **Exportiere deinen Workflow aus n8n**
   - Öffne deinen Workflow in n8n
   - Klicke auf das Menü (⋮)
   - Wähle "Download" oder "Copy to Clipboard"
   - Speichere die Datei als `workflow.json`

2. **Ersetze die workflow.json Datei**
   - Lösche die Beispiel-`workflow.json` Datei
   - Lade deine eigene `workflow.json` Datei hoch
   - Stelle sicher, dass die Datei im **gleichen Verzeichnis** wie `index.html` liegt

3. **Struktur für GitHub Pages**
   ```
   repository/
   ├── index.html
   └── workflow.json    ← Muss im gleichen Verzeichnis sein!
   ```

**Wichtig**: Beide Dateien müssen im Root-Verzeichnis deines Repositories liegen, damit GitHub Pages sie richtig lädt.

### Beispiel aus deinem Repository verwenden

Du kannst deine Workflow-Datei direkt von deinem Repository kopieren:
```bash
# Von deinem b2b-cross-selling-ai Repository
cp "n8n-workflows/AI Product Manager - Prototyp V5.json" workflow.json
```

Oder direkt von GitHub herunterladen und umbenennen in `workflow.json`.

### Farben anpassen

In der `<style>` Sektion, ändere die CSS-Variablen:

```css
:root {
    --purple: #a855f7;        /* Haupt-Akzentfarbe */
    --purple-dark: #7c3aed;   /* Dunklere Variante */
    --purple-light: #c084fc;  /* Hellere Variante */
}
```

### Inhalte anpassen

Die Website ist in Sections unterteilt:

- **Hero** (`#hero`): Hauptüberschrift und CTAs
- **About** (`#about`): Über mich und Skills
- **Project** (`#project`): n8n Workflow und Projektdetails
- **Experience** (`#experience`): Timeline mit Berufserfahrung
- **Contact** (`#contact`): Kontaktinformationen

Einfach die entsprechenden HTML-Bereiche bearbeiten.

## 🎨 Design Philosophy

### Monospace Typography
Verwendet **JetBrains Mono** für einen cleanen, code-artigen Look. Die Font wird von Google Fonts geladen.

### Automatic Dark Mode
```css
@media (prefers-color-scheme: dark) {
    /* Dark mode styles */
}
```
Das Dark Mode wird automatisch basierend auf den System-Einstellungen aktiviert.

### Scroll Animations
Elemente werden beim Scrollen animiert durch Intersection Observer API:
- `.fade-in` - Fade von unten
- `.slide-in-left` - Slide von links
- `.slide-in-right` - Slide von rechts

### Full Viewport Sections
Jede Section nutzt `min-height: 100vh` für volle Bildschirmhöhe.

## 📱 Responsive Breakpoints

```css
@media (max-width: 768px) {
    /* Mobile styles */
}
```

Mobile Navigation klappt automatisch ein und kann über den Hamburger-Button geöffnet werden.

## 🛠 Technische Details

### Dependencies
- **n8n Demo Component**: Für Workflow-Visualisierung
- **JetBrains Mono**: Monospace Font
- **Vanilla JS**: Keine zusätzlichen Frameworks

### Browser Support
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

### Performance
- Minimale externe Dependencies
- CSS Media Queries für Dark Mode (kein JS)
- Lazy-loaded n8n Component
- Optimiert für schnelles Laden

## 📦 Projekt-Struktur

```
portfolio/
├── index.html          # Haupt-Website (Single Page)
├── workflow.json       # Dein n8n Workflow (wird dynamisch geladen)
└── README.md          # Diese Datei
```

**Wichtig für GitHub Pages**: Beide `index.html` und `workflow.json` müssen im Root-Verzeichnis deines Repositories liegen!

## 🔗 Links & Resources

- **GitHub Repo**: [b2b-cross-selling-ai](https://github.com/robinaaron/b2b-cross-selling-ai)
- **n8n Documentation**: [docs.n8n.io](https://docs.n8n.io/)
- **n8n Demo Component**: [npm package](https://www.npmjs.com/package/@n8n_io/n8n-demo-component)

## 💡 Tipps

### SEO Optimierung
Füge Meta-Tags in `<head>` hinzu:
```html
<meta name="description" content="Robin A. Monecke - Digital Product Manager & Automation Engineer">
<meta name="keywords" content="n8n, automation, digital product management, AI">
<meta property="og:title" content="Robin A. Monecke - Portfolio">
<meta property="og:description" content="AI-Augmented Product Delivery & Workflow Automation">
```

### Weitere Workflows hinzufügen
Dupliziere einfach den `.workflow-container` Bereich:
```html
<div class="workflow-container fade-in">
    <div class="workflow-title">Zweiter Workflow</div>
    <n8n-demo workflow='{"nodes":[...]}' frame="true"></n8n-demo>
</div>
```

### Custom Domain
1. Erstelle eine Datei namens `CNAME` im Repository
2. Füge deine Domain hinzu (z.B. `robin-monecke.com`)
3. Konfiguriere DNS bei deinem Domain-Provider

## 🐛 Troubleshooting

**Workflow wird nicht angezeigt?**
- Prüfe, ob `workflow.json` im gleichen Verzeichnis wie `index.html` liegt
- Öffne die Browser-Konsole (F12) für Fehlermeldungen
- Stelle sicher, dass die `workflow.json` Datei valides JSON enthält
- Teste die JSON-Validität auf [jsonlint.com](https://jsonlint.com)
- Bei GitHub Pages: Beide Dateien müssen committed und gepusht sein

**"Failed to load workflow.json" Fehler?**
- Stelle sicher, dass beide Dateien im Root-Verzeichnis liegen
- Bei lokaler Entwicklung: Verwende einen lokalen Webserver (nicht `file://`)
  ```bash
  # Python 3
  python -m http.server 8000
  # Dann öffne: http://localhost:8000
  ```

**Workflow lädt zu langsam?**
- Große Workflows (>1MB) können länger brauchen
- Die Ladeanimation zeigt an, dass der Workflow geladen wird
- Warte bis zu 5 Sekunden nach dem Laden der Seite

**Dark Mode funktioniert nicht?**
- Prüfe System-Einstellungen (Dark Mode aktiviert?)
- Teste in verschiedenen Browsern
- CSS Media Query Support prüfen

**Mobile Navigation klappt nicht auf?**
- JavaScript-Fehler in der Konsole prüfen
- Browser-Cache leeren

## 📄 Lizenz

Frei zur persönlichen und kommerziellen Nutzung.

## 🤝 Kontakt

**Robin A. Monecke**
- Email: aaron.monecke@outlook.de
- GitHub: [@robinaaron](https://github.com/robinaaron)

---

Viel Erfolg mit deinem Portfolio! 🚀
