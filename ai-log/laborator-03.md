# Laboratorul 3: AI log

## Instrumente
- Claude (Claude Code), modelul Claude Opus 5.5

## Conversații
- Sesiune Claude Code, 2 nov. 2026 (Claude Code nu are link de partajare): recapitularea laboratorului 2, citirea enunțului din PDF, rezolvarea pas cu pas, cu verificare în browser după fiecare pas.

## Cereri principale
### 1. Mod de lucru
- Am cerut: rezolvarea laboratorului 3 pornind de la PDF.
- Am primit: o întrebare despre modul de lucru. Am ales „pas cu pas” și cerința suplimentară (ștergerea).

### 2. Secțiunile 3–4: prima componentă și props
- Am primit: `components/Rezumat.jsx` cu props `total`, `nevizitate`, `zile` și `App.jsx` care îl folosește cu valori fixe (6, 4, 18). `main.jsx` a rămas neschimbat.
- Ce am schimbat sau respins: le-am păstrat; am verificat în browser.

### 3. Exercițiul 1a–d: stilurile de bază, cardul și lista
- Am primit: `index.css` și `App.css` din enunț, `DestinatieCard.jsx` (clasa `card` / `card vizitat` cu ternar) și `ListaDestinatii.jsx` (`map` cu `key={destinatie.id}`, mesajul „Nu există nicio destinație.” pentru lista goală).
- Ce am schimbat sau respins: le-am păstrat.

### 4. Exercițiul 1e: cele 7 reguli CSS
- Am primit întâi doar indicii pentru fiecare selector; apoi am cerut să fie scrise regulile.
- Am primit: grila cu `repeat(auto-fit, minmax(200px, 1fr))`, stilurile cardului și `.card.vizitat` (verde), cu explicații pentru fiecare.
- Ce am schimbat sau respins: le-am păstrat; pagina arată ca în figura 7.

### 5. Exercițiul 2: rezumatul din stare și marcarea
- Am primit: lista pusă în `useState` în `App.jsx`, rezumatul calculat din stare cu `getNevizitate` și `totalZile`, `handleToggle` transmis ca `onToggle` prin `ListaDestinatii` până la butonul din card.
- Ce am schimbat sau respins: le-am păstrat; am verificat că rezumatul se schimbă la click.

### 6. Exercițiul 3 și cerința suplimentară
- Am primit: `FormularDestinatie.jsx` cu câmpuri controlate, `preventDefault`, validare, `crypto.randomUUID()`, `Number(zile)` și golirea câmpurilor; `handleAdd` și `handleDelete` în `App.jsx`; butonul „Șterge” pe fiecare card, cu regula CSS `.card button.sterge`.
- În plus față de enunț: `.trim()` la validare (un oraș format doar din spații nu se adaugă) și `type="number"` pe câmpul de zile.
- Ce am schimbat sau respins: le-am păstrat; am verificat adăugarea Sevillei și ștergerea.

### 7. Ordine în repo și GitHub
- Am primit: `.gitignore` și `README.md` mutate înapoi în rădăcina repo-ului, README completat cu laboratoarele 2 și 3, acest AI log și commit-ul.

## Ce am învățat / ce nu a mers
- O componentă este o funcție care întoarce JSX; apare pe pagină doar dacă un părinte o scrie ca etichetă, iar numele începe cu literă mare.
- Props vin de la părinte și nu se modifică în componentă. Ce se schimbă în timp stă în state și se schimbă doar prin funcția de actualizare.
- Ce se poate calcula din stare (rezumatul) nu se pune în stare separată.
- Datele coboară prin props, evenimentele urcă prin funcții primite tot ca props (`onToggle`, `onDelete`, `onAdd`).
- `onClick={() => onToggle(id)}` dă o funcție; `onClick={onToggle(id)}` ar apela-o la fiecare desenare.
- React observă schimbarea doar dacă primește o listă nouă; de aceea funcțiile din `utils` folosesc `map`, `filter` și spread.
- `key` trebuie să fie identificatorul, nu indicele din listă.
- `.card.vizitat` (fără spațiu) înseamnă un element cu ambele clase; `.card .vizitat` ar căuta un element în interiorul cardului.
- Un câmp controlat pornește cu `useState('')`, iar `event.preventDefault()` oprește reîncărcarea paginii la trimiterea formularului.
