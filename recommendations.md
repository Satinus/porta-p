# Recomendaciones para ARCHITECTURE.md

---

## 1. Estructura General
- Asegúrate de que todas las interfaces en el módulo `:common` manejen adecuadamente errores y validaciones.
- Documenta claramente el uso de cada interfaz para mantener la consistencia entre módulos.

## 2. Recomendaciones Específicas por Módulo

### **Módulo `:common` (Núcleo)**
- Considera agregar clases utilitarias para manejar excepciones y garantizar una gestión de errores consistente entre interfaces.
- Incluye validaciones para la clase `QrFrame` para evitar datos geométricos inválidos.

### **Módulo `:capture` (Entrada de Cámara)**
- Mejora la flexibilidad de resoluciones soportadas (por ejemplo, selección adaptativa de resolución).
- Incluye opciones para optimización dinámica del rendimiento que equilibren velocidad y claridad de imagen.

### **Módulo `:processing` (Algoritmos de Imagen)**
- Optimiza las operaciones de rotación y umbralización de imagen para reducir los tiempos de cómputo en dispositivos de gama baja.
- Evalúa alternativas más ligeras para transformaciones de imagen dependientes del dispositivo para lograr un menor consumo de recursos.

### **Módulo `:decoding` (Lógica QR)**
- Incluye métricas de rendimiento y registros detallados durante la decodificación para resolver fallos de QR.
- Considera pruebas y comparaciones de la biblioteca ZXing con varios formatos de QR y orientaciones para verificar su fiabilidad.

### **Módulo `:app` (Orquestación y UI)**
- Transiciona de una inyección de dependencias manual a un framework como Hilt/Dagger para lograr mejor escalabilidad y mantenimiento.
- Introduce soporte multilingüe o mecanismos de retroalimentación del usuario dentro del `OverlayView` para mejorar la accesibilidad.

---

## 3. Diagrama de Dependencias
- Revisa periódicamente las interdependencias entre módulos para reducir el acoplamiento y garantizar la escalabilidad del proyecto.
- Explora la viabilidad de convertir el módulo central `:common` en una biblioteca independiente para mayor portabilidad.

## 4. Recomendaciones sobre el Flujo de Datos
- Mejora el manejo de errores en todo el flujo de pipeline, especialmente para excepciones específicas del dispositivo.
- Introduce mecanismos de reintento en los flujos de `startCapture()` y decodificación, para aumentar la robustez en entornos dinámicos.
- Agrega registros de tiempo de ejecución y análisis de rendimiento para capturar conocimientos de depuración en tiempo real.