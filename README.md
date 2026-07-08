# 📝 Transcriptor de Audio y Video con IA (Whisper)

**Powered by [script1clic.com](https://script1clic.com)**

Herramienta gratuita para Google Colab que transcribe audio y video usando modelos de la familia Whisper (vía `faster-whisper`), con interfaz visual (Gradio), sin necesidad de saber programar.

---

## ✨ Características

- 🎬 **Audio y video**: acepta mp3, wav, m4a, ogg, flac, aac, mp4, mov, mkv, webm, entre otros. Si subes un video, extrae el audio automáticamente — no hace falta convertir nada antes.
- 🧠 **6 modelos para elegir** desde la interfaz, sin volver a ejecutar celdas, cada uno con sus pros y contras a la vista.
- 🌐 **Casi 100 idiomas**: detección automática del idioma, o selección manual desde una lista desplegable (útil si el audio es corto, ruidoso o tiene acento fuerte).
- ❌ **¿Archivo equivocado?** Recarga la pestaña (F5) para cortarlo al instante, sea que se esté subiendo o ya transcribiendo. No perderás el modelo ya cargado ni necesitas volver a ejecutar celdas.
- 🌍 **Traducción al inglés** con un solo clic (opcional).
- ⏱️ **Marcas de tiempo opcionales** en el texto transcrito.
- 📄 **Exportación en 4 formatos**: texto en párrafos (`.txt`), subtítulos (`.srt` y `.vtt`) y documento de Word (`.docx`).
- ⬇️ **Descargas directas**: los 4 formatos (.txt, .srt, .vtt, .docx) se descargan directamente a tu computadora con un clic, sin abrirse en una pestaña nueva.
- ⚡ **Funciona con GPU o CPU** (con GPU es mucho más rápido).
- 🔗 **Enlace público opcional** para abrir la herramienta desde el celular.

---

## 🚀 Cómo usarlo

1. **Abre el notebook en Google Colab.**
2. *(Recomendado)* Activa la GPU: `Entorno de ejecución` → `Cambiar tipo de entorno` → `T4 GPU`.
3. **Ejecuta la Celda 1** (instalación de dependencias). Tarda 2-4 minutos. Espera el mensaje `✅ Todo listo`. Solo hace falta ejecutarla una vez por sesión.
4. **Ejecuta la Celda 2** para abrir la interfaz visual. Ahí, dentro del navegador, eliges todo lo demás:
   - Sube tu archivo de audio o video.
   - Elige modelo, idioma, traducción y marcas de tiempo.
   - Presiona **"📝 Transcribir"**.
   - Descarga el resultado en el formato que necesites: los 4 archivos se descargan directamente a tu PC con un clic (ya no se abren en una pestaña nueva).
   - Si subiste el archivo equivocado (subiéndose o ya transcribiendo), recarga la pestaña del navegador (F5) — no perderás el modelo ya cargado, solo se reinicia la página.
5. Si algo falla, vuelve a ejecutar la Celda 1 y luego la Celda 2.

> 💡 La única opción que se define *antes* de abrir la interfaz es si quieres un enlace público (para usarlo desde el celular); está arriba de la Celda 2, como un simple check ✅/❌. El modelo y el idioma se eligen todos dentro de la interfaz, y se pueden cambiar las veces que quieras sin volver a ejecutar nada.

---

## 🧠 Modelos disponibles

Todos usan `faster-whisper` (reimplementación optimizada de Whisper, hasta 4x más rápida que el original sin perder precisión). Se puede cambiar de modelo en cualquier momento desde el desplegable de la interfaz.

| Modelo | Etiqueta | Ventajas | Desventajas |
|---|---|---|---|
| `rapido` | ⚡ Rápido | El más veloz de todos | Se equivoca más, sobre todo con acentos fuertes o ruido de fondo |
| `equilibrado` | ✅ Equilibrado (recomendado) | Buen balance velocidad/precisión, ideal para uso diario | — |
| `preciso` | 🎯 Preciso | Más preciso que "Equilibrado" | Tarda 2-3 veces más en procesar |
| `maxima_precision` | 🏆 Máxima precisión | El más preciso, reconoce +99 idiomas | El más lento de todos |
| `turbo` | 🚀 Turbo (rápido, multilenguaje) | Casi tan preciso como "Máxima precisión" pero 6-8 veces más rápido | Algo peor si se activa "Traducir al inglés" |
| `ultra_rapido_ingles` | ⚡⚡ Ultra rápido (solo inglés) | El más rápido de todos | Solo funciona bien con audio en INGLÉS |

> 💡 Para uso diario en español u otro idioma que no sea inglés, se recomienda **"Equilibrado"** o **"Turbo"**. Para inglés y máxima velocidad, **"Ultra rápido"**.

---

## 🔊 Idiomas soportados

Casi 100 idiomas disponibles en el desplegable manual (español, inglés, francés, alemán, italiano, portugués, ruso, japonés, coreano, chino, árabe, hindi, y muchos más), además de la opción **"🔍 Detectar automáticamente"**, que identifica el idioma del audio sin que el usuario tenga que indicarlo.

---

## 📄 Formatos de salida

| Archivo | Descripción |
|---|---|
| `.txt` | Texto transcrito organizado en párrafos, separados por pausas naturales del audio |
| `.srt` | Subtítulos con marcas de tiempo, listos para usar en editores de video |
| `.vtt` | Subtítulos en formato web (compatible con reproductores HTML5) |
| `.docx` | Documento de Word con la transcripción, listo para editar o compartir |

El texto también se puede editar directamente dentro de la interfaz antes de descargarlo. Los 4 botones de descarga guardan el archivo directamente en tu computadora (carpeta de Descargas del navegador); ninguno se abre en una pestaña nueva.

---

## ⚙️ Requisitos

- Cuenta de Google (para usar Google Colab).
- No requiere instalación local ni conocimientos de programación.
- Todas las dependencias (`faster-whisper`, `gradio`, `python-docx`, `ffmpeg`) se instalan automáticamente en la Celda 1.

---

## 🛠️ Solución de problemas

| Problema | Solución |
|---|---|
| Error en la instalación (Celda 1) | Vuelve a ejecutarla. Si persiste, `Entorno de ejecución` → `Reiniciar sesión` y ejecuta la Celda 1 de nuevo |
| "Faltan dependencias" en la Celda 2 | Ejecuta la Celda 1, espera `✅ Todo listo`, luego la Celda 2 |
| Subí el archivo equivocado (subiéndose o ya transcribiendo) | **Recarga la pestaña del navegador (F5).** Gradio no permite cancelar ni reemplazar un archivo a medio proceso — es una limitación de la plataforma, no del código. Recargar corta lo que esté pasando al instante y no pierdes el modelo ya cargado en Colab; solo se reinicia la página, no hace falta volver a ejecutar celdas |
| Falla la transcripción | Puede deberse a un archivo dañado, un formato no soportado, un archivo muy largo para la sesión gratuita de Colab, o memoria insuficiente. Prueba con otro archivo o con un modelo más liviano (por ejemplo "Rápido" en vez de "Máxima precisión") |
| No se detecta voz | Verifica que el archivo realmente contenga audio y prueba con otro archivo |

---

## 📌 Notas

- La primera vez que se usa un modelo, tarda 1-2 minutos en descargarse; después queda en caché y se reutiliza al instante durante el resto de la sesión.
- Los archivos y modelos descargados se pierden al cerrar la sesión de Colab (es normal, no afecta tus resultados ya descargados).
- El enlace público (Gradio `share`) es temporal y se desactiva al cerrar la sesión.

---

*Creado por [script1clic.com](https://script1clic.com)*
