# Prompt para el Análisis del Sistema e Ingeniería Inversa

Analiza la arquitectura completa del sistema en este repositorio considerando los siguientes puntos para documentar cada aspecto de manera sistemática:

## 1. Estructura General del Sistema
- **Enumera y explica todos los módulos existentes** (por ejemplo, `:common`, `:capture`, `:processing`, `:decoding`, `:app`) y sus responsabilidades.
- Describe las configuraciones a nivel raíz en `settings.gradle.kts` y `build.gradle.kts`, incluyendo las dependencias globales o scripts de compilación que afectan el flujo de trabajo.

## 2. Análisis Específico de Módulos
- ### Módulo `:common`:
  - Documenta las estructuras de datos compartidas (`QrFrame`, `QrResult`) y las interfaces (`ImageCapturer`, `ImageProcessor`, `QrDecoder`).
  - Aclara cómo se implementan estas interfaces en otros módulos.

- ### Módulo `:capture`:
  - Analiza cómo `CameraXImageCapturer` gestiona el flujo de datos desde CameraX.
  - Explica la gestión del ciclo de vida, la concurrencia o la administración de hilos relacionada con las operaciones de la cámara.

- ### Módulo `:processing`:
  - Explora la lógica para **rotar**, **binarizar** y **mejorar** imágenes (por ejemplo, `applyRotation`, `applyOtsu`).
  - Traza el flujo de transformación de imágenes previo a la decodificación.

- ### Módulo `:decoding`:
  - Detalla cómo el wrapper para ZXing traduce datos del `QrFrame` y realiza la decodificación.
  - Identifica áreas para integrar la lógica personalizada de decodificación HEX, ajustando o añadiendo nuevas rutas de decodificación si es necesario.

- ### Módulo `:app`:
  - Documenta la capa de orquestación (por ejemplo, `MainActivity`, `LectorApplication`).
  - Destaca el flujo de extremo a extremo que cubre las interacciones con todos los otros módulos.

## 3. Interacciones entre Módulos
- Describe cómo los módulos se comunican y transfieren datos (por ejemplo, `Flow<QrFrame>` → `QrResult`).
- Identifica el acoplamiento o las dependencias críticas entre módulos.

## 4. Análisis del Flujo de Datos
- Documenta el flujo de datos paso a paso:
  1. Captura de datos en CameraX.
  2. Preprocesamiento en `:processing`.
  3. Decodificación en `:decoding`.
  4. Visualización o salida en `:app`.

## 5. Plan de Ingeniería Inversa
- Sugiere puntos dentro del sistema existente para:
  - **Reemplazar o extender** la lógica con capacidades de decodificación HEX.
  - Añadir o modificar la funcionalidad con interrupciones mínimas en las características existentes.
- Resalta las áreas de código que requerirían pruebas para asegurar compatibilidad retroactiva.
 
## 6. Sugerencias de Mejora
- Recomienda formas de mejorar la eficiencia, el mantenimiento o el rendimiento, especialmente para dispositivos con capacidades más limitadas.

Objetivo: El propósito es documentar el sistema completo para identificar áreas donde aplicar ingeniería inversa de manera precisa, habilitando la decodificación HEX mientras se preserva la robustez del sistema.