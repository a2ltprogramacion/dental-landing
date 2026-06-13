# Clinica Dental BrightSmile - Landing Page

Landing page profesional para consultorio de odontologia, construida con el stack A2LT.

## Stack

- **Frontend:** Astro 6 + Tailwind CSS v4 (CSS-first @theme)
- **Citas:** Cal.com (embed inline — sin backend)
- **Deploy:** Cloudflare Pages ($0)
- **Calendario:** Google Calendar (sincronizado via Cal.com)

## Arquitectura

```
Sin backend — 100% estatico + SaaS

Cloudflare Pages  ->  Landing (Astro SSG)
Cal.com           ->  Sistema de citas (iframe embed)
Google Calendar   ->  Vista del operador en telefono
```

## Inicio Rapido

```bash
cd frontend
npm install
npm run dev
```

El sitio estara disponible en `http://localhost:4321`

## Deploy en Cloudflare Pages

1. Conectar repositorio GitHub en [Cloudflare Pages](https://pages.cloudflare.com)
2. Build command: `npm run build`
3. Output directory: `dist`
4. Framework preset: Astro

## Configurar Cal.com

1. Crear cuenta en [cal.com](https://cal.com) con el Gmail del consultorio
2. Conectar Google Calendar en Settings > Calendar
3. Crear 4 Event Types:

| Event Type | Duracion | Buffer |
|---|---|---|
| Odontologia General | 30 min | 5 min |
| Ortodoncia | 45 min | 5 min |
| Estetica Dental | 30 min | 10 min |
| Implantes | 60 min | 10 min |

4. Copiar los slugs de cada Event Type (ej: `cal.com/tu-user/general`)
5. Reemplazar los placeholders en `src/components/AppointmentForm.astro`:

```js
const CAL_EVENTS = {
  general: "https://cal.com/BRIGHTSMILE/general",    // <- reemplazar
  ortodoncia: "https://cal.com/BRIGHTSMILE/ortodoncia", // <- reemplazar
  estetica: "https://cal.com/BRIGHTSMILE/estetica",    // <- reemplazar
  implantes: "https://cal.com/BRIGHTSMILE/implantes",   // <- reemplazar
};
```

## Estructura

```
dental-landing/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── atoms/         # SeoHead
│   │   │   ├── AppointmentForm.astro  # Cal.com embed + tabs
│   │   │   ├── CTASection.astro
│   │   │   ├── Evidence.astro
│   │   │   ├── FAQ.astro
│   │   │   ├── Footer.astro
│   │   │   ├── Hero.astro
│   │   │   ├── HowItWorks.astro
│   │   │   ├── Navbar.astro
│   │   │   ├── ProblemSolution.astro
│   │   │   └── Services.astro
│   │   ├── layouts/          # Layout.astro
│   │   ├── pages/            # index.astro
│   │   └── styles/           # global.css (tokens + Tailwind v4)
│   ├── public/
│   │   ├── _headers          # Cloudflare Pages security headers
│   │   ├── robots.txt
│   │   ├── humans.txt
│   │   ├── favicon.ico
│   │   └── images/
│   ├── astro.config.mjs
│   └── package.json
└── README.md
```

## Personalizar

1. **Dominio:** Reemplaza `brightsmile.pages.dev` en `astro.config.mjs` y `robots.txt`
2. **WhatsApp:** Cambia el numero en `Footer.astro` y `index.astro`
3. **Colores:** Modifica los tokens en `src/styles/global.css` (`@theme { ... }`)
4. **Slugs Cal.com:** Reemplaza los placeholders en `AppointmentForm.astro`

## Placeholders por Reemplazar

| Placeholder | Archivo | Reemplazar con |
|---|---|---|
| `brightsmile.pages.dev` | astro.config.mjs, robots.txt | Dominio real |
| `[TU CIUDAD]` | index.astro | Ciudad del consultorio |
| `BRIGHTSMILE` (en Cal.com URLs) | AppointmentForm.astro | Tu username de Cal.com |
| `584121234567` | Footer.astro, index.astro | Numero WhatsApp real |
| Estadisticas | index.astro | Datos verificables reales |
| Testimonios | index.astro | Testimonios reales |

---

Desarrollado por [A2LT Soluciones](https://a2lt.netlify.app)
