# Film Gallery

A 3D interactive film photo gallery. Ring / Flat / Gallery modes with mouse repel, lightbox preview, and keyboard navigation.

## Setup

### 1. Add your photos

Put all your images inside the `images/` folder:

```
gallery/
├── index.html
├── images/
│   ├── 01.jpg
│   ├── 02.jpg
│   ├── 03.jpg
│   └── ...
```

### 2. Edit the photo list

Open `index.html` and find the `ITEMS` array near the top of the `<script>` block:

```js
const ITEMS = [
  { src: 'images/01.jpg', label: 'Tokyo — Night', sub: '35mm · Kodak 400' },
  { src: 'images/02.jpg', label: 'Rooftop View',  sub: '120 · Portra 800' },
  // add or remove entries to match your photos
];
```

- **src** — filename inside the `images/` folder
- **label** — photo title shown on hover and in lightbox
- **sub** — subtitle (film stock, location, date, etc.)

You can have any number of photos — just add or remove lines.

### 3. Deploy to Vercel

**Option A — Vercel CLI**
```bash
npm i -g vercel
cd gallery
vercel
```

**Option B — Vercel Dashboard (drag & drop)**
1. Go to [vercel.com](https://vercel.com) → New Project
2. Drag the entire `gallery/` folder into the browser
3. Click Deploy — done, you get a live URL instantly

No build step needed. This is plain HTML/JS.

## Interactions

| Action | Effect |
|--------|--------|
| Hover near cards | Push / repel effect (Ring mode) |
| Click card | Open fullscreen lightbox |
| Drag left/right | Rotate ring / scroll gallery |
| Scroll wheel | Same as drag |
| ← → arrow keys | Navigate in lightbox |
| Esc | Close lightbox |
| Click background | Pause / resume auto-spin |

## Customisation

All tunable constants are at the top of the `<script>` block:

```js
// Push effect radius and strength (Ring mode)
const PUSH_RADIUS = 130;
const PUSH_STR    = 75;

// Auto-spin speed
spinAngle += 0.0035; // increase for faster spin
```
