# 🌿 Bot Marley

Un chatbot inspirado en el espíritu, los valores y la filosofía de vida de Bob Marley y el movimiento Rastafari — construido como proyecto de aprendizaje, 100% en el navegador (HTML + JS + Claude API), sin backend.

## ¿Cómo funciona?

- Es una sola página (`index.html`) que corre completamente en tu navegador.
- Usa la [API de Claude](https://docs.claude.com) de Anthropic para generar las respuestas en tiempo real.
- Un *system prompt* le da a Claude la "personalidad Marley": temas de unidad, esperanza, resiliencia, naturaleza, justicia y alegría — comunicados con calidez y en sus propias palabras.
- Tu API key se guarda únicamente en el `localStorage` de tu navegador. Nunca se envía a ningún servidor nuestro (no existe un backend) — solo viaja directamente de tu navegador a la API de Anthropic.

## Cómo usarlo

1. Consigue una API key en [console.anthropic.com](https://console.anthropic.com/) (Settings → API Keys).
2. Abre `index.html` en tu navegador (doble clic, o publícalo en GitHub Pages — ver abajo).
3. Pega tu API key en el campo de arriba y presiona **Guardar**.
4. ¡Empieza a conversar!

## Publicarlo en GitHub Pages

1. Crea un repositorio nuevo en GitHub y sube `index.html` (y este `README.md`).
2. Ve a **Settings → Pages**, selecciona la rama `main` y la carpeta raíz (`/`).
3. GitHub te dará una URL pública (algo como `https://tu-usuario.github.io/bot-marley/`).
4. Comparte el link — cada persona que lo visite usará **su propia** API key, guardada solo en su navegador.

## Sobre las letras y los derechos de autor

Este proyecto **no contiene ni reproduce letras de canciones de Bob Marley**. El *system prompt* instruye explícitamente al modelo para que:

- hable en su propio lenguaje, inspirándose en los temas y el espíritu asociados a Bob Marley (unidad, esperanza, naturaleza, resistencia pacífica, alegría),
- pueda mencionar **títulos** de canciones cuando sea relevante,
- pero **nunca** reproduzca versos, estrofas o fragmentos extensos de letras —ni siquiera parafraseados de cerca—, limitándose como máximo a frases muy cortas y ampliamente conocidas, integradas con naturalidad.

Este es un proyecto educativo y no oficial, sin afiliación con la familia Marley, sus discográficas o sus derechohabientes. Las marcas y nombres mencionados pertenecen a sus respectivos dueños.

## Notas técnicas / de costos

- Modelo usado: `claude-haiku-4-5` (rápido y económico).
- `max_tokens` está limitado a 400 por respuesta y el historial de conversación se trunca a los últimos 12 mensajes, para mantener el costo de la API bajo control.
- La llamada incluye el header `anthropic-dangerous-direct-browser-access: true`, necesario para invocar la API de Anthropic directamente desde el navegador (en vez de desde un servidor). Ten presente que esto expone tu API key en el cliente — por eso cada persona usa la suya propia, y nunca debes compartir la tuya.

## Licencia

Código abierto para fines educativos. Úsalo, modifícalo y compártelo libremente — solo recuerda no incluir contenido con derechos de autor (como letras completas) en tus propias versiones.
