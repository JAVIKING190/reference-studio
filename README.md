# Reference Studio

Laboratorio editorial en español: referencias visuales → muestras de color, geometría y decisiones de diseño exportables.

## Probar

Abre [la aplicación](https://javiking190.github.io/reference-studio/) y pulsa **Probar un ejemplo**, o carga PNG/JPG/WEBP. Asigna roles a los colores, dibuja zonas sobre la referencia y exporta JSON, CSS o una plantilla HTML para imprimir como PDF. Guarda tu proyecto para conservar las imágenes y decisiones.

## Alcance

Extracción local de colores mediante agrupación de píxeles; muestreo puntual; referencias múltiples; zonas con coordenadas normalizadas; parámetros editoriales manuales; exportaciones y brief para un asistente de visión. Las imágenes se procesan en el navegador y no se suben al repositorio.

No incluye OCR, reconocimiento de fuentes ni interpretación automática con IA. La plantilla es una composición nueva, no una reconstrucción de la captura. El brief se utiliza adjuntando también las imágenes originales a un asistente. Integrar visión automática requerirá un servicio externo; GitHub Pages aloja la interfaz estática.

## Estructura

`index.html` contiene HTML, CSS y JavaScript en un único archivo autónomo. No hay dependencias, claves API ni compilación. Para publicar: Settings → Pages → Deploy from a branch → main → / (root).

## Procedencia

Implementación independiente inspirada en [humbleteam/extract-design-tokens](https://github.com/humbleteam/extract-design-tokens), una skill de instrucciones publicada bajo MIT. Este proyecto no es un fork ni incluye su SKILL.md. El ejemplo botánico se genera con Canvas.

## Licencia

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
