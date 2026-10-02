# Raffaele Feola — Sito personale e portfolio

Sito personale multipagina sviluppato in HTML5, CSS3 e Sass, senza una riga di JavaScript scritta a mano.

**[→ rafeola.github.io](https://rafeola.github.io/)**

> Progetto del modulo *HTML e CSS* del percorso Full Stack Development & AI Agents di [Start2Impact University](https://www.start2impact.it/).

---

## Le pagine

| Pagina | Contenuto |
|---|---|
| `index.html` | Home: posizionamento, tre aree di competenza, numeri, progetti in evidenza |
| `chi-sono.html` | Il percorso in cinque capitoli e la sezione sugli AI Agents |
| `progetti.html` | Cinque progetti con contesto, soluzione e risultato |
| `cv.html` | Curriculum completo in HTML, con download del PDF |
| `contatti.html` | Modulo di contatto e collegamenti |
| `grazie.html` | Pagina di conferma dopo l'invio del modulo |

## Scelte tecniche

**Sass con partial.** Il CSS non si scrive a mano: `scss/` contiene un file per area (variabili, base, navigazione, hero, componenti, footer) e il compilatore genera `css/style.css`. Cambiare la palette dell'intero sito significa modificare poche righe in `_variables.scss`.

**Nessun JavaScript.** Il menu mobile è costruito con una checkbox nascosta e il selettore `:checked`; il modulo di contatto invia i dati a un endpoint esterno tramite il solo attributo `action`. Il sito funziona identico anche con gli script disabilitati.

**Due sistemi di griglia.** Il layout delle card e dei progetti usa **CSS Grid nativo**; le pagine CV e Contatti usano la **griglia di Bootstrap 5**. La gutter di Bootstrap è azzerata sotto i 768px per evitare lo scorrimento orizzontale dentro un contenitore a padding fluido.

**Tipografia fluida.** Una sola dichiarazione `clamp()` per livello copre l'intero intervallo da 320px a desktop: nessun salto fra i breakpoint.

**Nebbia animata in solo CSS.** Tre sfere sfocate con durate diverse (27s, 34s, 41s) che non tornano mai in sincrono, così il movimento non appare ciclico. Disattivate per chi ha impostato la riduzione del movimento.

**Accessibilità.** Markup semantico, `aria-current` sulla voce di menu attiva, contorno di focus visibile per la navigazione da tastiera, immagini decorative escluse dalla lettura assistiva e `@media (prefers-reduced-motion: reduce)` che ferma ogni animazione.

**Prestazioni.** Immagini ridimensionate e compresse, attributi `width` e `height` dichiarati per evitare il salto del layout durante il caricamento, `loading="lazy"` sulle immagini sotto la piega.

## Struttura

```
.
├── index.html · chi-sono.html · progetti.html · cv.html · contatti.html · grazie.html
├── css/
│   └── style.css          ← generato: non modificare a mano
├── scss/
│   ├── style.scss         ← punto d'ingresso
│   ├── _variables.scss    ← colori, tipografia, spaziature, breakpoint
│   ├── _base.scss         ← reset, tipografia, nebbia di sfondo
│   ├── _nav.scss          ← navigazione sticky e menu mobile
│   ├── _hero.scss         ← intestazioni e pulsanti
│   ├── _components.scss   ← card, progetti, competenze, CV, moduli
│   └── _footer.scss
├── img/
│   ├── favicon-rf-32.png
│   ├── apple-touch-icon-rf-180.png
│   └── (foto, screenshot, immagine Open Graph)
└── files/
    └── CV_Raffaele_Feola.pdf
```

## Lavorare sul progetto

Il CSS va modificato in `scss/`, mai in `css/style.css`, che viene rigenerato a ogni compilazione.

```bash
# con Dart Sass installato
sass --watch scss/style.scss css/style.css
```

In alternativa, l'estensione **Live Sass Compiler** per VS Code compila automaticamente a ogni salvataggio.

## Autore

**Raffaele Feola** — in formazione su Full Stack Development & AI Agents presso Start2Impact University.

[LinkedIn](https://www.linkedin.com/in/raffaele-feola-3a0aa422b) · [GitHub](https://github.com/Rafeola)
