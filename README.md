# CIASUR — Sitio Web Institucional

Sitio estático (HTML5 + CSS3 nativo, sin frameworks) para el Círculo de
Investigación Ambiental de la Universidad Científica del Sur (CIASUR).

## 🚀 Despliegue en GitHub Pages

1. Crea un repositorio en GitHub (por ejemplo `ciasur.github.io` si es el
   repositorio de organización, o cualquier nombre si usarás Project Pages).
2. Sube estos archivos a la raíz del repositorio:index.html styles.css README.md assets.
3. Ve a **Settings → Pages** en tu repositorio.
4. En **Source**, selecciona la rama `main` y la carpeta `/ (root)`.
5. Guarda los cambios. GitHub publicará el sitio en 1–2 minutos en:
   - `https://<tu-usuario>.github.io/` (si el repo se llama `<tu-usuario>.github.io`), o
   - `https://<tu-usuario>.github.io/<nombre-repo>/` (Project Pages).
6. Si usas un dominio personalizado, agrégalo en **Settings → Pages → Custom domain**
   y crea un archivo `CNAME` en la raíz con el dominio (ej. `ciasur.org`).

> Si el sitio se publica en una subcarpeta (Project Pages), recuerda ajustar
> las rutas absolutas `/assets/...` de `index.html` y `styles.css` a rutas
> relativas (`assets/...`) o actualizar `url_base` según corresponda.

## 🖼️ Actualizar archivos multimedia en `/assets/`

La carpeta `assets/` debe contener:

| Archivo | Uso | Recomendación |
| `logo-ciasur.svg` | Logotipo completo (isotipo + wordmark) usado en header y footer | SVG, fondo transparente |
| `isotipo-ciasur.svg` | Isotipo individual usado como marca de agua en el Hero | SVG, fondo transparente |
| `favicon.svg` | Ícono de pestaña del navegador | SVG cuadrado 32×32 o superior |
| `og-cover.jpg` | Imagen de vista previa al compartir en redes (Open Graph) | JPG/PNG, 1200×630 px |
| `equipo/*.jpg` | Fotografías del directorio | JPG/WEBP, formato cuadrado (mínimo 480×480 px), mismo nombre que el `src` referenciado en `index.html` |

**Pasos para reemplazar una foto del directorio:**

1. Optimiza la imagen (formato cuadrado, peso recomendado < 200 KB).
2. Nómbrala exactamente igual al archivo referenciado en `index.html`
   (por ejemplo `carolina_angeles.jpg`).
3. Colócala dentro de `assets/equipo/`.
4. Sube los cambios (`git add`, `git commit`, `git push`) — GitHub Pages se
   actualizará automáticamente.

**Pasos para reemplazar el logo o isotipo:**

1. Exporta el archivo en formato `.svg` (preferido) o `.png` con fondo
   transparente.
2. Mantén el mismo nombre de archivo (`logo-ciasur.svg` / `isotipo-ciasur.svg`)
   o actualiza la ruta `src` correspondiente en `index.html`.

## 🎨 Sistema de diseño

- **Colores:** definidos como variables CSS en `:root` dentro de `styles.css`
  (`--color-primario`, `--color-secundario`, `--color-acento`, etc.). Cambiar
  un color institucional solo requiere editar la variable correspondiente.
- **Tipografía:** `Plus Jakarta Sans` (títulos) e `Inter` (cuerpo), cargadas
  desde Google Fonts en el `<head>` de `index.html`.
- **Íconos:** [Lucide Icons](https://lucide.dev) vía CDN (`data-lucide="..."`).
