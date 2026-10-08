# Java III — Klinika e CSS

Ky projekt paraqet një afishe për Klubin e Debatit duke përdorur HTML dhe CSS.

## Çfarë është përdorur

- HTML5
- CSS të jashtëm
- Klasa CSS të ripërdorshme
- CSS variables
- Flexbox
- Responsive design
- Hover
- Focus-visible
- Box-sizing
- CSS specificity

## Afisha

Afisha përmban:

- Titullin e klubit të debatit
- Temën e debatit
- Datën dhe orën
- Vendin
- Përshkrimin
- Lidhjen për regjistrim
- Tri etiketa: Falas, Vende të kufizuara dhe Edhe online

## CSS Variables

Ngjyrat dhe hapësirat janë vendosur në `:root` si variabla CSS, për shembull:

```css
:root {
    --background: #f4f1e8;
    --text: #17263c;
    --accent: #0f766e;
}
