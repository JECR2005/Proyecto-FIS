# 🖐️ SeñaTranslate — Traductor a Lengua de Señas Mexicana

**SeñaTranslate** es una aplicación web educativa que traduce texto en español e inglés a **Lengua de Señas Mexicana (LSM)**. Presenta cada seña como una tarjeta visual animada con emoji representativo, instrucciones de movimiento y categoría gramatical. Para palabras sin seña registrada, ofrece deletreo manual automático.

---

## 📸 Vista previa

> _Interfaz limpia con modo claro/oscuro, panel de entrada y salida lado a lado, y tarjetas de señas animadas._

---

## ✨ Funcionalidades

- **Traducción a LSM** — convierte frases cotidianas a una secuencia ordenada de señas mexicanas.
- **Detección automática de idioma** — identifica español e inglés sin configuración previa; también permite forzar el idioma manualmente.
- **Frases compuestas** — reconoce expresiones de varias palabras (`buenos días`, `muchas gracias`, `¿cómo estás?`, etc.) antes de traducir por separado.
- **Deletreo manual** — cuando una palabra no tiene seña registrada, indica cómo deletrearla letra por letra en LSM.
- **Tarjetas visuales animadas** — cada seña muestra emoji, categoría (`Saludo`, `Verbo`, `Lugar`…) e instrucción de movimiento.
- **Historial local** — guarda hasta 10 traducciones recientes en `localStorage` con opción de repetirlas.
- **Modo claro / oscuro** — preferencia persistida entre sesiones.
- **Diseño responsivo** — funciona en escritorio y móvil.

---

## 🗂️ Estructura del proyecto

```
sena-translate/
├── index.html   # Estructura HTML y accesibilidad (ARIA)
├── styles.css   # Diseño completo con variables CSS y modo oscuro
└── app.js       # Lógica de traducción, historial y tema
```

No requiere frameworks, dependencias ni proceso de compilación.

---

## 🚀 Uso

Clona el repositorio y abre `index.html` directamente en tu navegador:

```bash
git clone https://github.com/tu-usuario/sena-translate.git
cd sena-translate
# Abre index.html en tu navegador favorito
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

O arrastra el archivo `index.html` a cualquier pestaña de tu navegador. No necesita servidor ni conexión a internet (solo carga la fuente Inter desde Google Fonts).

---

## 📖 Diccionario LSM incluido

El diccionario cubre más de **100 palabras y 12 frases compuestas** distribuidas en estas categorías:

| Categoría | Ejemplos |
|---|---|
| Saludos | hola, adiós, buenos días, buenas noches |
| Cortesía | gracias, por favor, de nada, muchas gracias |
| Familia | mamá, papá, hermano, familia, amigo |
| Emociones | feliz, triste, enojado, miedo |
| Necesidades | ayuda, agua, comida, emergencia, urgente |
| Lugares | casa, escuela, hospital, baño, calle, tienda |
| Preguntas | ¿cómo estás?, dónde, qué, cuándo, quién |
| Transporte | autobús, taxi, ir, venir |
| Tiempo | hoy, mañana, ayer, día, tarde, noche |
| Objetos | teléfono, dinero, número |
| Adjetivos | bien, mal, grande, pequeño, caliente, frío |

---

## ⌨️ Atajos de teclado

| Acción | Atajo |
|---|---|
| Traducir | `Ctrl + Enter` / `Cmd + Enter` |

---

## ⚙️ Arquitectura interna (`app.js`)

| Función | Descripción |
|---|---|
| `normalizeText(text)` | Elimina acentos, convierte a minúsculas y limpia puntuación |
| `detectLanguage(text)` | Puntúa palabras clave en ES/EN para detectar el idioma |
| `textToSigns(text)` | Flujo principal: frases → palabras → deletreo de fallback |
| `renderSigns(sequence)` | Genera las tarjetas visuales en el DOM |
| `saveHistoryItem(...)` | Persiste la traducción en `localStorage` |
| `applyTheme(theme)` | Alterna y guarda la preferencia de tema |

---

## ♿ Accesibilidad

- Etiquetas `aria-label` y `aria-live` en zonas dinámicas.
- Regiones semánticas con `<header>`, `<main>`, `<nav>`, `<section>`, `<article>`, `<aside>` y `<footer>`.
- Botón de tema con `aria-pressed`.
- Contraste de colores adecuado en ambos modos.

---

## ⚠️ Aviso importante

> Este proyecto es un **prototipo educativo**. La LSM es una lengua viva con gramática espacial propia y variaciones regionales. Para comunicación formal o de salud, consulta siempre con una **persona intérprete LSM certificada**.

---

## 🛠️ Posibles mejoras futuras

- Integración con la API de Claude para traducir frases más complejas y contextuales.
- Incorporar animaciones SVG o videos reales de señas.
- Ampliar el diccionario con más regionalismos mexicanos.
- Síntesis de voz para reproducir el texto de entrada.
- Exportar la secuencia de señas como imagen o PDF.

---

## 📄 Licencia

Distribuido bajo la licencia **MIT**. Consulta el archivo `LICENSE` para más detalles.
