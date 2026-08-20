# Supportqss — Landing Page

Landing page de una sola página (`index.html`) para Supportqss, empresa de consultoría e infraestructura IT. Sin dependencias de build: es HTML + CSS + JS plano, listo para publicar en **GitHub Pages**.

## Estructura

```
supportqss-web/
├── index.html   ← toda la página (incluye estilos y script)
└── README.md
```

## Publicar en GitHub Pages (paso a paso)

1. **Creá un repositorio nuevo** en GitHub, por ejemplo `supportqss-web`.
   - Puede ser público (necesario si tenés cuenta gratuita y querés Pages activado fácilmente).

2. **Subí los archivos** (`index.html` y `README.md`) a la raíz del repositorio.
   - Opción rápida desde la web de GitHub: botón **"Add file" → "Upload files"**, arrastrá `index.html` y confirmá el commit.
   - Opción por consola:
     ```bash
     git init
     git add index.html README.md
     git commit -m "Landing page Supportqss"
     git branch -M main
     git remote add origin https://github.com/TU-USUARIO/supportqss-web.git
     git push -u origin main
     ```

3. **Activá GitHub Pages**:
   - Andá a **Settings → Pages** dentro del repositorio.
   - En "Build and deployment", elegí **Source: Deploy from a branch**.
   - Seleccioná **Branch: main** y carpeta **/(root)**.
   - Guardá.

4. **Esperá 1-2 minutos.** GitHub te va a dar una URL del estilo:
   ```
   https://TU-USUARIO.github.io/supportqss-web/
   ```

5. **(Opcional) Dominio propio**: si tenés `supportqss.com`, podés agregarlo en Settings → Pages → Custom domain, y crear un registro CNAME en tu proveedor de DNS apuntando a `TU-USUARIO.github.io`.

## Conectar el formulario de contacto

El formulario de la sección "Contacto" es una plantilla estática: por ahora solo muestra una alerta al enviarse, porque GitHub Pages no ejecuta backend. Para que los mensajes lleguen a tu email, elegí una opción:

- **Formspree** (más simple): creá una cuenta gratuita en formspree.io, obtené tu endpoint y cambiá en `index.html`:
  ```html
  <form id="contactForm" action="https://formspree.io/f/TU-ID" method="POST">
  ```
  y quitá el `e.preventDefault()` del script al final del archivo.

- **EmailJS**: permite enviar el formulario directo desde el navegador sin backend, con su propio SDK (ver emailjs.com/docs).

## Personalización rápida

- **Colores**: variables CSS al inicio del `<style>` (`--blue`, `--teal`, `--amber`, `--bg`).
- **Textos e íconos de servicios**: sección `id="servicios"`.
- **Datos de contacto**: sección `id="contacto"` (email, teléfono, dirección).
- **Logo**: reemplazá el bloque `.logo-mark` (actualmente iniciales "SQ") por una imagen si tenés un isotipo.

## Nota sobre el contenido

Esta página fue creada con un diseño y una estructura de secciones inspirados en páginas de consultoría de infraestructura IT (hero, servicios, proceso, contacto), pero con copy, paleta y componentes visuales originales para Supportqss — no reproduce el diseño, textos ni marca de ningún sitio de terceros.
