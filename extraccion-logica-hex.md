---
# Prompt para Extraer Lógica del Sistema de Generación y Decodificación HEX en Python

## Objetivo
El objetivo de este análisis es extraer la lógica específica implementada en el sistema Python de codificación y decodificación HEX para aplicarla mediante ingeniería inversa al lector de códigos QR actual, de manera eficiente y adaptable.

## 1. Identificar Componentes Clave
- **Codificador HEX:**
  - Ubicación en el sistema: archivo(s) o módulos relacionados con la generación de códigos HEX.
  - Funciones principales:
    - Entrada de datos para la generación.
    - Transformación o procesamiento interno.
    - Generación de datos finales en el formato HEX.
  - Analice cómo los parámetros de entrada son manipulados y asignados en la salida.

- **Decodificador HEX:**
  - Ubicación del archivo o script responsable.
  - Describir cómo toma la entrada visual (archivos PNG) y cómo estos datos son procesados internamente.
  - Identificar librerías externas, algoritmos específicos y transformaciones secundarias para realizar la decodificación HEX.

## 2. Analizar Lógica de Codificación y Decodificación
- Documentar la estructura de datos utilizada para representar los códigos HEX en ambos procesos.
- Identificar las dependencias necesarias (librerías, herramientas, configuraciones).
- Mapeo claro de los pasos del pipeline para codificar y decodificar:
  1. Entrada de datos.
  2. Normalización y procesamiento.
  3. Representación interna.
  4. Salida final (en formato HEX o información derivada).

## 3. Consideraciones para Ingeniería Inversa
- Evalúe cómo reducir la dependencia de elementos específicos de Python (e.g., librerías exclusivas, estructuras no estándar).
- Identificar partes de la lógica que pueden ser portadas directamente al lector QR (por ejemplo, algoritmos de transformación, normalización de datos).
- Asegurar que la lógica del decodificador pueda extenderse o adaptarse para consumir datos directamente de la salida del lector QR.

## 4. Objetivos de Integración
- Especificar cómo la lógica extraída debe integrarse en los módulos del lector QR (`:processing`, `:decoding`).
- Detallar adaptaciones necesarias en los flujos, incluyendo cambios en las estructuras o representaciones intermedias.

---

Este archivo tiene como propósito servir como guía para extraer, analizar y adaptar la lógica existente del sistema Python de codificación y decodificación HEX al lector de códigos QR desarrollado en este repositorio.