# Reference Studio · Visión local

Referencias visuales → análisis automático de diseño → parámetros y reconstrucción HTML editable. Aplicación en español publicada en [GitHub Pages](https://javiking190.github.io/reference-studio/).

## Cómo usar

1. Carga una imagen PNG, JPG o WEBP, o pulsa **Probar un ejemplo**.
2. Pulsa **Analizar diseño**. La primera ejecución descarga aproximadamente 700 MB desde Hugging Face y jsDelivr; las siguientes pueden aprovechar la caché del navegador.
3. La IA propone jerarquía, clase de tipografía, retícula, alineación, paleta y bloques de texto/imagen. Las posiciones se expresan como proporciones entre 0 y 1.
4. Revisa la reconstrucción y descarga **Parámetros JSON**, **Variables CSS** o **Reconstrucción HTML editable**. El HTML permite editar sus textos y guardarlo como PDF con la impresión del navegador.
5. **Guardar proyecto** conserva las imágenes, análisis y ajustes en un archivo local. Puedes abrirlo para continuar otro día.

## Motor

- [Qwen3.5 0.8B ONNX OPT](https://huggingface.co/onnx-community/Qwen3.5-0.8B-ONNX-OPT), modelo de visión/lenguaje abierto de Qwen, conversión de ONNX Community, licencia Apache 2.0.
- [Transformers.js 4.3.1](https://github.com/huggingface/transformers.js), con WebGPU y un Worker para ejecutar inferencia fuera del hilo de la interfaz.
- `@huggingface/transformers-structured-output` 4.3.1 limita la generación a un esquema JSON. Las categorías, números y colores se validan antes de utilizarlos. Las salidas del modelo no se ejecutan como HTML o JavaScript.
- Tesseract.js 6.0.1 lee textos y sus cajas mediante OCR local. La segmentación por bandas de píxeles refina regiones de imagen; las fuentes y la descripción visual proceden de la IA. Se registra la procedencia de la geometría en el JSON.
- No requiere cuenta, clave API ni servidor de inferencia. GitHub Pages aloja el código y cada equipo ejecuta su propio análisis.

## Requisitos y límites

Usa un navegador moderno con **WebGPU** y aceleración gráfica, preferentemente Edge o Chrome en un ordenador con memoria disponible. La aplicación comprueba la disponibilidad antes de descargar el modelo. Si el navegador o la GPU no lo admiten, muestra un mensaje; no simula un resultado ni cambia silenciosamente a un modelo en la nube.

Este es un modelo pequeño de prototipado. El OCR, las posiciones y las relaciones de diseño pueden equivocarse; no se identifican fuentes exactas. Las familias tipográficas son sustitutos aproximados. Las imágenes de la reconstrucción son recortes de la referencia original, no imágenes generadas ni elementos vectorizados. No se garantiza una réplica exacta ni preparación profesional para imprenta. Cada referencia se analiza individualmente; una referencia compleja o pequeña puede requerir otro intento. La generación puede tardar varios minutos según la GPU. **Cancelar** detiene el Worker y conserva los ajustes anteriores.

## Privacidad

Las imágenes se leen y analizan localmente. El motor y los pesos del modelo se descargan de terceros; las referencias no se envían a esos servicios ni se publican automáticamente en GitHub. Los archivos de proyecto contienen las imágenes originales y no deberían subirse al repositorio si son privados. No se persiste ninguna clave ni hay llamadas a una API de pago.

## Estructura y publicación

`index.html` incluye la interfaz, estilos, procesamiento, esquema de diseño y el código del Worker en un único archivo. Los pesos del modelo no están incluidos en el repositorio. El Worker importa las dependencias fijadas a versión 4.3.1 desde jsDelivr. Las dependencias y el modelo conservan sus respectivas licencias.

GitHub Pages: **Settings → Pages → Deploy from a branch → main → / (root)**. No hay instalación ni compilación para publicar este paquete.

## Procedencia

Implementación propia inspirada en el objetivo de [humbleteam/extract-design-tokens](https://github.com/humbleteam/extract-design-tokens). No es un fork ni incorpora su SKILL.md. El ejemplo botánico se dibuja con Canvas. La implementación de la aplicación se ofrece bajo licencia MIT; el modelo y las librerías tienen sus licencias independientes.


## Licencia de la aplicación

MIT License

Copyright (c) 2026 Reference Studio contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
