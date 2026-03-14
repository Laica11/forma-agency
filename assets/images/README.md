# FORMA — Image Assets

All images should be high-resolution, warm-toned editorial photography. Avoid cool or desaturated tones — match the parchment/linen palette of the site.

---

## Folder Structure

```
assets/images/
├── hero/
│   └── hero-portrait.jpg         # Full-height editorial portrait for hero right panel
│                                 # Recommended: 1200×1600px minimum, 3:4 ratio
│
├── about/
│   ├── about-studio.jpg          # Studio interior — Manila (portrait orientation)
│   ├── about-workshop.jpg        # Brand workshop session (portrait orientation)
│   └── about-cityscape.jpg       # Campaign cityscape (landscape orientation)
│                                 # Portraits: ~800×1024px | Landscape: ~1200×700px
│
├── showcase/
│   ├── showcase-rafael-santos.jpg    # Founder · Tech — wide card (4:5 ratio)
│   ├── showcase-isabel-reyes.jpg     # Executive · Finance (3:4 ratio)
│   ├── showcase-marco-dela-cruz.jpg  # Creative Director · Fashion (3:4 ratio)
│   ├── showcase-sofia-lim.jpg        # Founder · Wellness (3:4 ratio)
│   └── showcase-adrian-tan.jpg       # CEO · Real Estate (3:4 ratio)
│                                     # Wide: 900×1125px | Standard: 570×760px
│
├── team/
│   ├── team-alejandro-villanueva.jpg  # Founder & Chief Strategist (3:4 ratio)
│   ├── team-mia-castillo.jpg          # Creative Director (3:4 ratio)
│   ├── team-david-sy.jpg              # Head of Media (3:4 ratio)
│   └── team-lucia-hernandez.jpg       # Narrative Architect (3:4 ratio)
│                                      # Recommended: 600×800px minimum
│
└── og/
    └── og-cover.jpg              # Open Graph / social share image
                                  # Recommended: 1200×630px
```

---

## How to Wire Images Into the Site

Replace the gradient placeholder backgrounds in `index.html` with `<img>` tags or `background-image` CSS.

### Hero portrait
```html
<!-- Replace the layered divs inside .hero-photo-bg with: -->
<img src="assets/images/hero/hero-portrait.jpg" alt="FORMA client editorial portrait"
     style="width:100%;height:100%;object-fit:cover;object-position:center top;">
```

### About photos
```html
<!-- Inside each .aph-bg, replace the gradient span with: -->
<img src="assets/images/about/about-studio.jpg" alt="FORMA Studio — Manila"
     style="width:100%;height:100%;object-fit:cover;">
```

### Showcase cards
```html
<!-- Inside each .sc-photo, replace .sc-photo-bg gradient with: -->
<img src="assets/images/showcase/showcase-rafael-santos.jpg" alt="Rafael Santos"
     style="width:100%;height:100%;object-fit:cover;object-position:center top;"
     class="sc-photo-bg">
```

### Team photos
```html
<!-- Inside each .tm-photo, replace .tm-photo-bg gradient with: -->
<img src="assets/images/team/team-alejandro-villanueva.jpg" alt="Alejandro Villanueva"
     style="width:100%;height:100%;object-fit:cover;object-position:center top;"
     class="tm-photo-bg">
```

---

## Image Guidelines
- **Format:** JPG for photos (optimize to ≤ 300KB per image), PNG for graphics with transparency
- **Color tone:** Warm, editorial — match the `#EDE5D4` parchment palette
- **Subjects:** No harsh shadows, no stark white backgrounds
- **Compression:** Use [Squoosh](https://squoosh.app) or similar before uploading
