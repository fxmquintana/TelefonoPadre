# 📞 El Teléfono del Padre
### Comunidad Bajo tu Mirada — Alegres Servidores

App Android que entrega frases del Padre, una a la vez (al azar) o navegando la lista completa de 100, con opción de compartir.

---

## ¿Qué incluye esta app?

- **Pantalla principal:** tarjeta con una frase aleatoria sobre el fondo de la Virgen, con el logo de la comunidad.
- **Botón "Llamar de nuevo":** genera otra frase aleatoria (sin repetir la actual).
- **Pestaña "Ver las 100":** lista completa navegable y con buscador (por número o palabra).
- **Compartir:** envía la frase por WhatsApp u otra app, con el logo de la comunidad incluido en el texto.
- Funciona **sin internet** — todo está embebido en la app (frases, fondo, logo).

---

## Cómo generar el APK (igual que hicimos con Pan de Vida)

### Paso 1 — Sube el proyecto a GitHub
1. Ve a **github.com** y entra a tu cuenta
2. Crea un repositorio nuevo llamado `el-telefono-del-padre` (puede ser público)
3. Sube **todos** los archivos de este proyecto tal cual están, incluida la carpeta `.github` (recuerda activar "mostrar archivos ocultos" en Windows si usas el explorador)

### Paso 2 — Deja que GitHub Actions construya el APK
1. En tu repositorio, ve a la pestaña **Actions**
2. Verás el flujo de trabajo corriendo automáticamente (tarda ~8-10 minutos)
3. Espera el ✅ verde

### Paso 3 — Descarga el APK
1. Haz clic en el workflow que terminó en verde
2. Baja hasta la sección **Artifacts**
3. Descarga **el-telefono-del-padre-apk** (es un .zip, adentro está el APK)

### Paso 4 — Instala en el celular
1. Pasa el APK al celular (WhatsApp, cable USB, Drive, etc.)
2. En Android: **Ajustes → Seguridad → Instalar apps desconocidas** → actívalo para la app que uses
3. Abre el APK desde el celular y toca **Instalar**
4. Listo — aparece como **"El Teléfono del Padre"**

---

## Estructura del proyecto

```
el-telefono-del-padre/
├── www/
│   └── index.html          ← toda la app (HTML+CSS+JS, frases y logo embebidos)
├── android-icons/          ← ícono de la app en todas las resoluciones (logo de la comunidad)
├── .github/workflows/
│   └── build-apk.yml       ← construye el APK automáticamente
├── capacitor.config.json
├── package.json
└── README.md
```

### ⚠️ Importante sobre el ícono de la app
El workflow genera el APK con el ícono por defecto de Capacitor la primera vez (porque `npx cap add android` crea la carpeta `android` desde cero en cada build). Para que quede con el **logo de la comunidad** como ícono final, sigue el mismo proceso que usamos en Pan de Vida:

1. Después de la primera build exitosa, en GitHub ve a `android/app/src/main/res/`
2. Reemplaza el contenido de cada carpeta `mipmap-*` con los archivos que están en `android-icons/mipmap-*` de este proyecto (mismo nombre, los sobrescribes)
3. Sube esos cambios (commit) y se vuelve a generar el APK, ya con el logo correcto

Si prefieres, dime cuando tengas el repo creado y te guío paso a paso para hacer ese reemplazo igual que la vez pasada.

---

## ¿Cómo agregar o editar frases más adelante?

Abre `www/index.html`, busca la línea que empieza con:
```js
const FRASES = [
```
Ahí está el listado completo en formato `{ "id": número, "texto": "frase" }`. Puedes agregar, quitar o editar directamente ahí y volver a subir el archivo a GitHub — el Action se dispara solo y genera un nuevo APK.

---

## ¿Necesitas ayuda?
Vuelve a esta conversación (o pídeme que retome "El Teléfono del Padre") y seguimos desde donde quedamos.
