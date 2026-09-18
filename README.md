# Die Angebotsseite `future-space.plinyoo.com`

**Eine Datei, keine Anwendung.** Kein Bauvorgang, keine Abhängigkeiten, kein
`npm install`. Reines HTML mit eingebautem Stil — was hier liegt, ist genau
das, was der Besucher bekommt.

Gebaut am 18.09.2026 nach **Aufbau A („Drei Türen")**, den Heiko am selben Tag
entschieden hat. Vorlage:
`docs/features/sources/entwurf-future-space-angebotsseite.md` (Gestalter,
Stand `eae082d0`) und `entwurf-future-space-seite.md` (`39e34261`).

## Inhalt dieses Ordners

| Datei | Zweck |
|---|---|
| `index.html` | die Seite |
| `404.html` | vier Zeilen und ein Weg zurück — **absichtlich keine Kopie** von `index.html` |
| `robots.txt` | `Disallow: /` — die Fassung ist nicht abgestimmt und soll nicht gefunden werden |
| `.nojekyll` | schaltet Jekyll ab (BUG-0060: Jekyll verschluckt alles, was mit `_` beginnt) |

**Kein `CNAME`, kein Workflow — und das ist keine Auslassung.**

## Warum sie von hier nicht ausgeliefert wird

Ein Repo hat **eine** Pages-Seite und **einen** CNAME. Diese Seite hier gehört
`spoonup.me` (`.github/workflows/webseite-spoonup.yml` mit
`actions/deploy-pages`, plus `webseite-spoonup/CNAME`). Ein zweiter CNAME in
diesem Repo könnte `future-space.plinyoo.com` gar nicht beanspruchen, ohne
`spoonup.me` abzuräumen — und genau dieser Zustand ist der Gegenstand von
`apps/web/tests/bug-0135-ein-repo-je-domain.spec.ts`.

> **Die Seite bekommt ein eigenes Repo.** Vorschlag des Gestalters:
> `roadrider42/future-space`, Pages direkt aus `main`, `CNAME` =
> `future-space.plinyoo.com` — so wie `roadrider42/bplus` es mit
> `bplus.plinyoo.com` macht. **Ob ein weiteres Repo angelegt wird, entscheidet
> Heiko.** Bis dahin liegt der Ordner hier und wird nicht ausgeliefert.

Wer ihn umzieht, nimmt die vier Dateien mit und legt den `CNAME` **dort** an,
nicht hier.

## Was noch fehlt

**Der Wortlaut.** Jede Stelle mit noch nicht redaktionell entschiedenem Text
trägt `data-wortlaut="<name>"`. Das ist eine Liste zum Abarbeiten:

```
grep -o 'data-wortlaut="[^"]*"' index.html | sort -u
```

Die Markierung fällt beim Ersetzen mit weg — sie ist kein Gestaltungsmittel.

**Zwei Abschnitte fehlen mit Grund, nicht aus Vergessen:**

- **Kein Zahlenabschnitt, kein Zitatabschnitt.** Für Future Space ist keine
  Zahl gemessen, und es gibt kein Zitat eines Menschen dort. Beides entfällt
  ersatzlos, nicht als leere Kachelreihe.
- **Keine Probe („So sieht eine Lerneinheit aus").** Ihre Bedingung ist
  bindend: nur mit einer echten Karte aus einem Future-Space-Thema samt
  Quellzeile. Am 18.09.2026 live nachgesehen: kein Thema mit „future" oder
  „space" im Namen (Gegenprobe: 12 Themen, 905 Karten sichtbar). Sobald eine
  Karte vorliegt, gehört der Abschnitt zwischen die drei Türen und „Was ihr
  behaltet"; die Stelle ist in `index.html` als Kommentar markiert.

## Die Fassungszeile hat eine Abnahmebedingung

Sie steht an zwei Stellen in `index.html` und in keiner Formatvorlage:
Titelbereich und Fuß. **Sie kommt weg, sobald die Inhalte abgestimmt sind** —
und die Kennung („Angebotsfassung 1") steigt bei jeder Überarbeitung. Eine
Fassungszeile, die sechs Wochen denselben Stand trägt, behauptet Pflege, die
nicht stattfindet.

## Was gemessen ist

Bei **390 × 844** (`scripts/analyse/future-space-390x844.mjs`, nicht
versioniert): die drei Publikumskarten stehen untereinander, nichts
abgeschnitten, kein seitliches Schieben, Schaltflächen 48 px, Fußverweise
44 px, alle Farbpaare über 4,5 : 1. Die Zahlen stehen in der Commit-Botschaft.

**Nicht gemessen:** die echte bplus-Seite. Sie liegt in
`~/1-Projekte-lokal/bplus`, und dieser Ordner ist von der Agentenschale aus
nicht lesbar. Alles, was hier „wie bei bplus" heißt, stammt aus Abschnitt 5 des
Entwurfs — der Gestalter hat dort mit Zeilennummern festgehalten, was in jener
Datei steht.
