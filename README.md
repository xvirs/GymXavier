# Gym Pro Tracker 💪

PWA personal de seguimiento de rutina de gimnasio. 4 días de entrenamiento + cardio.

**Stack:** HTML + CSS + JS vanilla. Sin frameworks, sin dependencias.

---

## 📂 Estructura

```
GymXavier/
├── index.html          # App principal
├── manifest.json       # Metadata PWA
├── sw.js               # Service worker (cache offline)
├── icons/
│   ├── icon.svg        # Ícono fuente
│   ├── icon-192.png    # Ícono PWA 192x192
│   ├── icon-512.png    # Ícono PWA 512x512
│   └── favicon.png     # Favicon del browser
├── .gitignore
└── README.md
```

---

## 🚀 Setup local

```bash
cd /Users/xavier/Proyectos/GymXavier
```

Para probar localmente con un servidor (necesario para que el Service Worker funcione):

```bash
# Opción 1: Python
python3 -m http.server 8000

# Opción 2: Node
npx serve .
```

Después abrís `http://localhost:8000` en el navegador.

> ⚠️ Abrir el HTML directamente con doble click NO va a registrar el service worker (requiere `http://` o `https://`).

---

## 📤 Subir a GitHub

```bash
cd /Users/xavier/Proyectos/GymXavier

# Inicializar repo
git init
git add .
git commit -m "Initial commit: Gym Pro Tracker PWA"
git branch -M main

# Conectar con GitHub (creá el repo vacío primero en github.com)
git remote add origin https://github.com/TU_USUARIO/GymXavier.git
git push -u origin main
```

---

## 🌐 Deploy — 3 opciones

### Opción A — GitHub Pages (requiere repo público o GitHub Pro)

1. En GitHub: **Settings → Pages**
2. **Source:** Deploy from a branch
3. **Branch:** `main` / `(root)`
4. Save y esperá 1-2 minutos
5. URL final: `https://TU_USUARIO.github.io/GymXavier/`

### Opción B — Netlify (gratis con repo privado) ⭐ recomendado

1. Cuenta en [netlify.com](https://netlify.com) (login con GitHub)
2. **Add new site → Import an existing project → GitHub**
3. Seleccionás `GymXavier`
4. Build settings: dejar todo vacío (es estático)
5. Deploy → te da una URL tipo `https://random-name.netlify.app`
6. Podés cambiar el subdominio en Settings → Domain

### Opción C — Vercel (gratis con repo privado)

1. Cuenta en [vercel.com](https://vercel.com) (login con GitHub)
2. **Add New → Project → Import** desde tu GitHub
3. Framework preset: `Other` (o lo detecta solo)
4. Deploy → URL tipo `https://gym-xavier.vercel.app`

---

## 📱 Instalar en el celular

1. Abrir la URL deployada en **Chrome** o **Samsung Internet**
2. Menú (⋮) → **"Añadir a pantalla de inicio"** o **"Instalar app"**
3. Queda como app nativa con su ícono

> Para iOS: abrir en Safari → botón compartir → "Agregar a pantalla de inicio"

---

## 🔄 Actualizar la app después de cambios

Cada vez que modifiques archivos:

```bash
git add .
git commit -m "Descripción del cambio"
git push
```

El deploy se actualiza automáticamente (Pages/Netlify/Vercel).

> 💡 Si cambiás archivos cacheados por el SW (HTML, CSS, JS, íconos), bumpeá `CACHE_VERSION` en `sw.js` (ej: `v1` → `v2`) para forzar refresh del cache en los celulares ya instalados.

---

## 🛠️ Próximas mejoras pendientes

- [ ] Historial de pesos levantados por serie
- [ ] Animaciones suaves entre transiciones
- [ ] Modo timer para descansos entre series
- [ ] Export/import de progreso (backup en JSON)
- [ ] Estadísticas semanales
