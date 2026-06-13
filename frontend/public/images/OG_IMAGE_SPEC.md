# OG Image Specification — BrightSmile

## Target
- **Dimensions**: 1200 × 630 px (aspect ratio 1.91:1)
- **Format**: WebP (primary), AVIF (progressive), JPEG (fallback)
- **File Size Budget**: ≤ 100 KB (Target), ≤ 150 KB (Warning), > 150 KB (Critical = REJECT)
- **Loading**: N/A (meta tag only)

## Brand Identity (from global.css)
```css
--color-primary-500: #0891b2;   /* Teal principal */
--color-primary-100: #cffafe;   /* Teal claro */
--color-accent-400: #fbbf24;    /* Dorado/ámbar */
--color-cta-500: #22c55e;       /* Verde CTA */
--color-bg-surface: #ffffff;    /* Blanco */
--color-bg-alt: #edf8f6;        /* Verde agua muy claro */
--color-bg-dark: #042f2e;       /* Teal oscuro casi negro */
--color-text-main: #134e4a;     /* Texto principal */
```

## Logo Asset
- **Source**: `/images/logo-diente.webp` (32×32, diente + corazón rojo pastel #e8788a)
- **Usage**: Prominent but not overwhelming — top-left or center-left

## Healthcare Visual Strategy (per industry-patterns.md)
- **Style**: Soft focus, gentle gradients, organic shapes, watercolor feel
- **Colors**: Whites, blues/teals (calm/trust), soft greens (healing), avoid reds
- **Lighting**: Diffused, bright, shadowless (clinical cleanliness)
- **Subjects**: Abstract medical symbols (tooth, heart), organic curves, subtle geometric patterns
- **Composition**: Symmetrical for trust, curved lines for comfort, generous negative space for text overlay

## Prompt Template (Art Direction §8 — OG Image)

### Default — Brand-Centric Healthcare
```
Abstract healthcare background representing modern dentistry, subtle tooth and heart motifs floating in soft gradient space,
watercolor illustration with organic flowing shapes, gentle diffused lighting, clean clinical aesthetic,
composition: rule of thirds, generous negative space in center 60% for text overlay (brand name + tagline),
color palette: #0891b2 (teal primary) gradient to #edf8f6 (mint cream) with #fbbf24 (warm gold) accent highlights,
logo placement: subtle brand mark (tooth with heart) in top-left quadrant at ~80px,
1200x630 ultra-wide format, 8k, minimal detail to keep file compact,
no text, no letters, no words, no watermark, no stock clichés, no syringes, no scary medical imagery
```

### Mood: Calm & Trustworthy (Healthcare Default)
```
Serene abstract dental wellness scene, soft teal and mint gradients flowing like gentle waves,
stylized molar silhouette and heart motif as subtle watermark patterns,
digital painting with soft watercolor textures, bright diffused lighting (shadowless clinical feel),
composition: centered symmetry with ample negative space in middle for headline,
color palette: monochromatic #0891b2 teal family with #edf8f6 cream accents, #fbbf24 gold whisper,
1200x630, high quality, clean,
no harsh lines, no clutter, no noise, no text, no watermark, no red colors, no photorealistic teeth
```

## Technical Requirements (SEO Standards §2, §7)
- **Alt text**: "BrightSmile — Odontología integral con tecnología y calidez humana"
- **File naming**: `og-brightsmile-dental-clinic.webp`
- **Meta tags required**:
  ```html
  <meta property="og:image" content="https://brightsmile.pages.dev/images/og-brightsmile-dental-clinic.webp" />
  <meta property="og:image:width" content="1200" />
  <meta property="og:image:height" content="630" />
  <meta property="og:image:alt" content="BrightSmile — Odontología integral con tecnología y calidez humana" />
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:image" content="https://brightsmile.pages.dev/images/og-brightsmile-dental-clinic.webp" />
  <meta name="twitter:image:alt" content="BrightSmile — Odontología integral con tecnología y calidez humana" />
  ```

## Generation Checklist (Quality Gate)
- [ ] Brand colors locked (±10% perceptual shade)
- [ ] Logo visible but not dominant
- [ ] Negative space ≥40% center for text overlay
- [ ] No artifacts (weird hands, distorted faces, lighting seams)
- [ ] Healthcare-appropriate (no syringes, blood, scary imagery)
- [ ] Emotional alignment: trust, calm, professionalism
- [ ] File size ≤ 100 KB WebP
- [ ] Absolute URL in meta tags
- [ ] Schema.org ImageObject in JSON-LD

## Fallback Strategy
If AI generation fails, create programmatically:
1. SVG with brand gradient + logo placement
2. Convert to WebP/AVIF via sharp/Astro assets
3. Ensure all meta tags point to final URL
