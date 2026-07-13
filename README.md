# ⛪ Intelly - Dashboard Eclesiástico de Predicaciones y Eventos

Un sistema moderno, ágil y visualmente hermoso diseñado para organizar las predicaciones, coordinadores, eventos eclesiásticos y automatizar notificaciones diarias de forma 100% gratuita usando **GitHub Pages** y **GitHub Actions**.

Inspirado en una estética limpia de colores pastel, ideal para visualizarse tanto en computadoras como en dispositivos móviles de manera perfectamente sincronizada.

---

## 🚀 Características Clave

1. **Dashboard Visual Intuitivo**: Widgets coloridos que te muestran la próxima predicación, el evento más cercano, estadísticas de libros bíblicos estudiados y total de predicadores activos.
2. **Gráfico de Libros Bíblicos**: Gráficos interactivos generados con `Chart.js` que se actualizan automáticamente según las predicaciones agendadas.
3. **Descargador de Calendario Mensual**: Un botón especial que renderiza el calendario actual y lo descarga como imagen `.png` de alta definición usando `html2canvas`, listo para enviarse al grupo de WhatsApp de avisos.
4. **Notificaciones Automáticas vía WhatsApp/SMS**: Flujo de automatización diario mediante un script de Python ejecutado por **GitHub Actions** que alerta a los predicadores asignados 24 horas antes de su mensaje.
5. **PC & Móvil Sincronizados**: Diseñado con un entorno responsivo (Tailwind CSS) y un login simulado que guarda tu base en caché local (`localStorage`) y permite exportarla o importarla fácilmente en formato JSON.

---

## 📁 Estructura del Proyecto

* `index.html` : Interfaz visual con la estética pastel de tu mockup.
* `data.json` : Base de datos inicial con los predicadores, sermones y eventos.
* `js/app.js` : Controladores de renderizado, cálculo de KPIs, gráficos interactivos e importación/exportación.
* `scripts/notificar.py` : Script de automatización en Python que lee las fechas y envía los mensajes.
* `.github/workflows/notify.yml` : Proceso automático diario de GitHub que ejecuta la automatización a las 9:00 UTC.

---

## 🛠️ Cómo subirlo a GitHub y ponerlo en marcha (Paso a Paso)

### Paso 1: Subir el contenido a tu Repositorio
1. Crea un nuevo repositorio en tu cuenta de GitHub (ejemplo: `dashboard-iglesia`).
2. Descomprime este archivo `.zip` en tu computadora.
3. Sube todos los archivos de la carpeta directamente a la rama principal (`main` o `master`) de tu repositorio.

### Paso 2: Activar la página web (GitHub Pages)
1. En tu repositorio de GitHub, dirígete a **Settings** (Configuración) en el menú superior.
2. En la barra lateral izquierda, haz clic en **Pages**.
3. En la sección *Build and deployment*, bajo *Source*, selecciona **Deploy from a branch**.
4. En *Branch*, elige la rama **main** (o `master`) y la carpeta `/ (root)`. Haz clic en **Save** (Guardar).
5. ¡Listo! En un par de minutos, GitHub te dará un enlace público (ej. `https://tu-usuario.github.io/dashboard-iglesia/`) donde podrás abrir tu Dashboard desde tu celular o cualquier computadora.

### Paso 3: Configurar las Notificaciones de WhatsApp Gratuitas
El script de Python integrado utiliza **CallMeBot**, un servicio gratuito para enviar mensajes de WhatsApp automatizados:
1. Pídele al número de WhatsApp de la iglesia que agregue el contacto de CallMeBot y obtenga su **API Key** siguiendo las instrucciones en [https://www.callmebot.com/](https://www.callmebot.com/) (es rápido y gratuito, solo requiere enviar un mensaje de texto para activarlo).
2. En tu repositorio de GitHub, ve a **Settings** > **Secrets and variables** > **Actions**.
3. Haz clic en **New repository secret**.
4. Nombra al secreto: `CALLMEBOT_API_KEY` y pega la API key que te entregó el bot. ¡Y listo! GitHub Actions ejecutará el script diariamente de manera automática y silenciosa.

---

## 💾 Guardar Cambios Permanentemente

Dado que GitHub Pages aloja páginas estáticas, cuando agregues, edites o elimines predicaciones en tu celular o PC, estos cambios se guardarán automáticamente en la memoria de tu dispositivo (`localStorage`). 

Para que los cambios se sincronicen en **todos los dispositivos** de la iglesia de forma permanente:
1. Abre tu Dashboard y ve a la barra lateral izquierda.
2. Haz clic en **"Guardar Base JSON"**.
3. Se abrirá un recuadro con el código de tu base de datos actualizada. Haz clic en **"Copiar Código"**.
4. Ve a tu repositorio de GitHub, edita el archivo `data.json` pegando ese código y guarda los cambios (*Commit*). 
5. ¡Tu web se actualizará automáticamente en todos los celulares y computadoras de la iglesia con los nuevos datos cargados!

---
*Diseñado con cariño para la edificación y orden de la congregación.* ⛪
