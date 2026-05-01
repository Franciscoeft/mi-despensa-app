# 🍞 Despensa v3 — Inventario del Hogar

## Archivos del proyecto

```
despensa-app/
├── index.html      ← App principal (todo el código)
├── manifest.json   ← Configuración PWA
├── sw.js           ← Service Worker (offline + notificaciones)
├── icon.svg        ← Icono de la app (SVG)
└── README.md       ← Este archivo
```

## Cómo ejecutar localmente

### Opción 1 — VS Code Live Server (recomendado)
1. Instala la extensión **Live Server** en VS Code
2. Abre la carpeta `despensa-app/`
3. Click derecho en `index.html` → **Open with Live Server**
4. Se abre en `http://127.0.0.1:5500`

### Opción 2 — Python
```bash
cd despensa-app
python3 -m http.server 8080
# Abre http://localhost:8080
```

### Opción 3 — Node.js
```bash
npx serve despensa-app
```

> ⚠️ El Service Worker y la PWA solo funcionan con servidor HTTP, no abriendo el archivo directamente (file://).

## Publicar en internet (gratis)

### GitHub Pages
1. Sube los archivos a un repositorio GitHub
2. Ve a Settings → Pages → Source: main branch / root
3. Tu app estará en `https://tuusuario.github.io/tu-repo/`

### Netlify (drag & drop)
1. Ve a [netlify.com](https://netlify.com)
2. Arrastra la carpeta `despensa-app/` al dashboard
3. ¡Listo! URL automática en segundos

### Vercel
```bash
npx vercel deploy despensa-app
```

## Instalar como app en el móvil

1. Abre la URL en Safari (iPhone) o Chrome (Android)
2. Toca el botón de compartir → **"Añadir a pantalla de inicio"**
3. La app funciona offline gracias al Service Worker

## Funcionalidades

- 📦 Inventario completo con emojis, etiquetas y ubicaciones
- 📅 Línea de tiempo de caducidades con alertas
- 🛒 Lista de la compra con auto-completar
- 📊 Estadísticas: valor del inventario, gráficos por categoría
- 🔍 Búsqueda y filtros avanzados
- 👆 Selección múltiple para acciones en lote
- 📤 Exportar/importar JSON y CSV
- 🔔 Notificaciones del navegador
- 📲 PWA instalable — funciona sin internet
- 💾 Datos guardados localmente (localStorage)

## Para convertir a app nativa (App Store / Play Store)

Usa **Capacitor** (requiere Mac para iOS):
```bash
npm install @capacitor/core @capacitor/cli
npx cap init Despensa com.tudominio.despensa
npx cap add ios    # requiere Mac + Xcode
npx cap add android
npx cap copy
npx cap open ios
```
