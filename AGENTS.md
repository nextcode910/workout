# Fitness Tracker — App PWA

## Struttura progetto
- `index.html` — Single-file app (~2800 linee JS inline)
- `style.css` — CSS esterno con versioning
- `sw.js` — Service worker con cache versioning
- `manifest.json` — PWA manifest

## Comandi dev
- Apri `index.html` direttamente nel browser O usa server locale: `npx serve .`
- Nessun build system, nessun lint/typecheck

## Skills da usare
- `/caveman` — comunicazione compressa
- `/frontend-design` — design UI di qualità

## Architettura
- Vanilla JS, nessun framework
- State management: oggetto globale `state` in localStorage (`fitnessTracker_v5`)
- Programma caricato da `program.json` locale o GitHub Gist
- Log key: `${letter}_W${week}` (es. `A_W1`)

## Convenzioni stilistiche
- CSS custom properties: `--accent` (#e8ff3c), `--accent2` (#3cffb4), `--accent3` (#ff6b3c)
- Font: Bebas Neue (titoli), DM Sans (body)
- Material Icons via CDN Google Fonts

## Aggiornamenti PWA

### Come forzare aggiornamento cache

**style.css**: Rinomina con data-ora ad ogni modifica (es. `style_250425_1430.css`) e aggiorna il link in `index.html`

**sw.js**: Aggiorna `CACHE_VERSION` con stessa data-ora usata per style.css

**index.html**: Aggiorna versione nel link `style.css?v=YYYYMMDD_HHMM`

### Esempio workflow aggiornamento style
1. Modifica `style.css`
2. Rinomina file: `style.css` → `style_250425_1430.css`
3. In `index.html`: `<link href="style_250425_1430.css">`
4. In `sw.js`: `CACHE_VERSION = '250425_1430'`
5. In `sw.js`: Aggiungi `style_250425_1430.css` a `STATIC_ASSETS`
6. Elimina vecchi file style.css non più usati