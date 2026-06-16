# Ciaa — Sitio Web Oficial

Página web de artista construida en HTML puro, lista para alojar en **GitHub Pages** y conectar con **Cloudflare**.

---

## 🚀 Cómo publicar en GitHub Pages

### 1. Crear el repositorio en GitHub
1. Inicia sesión en [github.com](https://github.com)
2. Haz clic en **New repository**
3. Ponle el nombre: `ciaa-site` (o el que prefieras)
4. Dejarlo **Public**
5. Clic en **Create repository**

### 2. Subir el archivo
Opción fácil (sin usar terminal):
1. En el repositorio recién creado, haz clic en **"uploading an existing file"**
2. Arrastra el archivo `index.html` ahí
3. Escribe un mensaje como `"Primer lanzamiento"` y haz clic en **Commit changes**

### 3. Activar GitHub Pages
1. Ve a **Settings** → **Pages** (en el menú lateral izquierdo)
2. En **Source**, selecciona **"Deploy from a branch"**
3. En **Branch**, elige `main` y la carpeta `/ (root)`
4. Clic en **Save**

Tu sitio estará en: `https://TU-USUARIO.github.io/ciaa-site/`

---

## ☁️ Conectar con Cloudflare (dominio personalizado)

### Si ya tienes un dominio (ej: `ciaa.cl`)

1. Entra a [cloudflare.com](https://cloudflare.com) y agrega tu dominio
2. Cloudflare te dará sus nameservers → cámbia los de tu registrador por los de Cloudflare
3. En Cloudflare, ve a **DNS** y agrega estos registros:

```
Tipo    Nombre    Contenido
CNAME   www       TU-USUARIO.github.io
A       @         185.199.108.153
A       @         185.199.109.153
A       @         185.199.110.153
A       @         185.199.111.153
```

4. En GitHub → Settings → Pages → **Custom domain**: escribe `www.ciaa.cl`
5. Activa **"Enforce HTTPS"** en GitHub Pages
6. En Cloudflare, pon el **Proxy Status** en **DNS only** (nube gris) para el CNAME de GitHub Pages

### Beneficios de Cloudflare
- SSL/HTTPS gratuito
- CDN global (carga más rápida)
- Protección DDoS básica gratuita

---

## 📁 Estructura del proyecto

```
ciaa-site/
└── index.html    ← toda la web en un solo archivo
```

---

## 💬 Configurar comentarios (Giscus)

La nueva página `index.html` tiene estilo de wiki con una pestaña de "Discusión" que usa **Giscus** — comentarios gratis que funcionan a través de GitHub Discussions. Los visitantes necesitan una cuenta de GitHub para comentar (inicio de sesión real, sin nombres anónimos).

### Pasos para activarlo:

1. Asegúrate que tu repositorio sea **público**
2. Ve a **Settings** del repo → activa **Discussions** (checkbox en la sección Features)
3. Ve a [giscus.app](https://giscus.app) y completa el formulario:
   - Pon el nombre de tu repositorio (`tu-usuario/ciaa-site`)
   - Elige la categoría de Discussions (recomendado: crear una llamada "General" o "Comentarios")
   - Elige "Página → discusión" como mapeo
4. Giscus te dará un bloque de código `<script>` con tus valores reales de `data-repo-id` y `data-category-id`
5. Abre `index.html`, busca esta sección cerca del final:

```html
<script src="https://giscus.app/client.js"
        data-repo="TU-USUARIO/ciaa-site"
        data-repo-id="REEMPLAZAR_REPO_ID"
        data-category="General"
        data-category-id="REEMPLAZAR_CATEGORY_ID"
        ...
```

6. Reemplaza `TU-USUARIO`, `REEMPLAZAR_REPO_ID` y `REEMPLAZAR_CATEGORY_ID` con los valores que te dio Giscus
7. Sube el cambio a GitHub — listo, los comentarios ya funcionan

---

## 🗂️ Archivos del proyecto

```
ciaa-site/
├── index.html                  ← página principal, ahora con estilo wiki (MediaWiki/Miraheze)
├── index-original-backup.html  ← el diseño anterior (artístico/oscuro), por si quieres volver
├── discografia.html            ← versión visual de la discografía con portadas grandes
└── README.md
```

La página wiki (`index.html`) tiene pestañas internas: **Artículo**, **Discografía**, **Biografía detallada** y **Discusión** (comentarios), todo en un solo archivo con buscador funcional incluido.

---

*Hecho con ❤️ para Ciaa — Concepción, Chile 🇨🇱*
