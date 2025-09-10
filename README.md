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

## Código en Python

```python
import numpy as np
import matplotlib.pyplot as plt

# Parámetros
Ts = 1.25e-3   # periodo de muestreo
n = np.arange(9)  # muestras 0 <= n <= 8
f = 100        # frecuencia 100 Hz

# Señales discretas
x1 = np.cos(2 * np.pi * f * n * Ts)   # x1[n] = cos(2π·100·n·Ts)
x2 = np.sin(2 * np.pi * f * n * Ts)   # x2[n] = sin(2π·100·n·Ts)

# Correlación cruzada
correlacion = np.correlate(x1, x2, mode='full')
print("Correlación cruzada (vector resultado):")
print(correlacion)

# Eje de desplazamientos (lags)
t_corr = np.arange(-len(n) + 1, len(n))

# Gráfica de la correlación cruzada
plt.figure(figsize=(8, 4))
plt.stem(t_corr, correlacion)
plt.axhline(0, color="red")  # línea en y=0 para referencia
plt.xlabel("Desplazamiento")
plt.ylabel("Correlación")
plt.title("Correlación cruzada entre x1[n] y x2[n]")
plt.grid()
plt.show()

## 2. Resultados de Colab

Vector de correlación cruzada (`mode='full'`):

```
[-2.44929360e-16 -7.07106781e-01 -1.50000000e+00 -1.41421356e+00
 -2.54671001e-16  2.12132034e+00  3.50000000e+00  2.82842712e+00
 -2.28847549e-17 -2.82842712e+00 -3.50000000e+00 -2.12132034e+00
  4.55531587e-16  1.41421356e+00  1.50000000e+00  7.07106781e-01
  0.00000000e+00]
```

La gráfica muestra los valores de correlación cruzada en el rango de desplazamientos `m = -8 … 8`.

## 3. Análisis
Frente al análisis del código destaca que los valores de tiempo (Ts) y frecuencia (f) ya habian sido establecidos por las propias fórmulas estbalecidas. En cuanto al resultado de su tabla destaca que el eje X tiene valores de -8 a 8, lo que indica que estás observando un rango de desplazamientos entre las dos señales y desde -8 hasta +8 muestras; el eje Y tiene un rango de -3 a 3, lo que significa que los valores de correlación cruzada varían en este intervalo.

La forma general de la gráfica muestra un comportamiento de simetría con respecto al eje. Esta simetría es típica cuando se correlacionan señales periódicas con un desfase constante. La gráfica parece tener un pico en y=4 y luego decae en ambos sentidos. Esto refleja un patrón de correlación común entre señales como seno y coseno.

Por último, la gráfica tiene un comportamiento que sigue la naturaleza de las señales seno y coseno, que están desfasadas. El valor cero es el lugar donde las señales son ortogonales y no se correlaciona. Los desplazamientos negativos y positivos reflejan el desfase de las señales en distintas posiciones a lo largo del tiempo, con una caída de la correlación a medida que las señales se desalinean.



### ¿En qué situaciones resulta útil aplicar la correlación cruzada en el procesamiento digital de señales?
## 4. Aplicaciones de la correlación cruzada en DSP

La correlación cruzada es útil en múltiples contextos de procesamiento digital de señales, como:
**Estimación de retardo/desfase** → sincronización de señales, localización de fuentes (radar, sonar, acústica).  
**Detección de patrones o plantillas** (*matched filtering*), útil para encontrar secuencias conocidas en ruido.  
**Comunicaciones digitales** → sincronización de símbolos, detección de preámbulos o códigos de inicio.  
**Señales biomédicas** → análisis de retardo entre ECG y PPG, o entre distintos sensores.  
**Procesamiento de imágenes** → registro y alineación de imágenes desplazadas.  
**Control de calidad** → comparación de señales de vibración o fallas con patrones de referencia.



## PARTE C 
### Resumen 
Esta sección del laboratorio se centra en la convolución y la compresión cruzada , específicamente su relación con la simetría de las señales. Se examina cómo el orden de las señales afecta los resultados de la convolución y cómo la codificación cruzada está intrínsecamente ligada a la convolución de una señal invertida en el tiempo. El objetivo principal es validar la propiedad conmutativa de la convolución y demostrar la conexión entre ambas operaciones.
