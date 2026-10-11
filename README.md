# Schaltschrankbau Landing

SEO-orientierte B2B-Landingpage für Schaltschrankbau, Lohnfertigung und Serienfertigung in Mannheim.

**Status: Entwurf, nicht veröffentlichungsreif.** Der bestehende Webauftritt und die Domain werden nicht automatisch verändert.

## Stack

- Astro 7, statische Ausgabe (kein SSR und keine Datenbank)
- TypeScript für das kleine Formular-Skript
- Responsive CSS, ohne UI-Framework, ohne Cookies/Tracking in dieser Version
- Cloudflare Pages via GitHub-Integration (geplant)
- HTML-Metadaten, Canonicals, JSON-LD, Sitemap, robots.txt

## Lokal starten

```bash
npm install
npm run dev
npm run build
```

Node.js >= 22.12 verwenden.

## Cloudflare Pages

- GitHub-Repository: `AlekseiDudchenko/schaltschrankbau-landing`
- Produktionsbranch: `main`
- Build-Befehl: `npm run build`
- Output-Verzeichnis: `dist`

Cloudflare-Projekt und Domain erst nach Freigabe verbinden.

## Anfrageformular

Das Formular öffnet derzeit nur den lokalen Mail-Client mit vorausgefüllten Angaben an `vertrieb@mp-schaltanlagen.de`. Es gibt **keine** Serverübertragung, keine Datei-Uploads und keine garantierte erfolgreiche Zustellung. Für eine spätere echte Web-Anfrage sind Datenschutz, Spam-Abwehr, sicherer Dateitransfer und ein E-Mail-Zustelldienst gesondert zu implementieren.

## Launch-Checkliste / Blocker

- [ ] Offiziellen Betriebsnamen und geplanten Marketing-Brand festlegen; Markenrechte prüfen
- [ ] **Aktuelle ladungsfähige Anschrift bestätigen:** bisherige Impressum-Adresse weicht von genannter Adresse Mannheim U6, 3 ab
- [ ] Angaben zu USt-IdNr., Betreiber und Datenschutztext verbindlich prüfen
- [ ] **Rechtsseiten sind derzeit nur Entwürfe und ausdrücklich NICHT freigegeben**
- [ ] Leistungsmerkmale und eventuelle Zertifizierungen mit dem Inhaber prüfen
- [ ] Technische Illustrationen durch echte Produkt- und Fertigungsfotos ersetzen
- [ ] Datenschutzkonforme Anfrageform oder Mailto-Variante endgültig entscheiden
- [ ] Canonical, Sitemap, Domain und ggf. Redirects an die tatsächliche Domain anpassen
- [ ] Cloudflare-Git-Integration einrichten, Build testen und Produktionsdomain erst danach umschalten
- [ ] Search Console verbinden, Conversion-Ziele definieren

## Seiten

- `/` — Hauptlandingpage
- `/schaltschrankbau-lohnfertigung/` — individuelle SEO-Seite für Fertigung nach Schaltplan
- `/impressum/` — **Entwurf, vor Launch zu vervollständigen**
- `/datenschutz/` — **Entwurf, vor Launch rechtlich zu prüfen**
