# Laboratorio 2 - Convolución, Correlación y Transformada de Fourier
**Universidad Militar Nueva Granada**  
**Asignatura:** Laboratorio de Procesamiento Digital de Señales  
**Estudiantes:** [Maria Jose Peña Velandia, Joshara Valentina Palacios, Lina Marcela Pabuena]  
**Fecha:** Septiembre 2025  
**Título de la práctica:** Convolución, correlación y transformada de Fourier

## Objetivos
- Comprender la convolución como una operación que permite obtener la respuesta de un sistema discreto ante una entrada determinada.
- Analizar la correlación como medida de similitud entre dos señales.
- Aplicar la Transformada de Fourier como herramienta de análisis en el dominio de la frecuencia.
## PARTE B

##  Resumen

Esta sección del laboratorio se centra en la aplicación de la **correlación cruzada** entre dos señales discretas, **$x[n]$** y **$h[n]$**. El objetivo es determinar la similitud entre ambas señales en función de un desplazamiento temporal. El proceso incluye el cálculo, la representación gráfica del resultado y una discusión sobre la utilidad de esta técnica en el procesamiento digital de señales.

### 1. Definición de Señales
- Señal Cosenoidal
  x1[nTs] = cos(2π * 100 * nTs) = cos(n * π/4)  
- Señal Senoidal
  x2[nTs] = sin(2π * 100 * nTs) = sin(n * π/4)

### 2. Correlación Cruzada
<img width="689" height="393" alt="image" src="https://github.com/user-attachments/assets/8250ec23-9857-4f87-b1a8-dd81d334ff54" />

### 3. ¿En qué situaciones resulta útil aplicar la correlación cruzada en el procesamiento digital de señales?

## PARTE C 
### Resumen 
Esta sección del laboratorio se centra en la convolución y la compresión cruzada , específicamente su relación con la simetría de las señales. Se examina cómo el orden de las señales afecta los resultados de la convolución y cómo la codificación cruzada está intrínsecamente ligada a la convolución de una señal invertida en el tiempo. El objetivo principal es validar la propiedad conmutativa de la convolución y demostrar la conexión entre ambas operaciones.
