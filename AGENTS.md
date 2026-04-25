# Fitness Tracker — App PWA

## Struttura progetto
- `index.html` — Single-file app (HTML + CSS + JS inline, ~2800 linee)
- `sw.js` — Service worker per PWA offline
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