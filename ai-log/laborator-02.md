# Laboratorul 2: AI log

## Instrumente
- Claude (Claude Code), modelul Claude Opus 5.5

## Conversații
- Sesiune Claude Code în VS Code, 19 oct. 2026 (Claude Code nu are link de partajare): citirea enunțului din PDF, pasul 3, exercițiile 1–3, explicații despre cod, publicarea pe GitHub.

## Cereri principale
### 1. Prima încercare, anulată
- Am cerut: rezolvarea laboratorului pornind doar de la PDF.
- Am primit: un proiect Vite nou, creat în `city-explorer/app`, cu toate exercițiile.
- Ce am schimbat sau respins: am cerut undo, iar folderul a fost șters. Proiectul Vite îl creasem deja eu, în `TW-laborator/app`, cu pașii 1 și 2 din enunț.

### 2. Pasul 3 (curățenia)
- Am cerut: pasul 3 din enunț, în proiectul meu.
- Am primit: directoarele `src/data`, `src/utils` și `src/api`, `App.jsx` cu titlul „City Explorer”, `App.css` și `index.css` golite, `main.jsx` cu `console.log('L2 Merge!')`. `src/assets` și `public/icons.svg` le ștersesem deja eu.
- Ce am schimbat sau respins: le-am păstrat.

### 3. Exercițiile 1–3
- Am cerut: restul laboratorului.
- Am primit: `data/destinatii.js` (lista din enunț), `utils/destinatii.js` (cele 9 funcții de la Ex. 1 și Ex. 2), `api/orase.js` (`fetchUsers` și `fetchUserById`, cu verificarea `response.ok`) și afișările din `main.jsx`, cu prefixul `L2`. Rezultatele au fost comparate cu cele din enunț, iar `npm run lint` și `npm run build` au trecut.
- Ce am schimbat sau respins: le-am păstrat. Pentru punctul 3c, în cod rămâne apelul cu `1`, iar un comentariu arată unde se pune temporar `999`.

### 4. Explicații
- Am cerut: cum deschid consola, ce face fiecare exercițiu, dacă `destinatii` e o listă, ce face fiecare funcție din `utils/destinatii.js` și din `api/orase.js`.
- Am primit: explicații pas cu pas, cu valorile intermediare pe lista de destinații (de exemplu cum acumulează `reduce` la `totalZile` și la `numarPeTara`).

### 5. GitHub
- Am cerut: urcarea pe GitHub.
- Am primit: commit cu folderul `app/` (fără `node_modules`) și push pe `main`.

## Ce am învățat / ce nu a mers
- `map` întoarce o listă de aceeași lungime, `filter` una mai scurtă sau egală, iar `reduce` o singură valoare. La `reduce` trebuie dată valoarea de pornire (`0` sau `{}`).
- `sort` modifică lista pe care este aplicat, de aceea se sortează o copie: `[...list]`.
- Ca să modific un element fără să stric lista, fac un obiect nou cu `{ ...d, vizitat: !d.vizitat }`, iar celelalte elemente rămân aceleași obiecte. Testul `destinatii[1] === dupaMarcare[1]` arată `true`.
- `fetch` nu consideră 404 o eroare, așa că verific `response.ok` și arunc eroarea cu `throw`. Ea ajunge în `catch`.
- Consola se deschide cu F12 sau cu Ctrl + Shift + J. Pe laptopul ASUS, F12 poate cere și tasta Fn.
