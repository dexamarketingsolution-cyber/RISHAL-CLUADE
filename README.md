# Rilshan Razik — Portfolio

A static, single-page portfolio. No build step, so it deploys to Vercel as-is.

## Folder

```
index.html              the whole site (HTML + CSS + JS)
favicon.svg
vercel.json             clean URLs + asset caching
assets/rilshan.jpg      portrait (taken from the CV)
assets/Rilshan-Razik-CV.pdf
assets/works/           put your project images here
```

## Deploy to Vercel

**Option A — drag and drop**
1. Go to vercel.com → Add New → Project.
2. Drag this whole folder in. Framework preset: **Other**. No build command, output directory `.` (root).
3. Deploy.

**Option B — CLI**
```
npm i -g vercel
cd rilshan-portfolio
vercel --prod
```

**Option C — GitHub**
Push the folder to a repo, then import the repo in Vercel (preset: Other).

To use your own domain (e.g. rilshangraphics.com): Vercel project → Settings → Domains.

## Add your real work

Open `index.html`, find `const WORKS = [` near the bottom. Each project looks like:

```js
{ id:"legal-social", title:"Legal social series", cat:"social", year:"2023–now",
  client:"Mashael Alsulaiti Law Firm, Doha",
  shape:"tall",            // "tall" 4:5, "square" 1:1, "land" 5:4
  art:"grid",              // generated artwork used when image is empty
  image:"assets/works/legal-01.jpg",   // <- add your image here
  blurb:"...", tags:["Instagram","LinkedIn"] },
```

- Put images in `assets/works/` (JPG or WebP, about 1600px wide, under 500 KB each).
- Set `image:` to the path. Leave it `""` to keep the generated CMYK artwork.
- Add or remove objects to add or remove projects. `cat` must be one of: `social`, `print`, `brand`, `editorial`, `ads`. Filter buttons update automatically.

## Update the CV

Replace `assets/Rilshan-Razik-CV.pdf` with a new file of the same name.

## Interactions included

- Plate-registration loader (C, M, Y, K)
- Hero name printed as 4 separate ink plates that drift out of register with the mouse and with scroll speed
- Registration-mark custom cursor with contextual labels (Open, PDF, Copy…)
- Click anywhere: CMYK halftone dot burst + registration ring
- Clickable colour bar that re-inks the page accent
- Filter animations and project pop-up morph using the View Transitions API
- 3D tilt + light glare on project cards
- Scroll-driven reveals (CSS `animation-timeline: view()`), with a fallback for older browsers
- Magnetic buttons, rolling button labels, scrambled nav text
- Marquees that speed up and reverse with your scroll
- CMYK scroll progress bar
- Respects "reduce motion" system settings; custom cursor only on mouse devices
