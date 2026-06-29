# CineMax MX — Netflix Clone 2026 (Optimizado para Cloudflare Pages)

¡Bienvenido a **CineMax MX**! Una plantilla web moderna, ultra rápida y completamente en español de México (ES-MX), inspirada en la interfaz de usuario de Netflix de 2026. Está optimizada para dispositivos móviles, cuenta con modo oscuro automático, sistema de búsqueda inteligente, reproducción de videos de YouTube, listas de episodios para series, áreas dedicadas para afiliados y espacios estratégicos para Smartlinks de Adsterra.

Este proyecto está diseñado para ser estático (HTML, CSS y JS puro en un solo archivo `index.html`), lo que garantiza tiempos de carga casi instantáneos y una compatibilidad de 100% con **Cloudflare Pages**, **GitHub Pages**, **Vercel** o **Netlify**.

---

## 🚀 Características Clave

1. **Giao diện Netflix 2026 (Netflix 2026 UI/UX)**: Diseño inmersivo, moderno, minimalista, con tarjetas dinámicas (verticales para películas, horizontales avanzadas para series), sombras suaves y efectos de resplandor neón en rojo Netflix.
2. **Totalmente en Español (Mexico)**: Todos los textos, descripciones de películas de muestra, géneros y avisos legales adaptados al mercado mexicano.
3. **Optimizado para Móviles**: Menú hamburguesa responsivo, barra de búsqueda adaptativa, grids flexibles y optimización táctil.
4. **Modo Oscuro Permanente**: Paleta de colores oscuros profundos (`#0a0a0f`) con alto contraste para cuidar la vista.
5. **Búsqueda Avanzada**: Búsqueda instantánea en tiempo real sin recargar la página (busca por título o género).
6. **Filtros por Géneros**: Navegación rápida por categorías (Acción, Comedia, Drama, Terror, Animación, Ciencia Ficción, Romance, Series, etc.) con transiciones suaves.
7. **Reproductor Integrado**: Ventana modal moderna con reproductor responsivo de YouTube que detiene la reproducción al cerrarse.
8. **Lista de Episodios**: Soporte integrado para series. Permite listar episodios y cambiar dinámicamente entre videos al hacer clic en cada botón de episodio.
9. **Monetización Adsterra (Smartlink)**: 
   - Banner superior (Header Smartlink).
   - Espacio en la sección media (Middle Banner).
   - Banner inferior (Bottom Banner).
10. **Zona de Afiliados (Affiliate Area)**: Tarjeta destacada con botones personalizados para enlaces de afiliados (Smart TVs, Audífonos, VPN, etc.).
11. **Google Analytics**: Script de rastreo integrado en la cabecera (Header), listo para configurar.
12. **Carga Ultra Rápida**: Preconnects para fuentes y APIs externas, sin frameworks pesados, 100% HTML/CSS/JS nativo.

---

## 📂 Estructura del Proyecto

El sitio se compone principalmente de dos archivos principales en este directorio:
* `index.html` — Todo el código fuente (HTML5, estilos CSS3 responsivos y lógica JavaScript optimizada).
* `README.md` — Esta guía detallada de configuración y despliegue.

---

## 🛠️ Guía de Personalización y Configuración

Abre el archivo `index.html` en un editor de texto (como VS Code) y realiza los siguientes ajustes:

### 1. Configurar Google Analytics
Busca la línea 11 en el archivo `index.html` y reemplaza `G-XXXXXXXXXX` con tu ID de flujo real de Google Analytics:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=TU_ID_AQUÍ"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'TU_ID_AQUÍ');
</script>
```

### 2. Colocar tus Smartlinks de Adsterra
Hemos dejado tres bloques comentados donde puedes colocar tus scripts o enlaces de Adsterra:
* **Top Banner (Línea ~485)**: Reemplaza el enlace `<a href="#">` o pega el script de Adsterra dentro de `<div id="adsterra-top">`.
* **Middle Banner (Línea ~571)**: Reemplaza el texto en `<div class="adsterra-mid">` con tu banner de Adsterra (de 728x90 o similar) o tu Smartlink de redirección.
* **Bottom Banner (Línea ~616)**: Reemplaza el contenido en `<div class="adsterra-bottom">`.

### 3. Configurar Enlaces de Afiliados
En la sección de afiliados (Línea ~590), cambia los atributos `href="#"` por tus enlaces de afiliados reales (Amazon, AliExpress, etc.):
```html
<div class="affiliate-links">
  <a href="TU_LINK_AFILIADO_1" class="aff-btn aff-btn-1">📺 Smart TV 4K — Ver oferta</a>
  <a href="TU_LINK_AFILIADO_2" class="aff-btn aff-btn-2">🎧 Audífonos Bluetooth — Ver oferta</a>
  <a href="TU_LINK_AFILIADO_3" class="aff-btn aff-btn-3">🚀 VPN Premium — Descuento</a>
</div>
```

### 4. Administrar el Catálogo de Películas y Series
Toda la base de datos de películas se maneja mediante un arreglo JSON en JavaScript en la línea ~665. Puedes añadir, editar o eliminar elementos de forma sumamente sencilla:

```javascript
const MOVIES = [
  {
    id: 0,
    title: "Título de la Película o Serie",
    genre: "Acción", // Género principal
    year: 2026,
    rating: 8.7,
    duration: "2h 18min", // o "45min/ep" para series
    type: "Película", // "Película" o "Serie"
    yt: "dQw4w9WgXcQ", // ID de video de YouTube (ej. youtube.com/watch?v=dQw4w9WgXcQ)
    emoji: "🎬", // Emoji representativo para miniaturas dinámicas
    desc: "Descripción o sinopsis detallada aquí.",
    badge: "TENDENCIA", // Etiqueta superior (ej. "NUEVO", "POPULAR", "T2 NUEVA" o dejar vacío "")
    episodes: [] // Dejar vacío si es Película. Para series, añade ["Ep 1", "Ep 2", ...]
  },
  ...
];
```

---

## ⚡ Despliegue en Cloudflare Pages (¡Gratis y Súper Rápido!)

Debido a que es un sitio completamente estático, **Cloudflare Pages** es la mejor opción para alojarlo. Ofrece CDN global ultrarrápida, SSL gratis ilimitado y compresión automática.

### Método 1: Despliegue Directo (Arrastrar y Soltar)
1. Ve a tu panel de **Cloudflare** y navega a la sección **Pages** (o Pages & Workers).
2. Haz clic en **Create a project** (Crear un proyecto) -> **Direct Upload** (Carga directa).
3. Escribe un nombre para tu proyecto (por ejemplo: `cinemax-mx`).
4. Arrastra la carpeta que contiene el archivo `index.html` (o comprímela en un archivo `.zip` y súbela).
5. Haz clic en **Deploy site** (Desplegar sitio). ¡Listo! Cloudflare te dará un subdominio gratuito tipo `cinemax-mx.pages.dev` inmediatamente.

### Método 2: Despliegue mediante GitHub (Recomendado para Actualizaciones)
1. Crea un repositorio privado o público en GitHub y sube tu archivo `index.html`.
2. En el panel de **Cloudflare Pages**, selecciona **Connect to Git** (Conectar a Git).
3. Selecciona tu repositorio de GitHub.
4. En la configuración de construcción, deja todo por defecto (Build command: vacío, Build directory: vacío, ya que es HTML puro).
5. Haz clic en **Save and Deploy**. Cada vez que hagas un cambio y lo subas a GitHub, tu sitio web se actualizará automáticamente en menos de 10 segundos.

---

## 📱 Vista en Dispositivos Móviles

El sitio está diseñado bajo la filosofía *Mobile-First*. El menú hamburguesa lateral despliega una barra de búsqueda dedicada para smartphones y una lista vertical de todos los géneros cómoda para el pulgar. Los reproductores de video se adaptan perfectamente a pantallas táctiles horizontales y verticales (responsive aspect-ratio de `16:9`).

---

## ⚖️ DMCA y Descargo de Responsabilidad

Se incluye un descargo de responsabilidad en el footer de la página adecuado para este tipo de portales en México:
*"© 2026 CineMax MX — Solo para entretenimiento. No almacenamos ningún archivo en nuestros servidores. Todos los contenidos son proporcionados por servicios externos de reproducción (YouTube)."*
