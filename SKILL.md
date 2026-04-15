---
name: generador-landing-premium
description: >
  Usa este skill SIEMPRE que necesites crear una landing page profesional, sitio web de una página, página de ventas o portafolio web.
  Genera landing pages Dark Luxury completas en un solo archivo HTML con CSS y JS integrados: glassmorphism, animaciones 3D, flip cards de servicios con imágenes, partículas, navbar sticky, sección de testimonios, CTA con glow pulsante y footer completo.
  Se activa cuando el usuario dice: "crea una landing page", "hazme un sitio web", "necesito una página de ventas", "quiero una web para mi negocio", "genera un portafolio web", "crea mi página de presentación".
  Siempre hace 3 preguntas antes de generar: negocio, sector/estilo, color. Genera imágenes primero, luego el HTML. Compatible con Claude Code, Antigravity y NoCode.
compatibility:
  - claude
  - antigravity
  - nocode
---

# 🚀 PROMPT UNIVERSAL: Landing Page Premium Dark Mode

Genera landing pages de alta conversión con estética Dark Luxury, glassmorphism, animaciones 3D y flip cards de servicios. Compatible con Claude Code, Antigravity y NoCode.

---

## 📋 PASO 0 — HACER 3 PREGUNTAS ANTES DE GENERAR

Antes de generar cualquier código o imagen, recopila esta información del usuario:

### ❓ PREGUNTA 1: Información del Negocio
- **Nombre del negocio/marca:**
- **Tagline (frase descriptiva en 1 línea):**
- **Propuesta de valor (qué haces/ofreces):**

### ❓ PREGUNTA 2: Sector y Tipo de Web
**Sector/Industria:** (Tech/IA, Salud, Finanzas, Educación, E-commerce, Consultoría, Creatividad, etc.)

**Tipo de web:** (Selecciona UNA)
- **Personal** — Freelancer, creador de contenido, influencer
- **Corporativa** — Empresa establecida, profesional
- **Tech/Startup** — Tecnología, innovación, SaaS
- **Industrial** — Manufactura, B2B tradicional
- **Creativa** — Diseño, arte, agencia creativa

### ❓ PREGUNTA 3: Color Principal
**Color de acento principal:** (HEX)
- Púrpura/Lila: `#A855F7`
- Azul Eléctrico: `#3B82F6`
- Verde Neón: `#22C55E`
- Naranja/Fuego: `#F97316`
- Rosa/Magenta: `#EC4899`
- Cian: `#06B6D4`
- Otro: código HEX personalizado

---

## 🎨 PASO 1 — GENERAR IMÁGENES (antes que el HTML)

**⚡ TAN PRONTO el usuario responda las 3 preguntas, genera TODAS las imágenes antes de escribir una sola línea de código.**

### Imágenes a generar (orden obligatorio)

#### 1. Logo (`images/logo.png`) — 512×512px, PNG fondo transparente
```
Modern minimalist logo for [NOMBRE], [SECTOR] industry,
featuring [COLOR] as primary color, dark background,
premium aesthetic, clean design, scalable icon, vector style
```

#### 2. Visual del Hero (`images/hero_visual.png`) — 1200×1200px
```
Premium hero section visual for [NOMBRE], [SECTOR] industry,
featuring [COLOR] glowing elements, 3D abstract shapes,
dark luxury background, futuristic aesthetic, floating particles,
depth, cinematic composition, high-end render, 4K quality
```

#### 3. Imágenes de Servicios (`images/service_1.png` … `service_6.png`) — 800×600px c/u
```
Professional [DESCRIPCIÓN DEL SERVICIO] visual for [SECTOR],
[COLOR] accent lighting, dark luxury aesthetic,
premium quality, modern composition, cinematic lighting, 4K quality
```

**Ejemplos por sector:**
- Tech/SaaS → Dashboard interfaces, redes neuronales, circuitos futuristas
- Corporativa → Oficinas modernas, reuniones, gráficos de negocio
- Creativa → Paletas, herramientas de diseño, arte abstracto
- Industrial → Maquinaria moderna, fábricas high-tech, ingeniería
- Personal → Workspace, herramientas, elementos de branding

#### 4. Imágenes opcionales
- `images/showcase_1.png`, `images/showcase_2.png` — Casos de éxito / Portfolio
- `images/about_image.png` — Foto de equipo o About

### Estructura de carpeta
```
images/
  ├── logo.png
  ├── hero_visual.png
  ├── service_1.png … service_6.png
  ├── showcase_1.png  (opcional)
  ├── showcase_2.png  (opcional)
  └── about_image.png (opcional)
```

---

## 🏗️ PASO 2 — GENERAR EL HTML COMPLETO

Una vez generadas las imágenes, produce un único `index.html` con CSS y JS incrustados.

### Sistema de diseño

#### Fondos (siempre iguales)
```css
--bg-primary:   #000000;
--bg-secondary: #09090B;
--bg-tertiary:  #18181B;
```

#### Escala del color primario (generar a partir del HEX elegido)
```css
--primary-400: [Color base +20% brillo]   /* hover states */
--primary-500: [COLOR BASE]               /* principal */
--primary-600: [Color base -10% brillo]   /* botones activos */
--primary-700: [Color base -20% brillo]   /* gradientes profundos */
```

#### Textos
```css
--text-primary:   #FFFFFF;
--text-secondary: #E4E4E7;
--text-tertiary:  #A1A1AA;
```

#### Tipografía (Google Fonts)
```css
/* Títulos */ "Plus Jakarta Sans", weight 700-800
/* Cuerpo */  "Inter", weight 400-500
/* Código */  "JetBrains Mono" (solo si es Tech)
```

Jerarquía:
```
H1 Hero:     76px, weight 800, letter-spacing -0.02em
H2 Sección:  48px, weight 700
H3 Card:     24px, weight 600
Body:        16-20px, weight 400, line-height 1.6-1.7
Labels:      12px, uppercase, letter-spacing 0.1em
```

---

### Secciones obligatorias

#### 1. NAVBAR sticky
- Logo `images/logo.png` (48px alto)
- Links de navegación con underline animado
- Al hacer scroll: `background: rgba(0,0,0,0.8)`, `backdrop-filter: blur(24px)`

#### 2. HERO (100vh)
```html
<section class="hero">
  <!-- Partículas flotantes en JS -->
  <!-- Hero visual: images/hero_visual.png con animación float -->
  <!-- Label superior: [emoji] [claim diferenciador] -->
  <!-- H1 con gradiente del color primario -->
  <!-- Subtítulo: propuesta de valor en 1-2 líneas -->
  <!-- CTA Primary (glow pulsante) + CTA Secondary (outline) -->
</section>
```

#### 3. SOCIAL PROOF
- Logos de clientes/partners en escala de grises → color al hover
- Métrica principal: "[Número]+ [métrica relevante]"

#### 4. SERVICIOS — Flip Cards 3D (grid 3×2)
```html
<div class="service-card-flip">
  <div class="service-card-inner"> <!-- flip 180° en hover -->
    <div class="service-card-front">
      <img src="images/service_1.png" alt="[Servicio]" class="service-image">
      <div class="service-overlay">
        <h3>[Nombre Servicio]</h3>
      </div>
    </div>
    <div class="service-card-back glass-card">
      <h3>[Nombre Servicio]</h3>
      <p>[Descripción 2-3 líneas]</p>
      <div class="service-features">
        <span class="feature-tag">[Tag 1]</span>
        <span class="feature-tag">[Tag 2]</span>
      </div>
    </div>
  </div>
</div>
```
Animación: flip 3D de 180° en hover (0.8s cubic-bezier). En mobile: tap.

#### 5. SHOWCASE / PORTFOLIO / DASHBOARD
Adaptar según tipo de web usando `images/showcase_*.png` o `hero_visual.png`.
- Glass cards con glassmorphism
- Estadísticas animadas (IntersectionObserver + contador JS)

#### 6. TESTIMONIOS
- Grid o carousel de cards con glassmorphism
- Quote marks en color primario
- Avatares circulares con borde del color primario
- Rating ★★★★★

#### 7. SOBRE MÍ / NOSOTROS
- Grid 1:2 (imagen `images/about_image.png` con glow : texto)
- Bio en 2-3 párrafos
- Redes sociales con iconos

#### 8. CTA FINAL
- Fondo con radial-gradient del color primario intenso
- Título grande + subtítulo de urgencia
- Botón con `animation: pulse-glow 3s ease-in-out infinite`

#### 9. FOOTER
- Logo + columnas de links (Servicios, Recursos, Legal, Contacto)
- Iconos de redes sociales
- Copyright: `© [AÑO] [Nombre]. Todos los derechos reservados.`

---

### Componentes CSS obligatorios

#### Glassmorphism card
```css
.glass-card {
  background: linear-gradient(135deg,
    rgba([PRIMARY-RGB], 0.08) 0%,
    rgba([PRIMARY-RGB], 0.04) 50%,
    rgba([PRIMARY-RGB], 0.08) 100%);
  backdrop-filter: blur(24px) saturate(180%);
  border: 1px solid rgba([PRIMARY-RGB], 0.15);
  border-radius: 24px;
  padding: 32px;
  box-shadow:
    0 4px 6px -1px rgba(0,0,0,0.3),
    inset 0 1px 0 rgba(255,255,255,0.05);
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}
.glass-card:hover {
  border-color: rgba([PRIMARY-RGB], 0.35);
  box-shadow: 0 25px 50px -12px rgba([PRIMARY-RGB], 0.35);
  transform: translateY(-4px);
}
```

#### Botón CTA Primary
```css
.btn-primary {
  background: linear-gradient(135deg,
    var(--primary-600), var(--primary-500), var(--primary-400), var(--primary-500));
  background-size: 200% 200%;
  animation: gradient-shift 4s ease infinite, pulse-glow 3s ease-in-out infinite;
  color: #fff;
  font-weight: 600;
  padding: 16px 32px;
  border-radius: 12px;
  border: none;
  box-shadow:
    0 0 0 1px rgba([PRIMARY-RGB], 0.5),
    0 4px 24px rgba([PRIMARY-RGB], 0.4),
    inset 0 1px 0 rgba(255,255,255,0.2);
}
.btn-primary:hover {
  transform: translateY(-2px) scale(1.02);
  filter: brightness(1.1);
}
```

#### Glow effects
```css
.glow-primary {
  filter:
    drop-shadow(0 0 20px rgba([PRIMARY-RGB], 0.6))
    drop-shadow(0 0 40px rgba([PRIMARY-RGB], 0.4))
    drop-shadow(0 0 60px rgba([PRIMARY-RGB], 0.3));
}
.glow-text {
  text-shadow:
    0 0 10px rgba([PRIMARY-RGB], 0.8),
    0 0 20px rgba([PRIMARY-RGB], 0.6),
    0 0 40px rgba([PRIMARY-RGB], 0.4);
}
```

---

### Animaciones CSS obligatorias

```css
/* Flotación del hero visual */
@keyframes float {
  0%, 100% { transform: translateY(0) rotate(0deg); }
  25%       { transform: translateY(-20px) rotate(2deg); }
  50%       { transform: translateY(-10px) rotate(-2deg); }
  75%       { transform: translateY(-30px) rotate(1deg); }
}

/* Partículas de fondo */
@keyframes float-particle {
  0%, 100% { transform: translate(0, 0);           opacity: 0.4; }
  25%       { transform: translate(100px, -100px);  opacity: 0.8; }
  50%       { transform: translate(-50px, -200px);  opacity: 0.6; }
  75%       { transform: translate(-100px, -100px); opacity: 0.8; }
}

/* Glow pulsante del CTA */
@keyframes pulse-glow {
  0%, 100% { box-shadow: 0 0 0 1px rgba([PRIMARY-RGB],0.5), 0 4px 24px rgba([PRIMARY-RGB],0.4); }
  50%       { box-shadow: 0 0 0 2px rgba([PRIMARY-RGB],0.8), 0 8px 40px rgba([PRIMARY-RGB],0.6); }
}

/* Desplazamiento del gradiente */
@keyframes gradient-shift {
  0%, 100% { background-position: 0% 50%; }
  50%       { background-position: 100% 50%; }
}

/* Entrada desde abajo */
@keyframes fade-in-up {
  from { opacity: 0; transform: translateY(30px); }
  to   { opacity: 1; transform: translateY(0); }
}
```

### JavaScript obligatorio

```javascript
// Partículas flotantes generadas dinámicamente
// Navbar con clase .scrolled al pasar scroll
// IntersectionObserver para reveal de secciones y stagger de cards
// Contador animado para métricas (0 → valor final)
// Parallax suave en hero (0.3x velocidad)
// En mobile: tap-to-flip para service cards
```

---

### Adaptación por tipo de web

| Tipo | Hero | Tono | Secciones extra |
|------|------|------|----------------|
| **Personal** | Foto de perfil prominente | Cercano, storytelling | Portfolio, Blog, Redes |
| **Corporativa** | Logo + claim | Profesional, orientado a resultados | Equipo, Clientes, Certificaciones |
| **Tech/Startup** | Demo interactiva | Innovador, técnico accesible | Pricing, API, Roadmap |
| **Industrial** | Instalaciones + datos overlay | Sólido, técnico | Certificaciones ISO, Capacidades |
| **Creativa** | Portfolio visual inmersivo | Inspirador, visual-first | Awards, Proceso creativo |

---

### Páginas legales (incluir siempre)

Generar también en carpeta `legal/`:
- `privacidad.html` — Política de Privacidad
- `cookies.html` — Política de Cookies
- `terminos.html` — Términos y Condiciones

Mismo estilo dark del index, sin distracciones, con link de regreso.

---

### Integración n8n (opcional)

Si el usuario tiene un webhook de n8n para captura de leads, integrar en el formulario de contacto:

```javascript
const WEBHOOK_URL = 'https://tu-instancia-n8n.com/webhook/[ID]';

async function submitForm(data) {
  const res = await fetch(WEBHOOK_URL, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(data)
  });
  return res.ok;
}
```

Incluir **honeypot** anti-bot (campo oculto que los bots rellenan y los humanos ignoran):
```html
<input type="text" name="website" style="display:none" tabindex="-1" autocomplete="off">
```

---

## 🙏 Agradecimientos

<p align="center">
  <br/>
  <em>
    "Porque Dios es el que en vosotros produce<br/>
    así el querer como el hacer,<br/>
    por su buena voluntad."
  </em>
  <br/>
  <strong>— Filipenses 2:13</strong>
  <br/><br/>
  Todo lo que aquí existe nació primero como un deseo en el corazón.<br/>
  Cada proyecto, cada línea, cada idea que toma forma —<br/>
  es un regalo de Aquel que nos dio tanto el sueño como la fuerza de alcanzarlo.<br/>
  <strong>A Dios, toda la gloria.</strong>
  <br/>
</p>
