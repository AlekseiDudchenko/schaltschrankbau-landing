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

## Cloudflare Pages: nur Preview bis zur Launch-Freigabe

`main` enthält derzeit nur README.md (Commit `09edc5e`), nicht die Astro-App.
Ein Build von `main` mit `npm run build` scheitert deshalb mit ENOENT für
`/opt/buildhome/repo/package.json`. Die App liegt in Draft-PR #1 auf
`feat/astro-seo-landing-v1`. Weder den PR mergen noch diese Feature-Branch
zur Production branch machen, um den Fehler zu umgehen.

Im bestehenden Pages-Projekt unter **Settings > Build > Branch control > Edit**:

| Einstellung | Wert |
| --- | --- |
| Production branch | `main` |
| Enable automatic production branch deployments | **Aus** |
| Preview branch | **Custom branches** |
| Include Preview branches | `feat/astro-seo-landing-v1` (ohne `*`) |
| Exclude Preview branches | Leer |

Speichern. Unter **Settings > Build > Build configuration**:

| Einstellung | Wert |
| --- | --- |
| Framework preset | Astro (falls angezeigt) |
| Build command | `npm run build` |
| Build output directory | `dist` |
| Root directory | Leer (Repository-Wurzel) |
| Preview environment variable | `NODE_VERSION=22` |

Die Git-Integration installiert die npm-Abhängigkeiten automatisch. Keine
Wrangler-Konfiguration und keine Verschiebung in ein Unterverzeichnis nötig.
Nach dem Speichern einen Commit auf `feat/astro-seo-landing-v1` pushen.
Unter **Deployments** muss der neue Build **Preview**, die Feature-Branch und
den neuen Commit anzeigen. Nicht den fehlgeschlagenen `main`-Build wiederholen:
ein Retry baut weiterhin dessen alten Commit.

Den Preview-Link des erfolgreichen Deployments verwenden. Preview ist standardmäßig
öffentlich; Cloudflare setzt für Preview `X-Robots-Tag: noindex`. Das ist kein
Zugriffsschutz. Bei Bedarf **Settings > General > Preview access > Restrict previews**
mit Cloudflare Access konfigurieren. Keine Produktionsdomain verbinden.

Production erst nach Abschluss der Launch-Checkliste, ausdrücklicher Freigabe
und Merge nach `main` aktivieren. Draft-Status allein verhindert keine Deployments;
der Schutz erfolgt durch die Branch-Einstellungen.

Dokumentation: [Branch controls](https://developers.cloudflare.com/pages/configuration/branch-build-controls/),
[Preview deployments](https://developers.cloudflare.com/pages/configuration/preview-deployments/).

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
