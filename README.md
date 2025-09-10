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

# PARTE A

## Resumen

Este repositorio documenta la primera fase de un laboratorio enfocado en el procesamiento de señales discretas. El objetivo principal fue calcular la convolución de dos señales, $x[n]$ y $h[n]$, definidas a partir de datos personales (cédula y código estudiantil, respectivamente). El proceso incluyó una **convolución manual**, seguida de una **verificación computacional** utilizando Python.

### 1. Definición de Señales y Convolución Manual

Las señales de entrada, **$x[n]$** y **$h[n]$**, se definieron usando los dígitos de la cédula y el código estudiantil de cada una de las integrantes. La convolución, $y[n] = x[n] * h[n]$, se calculó paso a paso de forma manual, documentando cada operación.

- **Señal $y[n]$**: María José
  ![conv majo](https://github.com/user-attachments/assets/a3fb18ed-6df5-4a69-818a-dac87e23b746)

- **Señal $y[n]$**: Valentina
 ![conv vale](https://github.com/user-attachments/assets/23e43f71-4eb9-49c3-9fa7-58743fa4ac29)

- **Señal $y[n]$**: Lina
  ![conv lina](https://github.com/user-attachments/assets/153582a5-05e7-4d07-b0c3-720d2b422c82)


### 2. Representación Gráfica y Secuencial

Se generaron las representaciones gráficas y secuenciales de las señales originales ($x[n]$, $h[n]$) y de la señal resultante ($y[n]$). Este paso se realizó a mano para visualizar el desplazamiento y la superposición de las señales.

- **Gráfica señal $y[n]$**: María José
  ![conv majo a mano](https://github.com/user-attachments/assets/3b62d600-5d17-4355-b457-d766a14de749)

- **Gráfica señal $y[n]$**: Valentina
  ![conv vale a mano](https://github.com/user-attachments/assets/fce6176d-1b8e-49ad-932e-ab8a7b29ed86)

- **Gráfica señal $y[n]$**: Lina
  ![conv lina a mano](https://github.com/user-attachments/assets/514129b4-bbf1-4e4d-9e9f-46781c67801a)


### 3. Verificación Computacional con Python

Para validar los resultados manuales, se implementó el cálculo de la convolución en Python. Se utilizó la librería **NumPy** para manipular las señales como arreglos y verificar la precisión del cálculo.

<pre>
  # Datos Majo
x = np.array([1,0,1,1,0,8,5,6,7,9])   # cédula
h = np.array([5,6,0,0,8,7,6])         # código estudiantil

# Gráfica de h[n]
t = np.arange(len(h))
plt.figure(figsize=(8, 4))
plt.stem(t, h)
plt.xlabel('n')
plt.ylabel('h [n]')
plt.title('h [n] María José')
plt.grid()
plt.show()

# Gráfica de x[n]
t = np.arange(len(x))
plt.figure(figsize=(8, 4))
plt.stem(t, x)
plt.xlabel('n')
plt.ylabel('x [n]')
plt.title('x [n] María José')
plt.grid()
plt.show()

# Convolución
y = np.convolve(x, h, mode='full')
print("Señal convolución entre h [n] y x [n], María José:")
print(y)

# Gráfica de y[n]
t = np.arange(len(y))
plt.figure(figsize=(10, 4))
plt.stem(t, y)
plt.xlabel('n')
plt.ylabel('y [n]')
plt.title('Convolución y [n] = x [n] * h [n]')
plt.grid()
plt.show()
</pre> 

## Gráfica Código Estudiantil María José
<img width="678" height="394" alt="Grafica Codigo estudiantil majo" src="https://github.com/user-attachments/assets/1aaf8e9b-b287-4250-b6c0-6ca1ea3164a4" />

## Gráfica Cédula María José
<img width="678" height="394" alt="Grafica cedula majo" src="https://github.com/user-attachments/assets/6bef032c-da47-4662-96d0-f239514e7249" />

## Gráfica Convolución María José
<img width="850" height="394" alt="convolución Majo" src="https://github.com/user-attachments/assets/7a8b5d55-60a3-4030-b6a4-b4961f4605ad" />

<pre>
# Datos de Valentina
x = np.array([1,0,2,3,3,7,1,2,5,9])   # cédula
h = np.array([5,6,0,0,8,1,7])         # código estudiantil

# Gráfica de h[n]
t = np.arange(len(h))
plt.figure(figsize=(8, 4))
plt.stem(t, h)
plt.xlabel('n')
plt.ylabel('h[n]')
plt.title('h[n] Valentina')
plt.grid()
plt.show()

# Gráfica de x[n]
t = np.arange(len(x))
plt.figure(figsize=(8, 4))
plt.stem(t, x)
plt.xlabel('n')
plt.ylabel('x[n]')
plt.title('x[n] Valentina')
plt.grid()
plt.show()

# Convolución
y = np.convolve(x, h, mode='full')
print("Señal convolución entre h[n] y x[n], Valentina:")
print(y)

# Gráfica de y[n]
t = np.arange(len(y))
plt.figure(figsize=(10, 4))
plt.stem(t, y)
plt.xlabel('n')
plt.ylabel('y[n]')
plt.title('Convolución y[n] = x[n] * h[n]')
plt.grid()
plt.show()
</pre> 
## Gráfica Código Estudiantil Valentina
<img width="678" height="393" alt="Grafica Codigo estudiantil Vale" src="https://github.com/user-attachments/assets/8b83cab4-9bdc-4b25-9e0c-d32b3719cae3" />

## Gráfica Cédula Valentina
<img width="678" height="393" alt="Grafica cedula vale" src="https://github.com/user-attachments/assets/e2d26cb3-f49a-40fb-ac49-1b276941aa10" />

## Gráfica Convolución Valentina
<img width="850" height="394" alt="convolución Vale" src="https://github.com/user-attachments/assets/59ea24ef-ce9b-40b7-a16b-fa83f87d4260" />

<pre>
# Datos de Lina
x = np.array([1,0,1,1,0,8,2,1,5,0])   # cédula
h = np.array([5,6,0,0,8,2,2])         # código estudiantil

# Gráfica de h[n]
t = np.arange(len(h))
plt.figure(figsize=(8, 4))
plt.stem(t, h)
plt.xlabel('n')
plt.ylabel('h[n]')
plt.title('h[n] Lina')
plt.grid()
plt.show()

# Gráfica de x[n]
t = np.arange(len(x))
plt.figure(figsize=(8, 4))
plt.stem(t, x)
plt.xlabel('n')
plt.ylabel('x[n]')
plt.title('x[n] Lina')
plt.grid()
plt.show()

# Convolución
y = np.convolve(x, h, mode='full')
print("Señal convolución entre h[n] y x[n], Lina:")
print(y)

# Gráfica de y[n]
t = np.arange(len(y))
plt.figure(figsize=(10, 4))
plt.stem(t, y)
plt.xlabel('n')
plt.ylabel('y[n]')
plt.title('Convolución y[n] = x[n] * h[n]')
plt.grid()
plt.show()
</pre> 
## Gráfica Código Estudiantil Lina
<img width="678" height="393" alt="Grafica Codigo estudiantil Lina" src="https://github.com/user-attachments/assets/6fbecc7b-b591-4250-8839-b40a92d5a6e7" />

## Gráfica Cédula Lina
<img width="678" height="393" alt="Grafica cedula lina" src="https://github.com/user-attachments/assets/d56ceb1a-93f1-49ea-afb2-bd100345d890" />

## Gráfica Convolución Lina
<img width="850" height="394" alt="convolución Lina" src="https://github.com/user-attachments/assets/fbcbcc0f-cf23-4089-8a8a-2a91edeaf5a6" />


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

La gráfica muestra los valores de correlación cruzada en el rango de desplazamientos `m = -8 … 8`.

## 3 Análisis
Frente al análisis del código destaca que los valores de tiempo (Ts) y frecuencia (f) ya habian sido establecidos por las propias fórmulas estbalecidas. En cuanto al resultado de su tabla destaca que el eje X tiene valores de -8 a 8, lo que indica que estás observando un rango de desplazamientos entre las dos señales y desde -8 hasta +8 muestras; el eje Y tiene un rango de -3 a 3, lo que significa que los valores de correlación cruzada varían en este intervalo.

La forma general de la gráfica muestra un comportamiento de simetría con respecto al eje. Esta simetría es típica cuando se correlacionan señales periódicas con un desfase constante. La gráfica parece tener un pico en y=4 y luego decae en ambos sentidos. Esto refleja un patrón de correlación común entre señales como seno y coseno.

Por último, la gráfica tiene un comportamiento que sigue la naturaleza de las señales seno y coseno, que están desfasadas. El valor cero es el lugar donde las señales son ortogonales y no se correlaciona. Los desplazamientos negativos y positivos reflejan el desfase de las señales en distintas posiciones a lo largo del tiempo, con una caída de la correlación a medida que las señales se desalinean.



### 4 ¿En qué situaciones resulta útil aplicar la correlación cruzada en el procesamiento digital de señales?
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

Lo primero fue generar la señal y extraerla en el laboratorio: 

### Adquisición de la Señal con DAQ
Para la adquisición de la señal, se implementó un sistema basado en un dispositivo de adquisición de datos (DAQ). Este proceso requirió la integración de dos librerías críticas:

- La librería del driver del DAQ que nos proporciona las funciones que permiten la comunicación directa con el hardware del dispositivo.
- La librería del DAQque nos ofrece una interfaz de programación que simplifica la configuración de los canales de entrada, la frecuencia de muestreo y otras especificaciones del proceso de adquisición.

### Configuración y Pruebas Iniciales
El proceso de adquisición comenzó con la generación de una señal biológica EOG (electrooculograma) utilizando un generador de señales. Se configuró la frecuencia de esta señal en 1 Hz para simular un movimiento ocular lento.

Antes de la adquisición final, se realizó una prueba en el simulador del driver. Durante esta prueba, se verificaron los siguientes parámetros de la señal:

- Amplitud máxima (Max): 2 V
- Amplitud mínima (Min): -1 V
- Tasa de muestreo (Rate Hz): 4000 Hz
![Driverseñal](https://github.com/user-attachments/assets/24c7bc9b-621d-488f-9967-ef1aafdb2fdb)

### Extracción y Visualización de las Gráficas
Para la extracción y visualización de la señal adquirida, se utilizó un script de Python proporcionado por la docente. Este código se ejecutó en el entorno de desarrollo Anaconda/Spyder. El script permitió procesar los datos capturados por el DAQ y generar las representaciones gráficas necesarias para el análisis.

A continuación, se presentan la gráfica obtenida, la cual muestra la señal EOG adquirida con sus características de amplitud y frecuencia:
![fc4000](https://github.com/user-attachments/assets/74269f0d-b4a4-4d55-b085-6e8ad735fcf9)


## Código en Python

```python

from google.colab import drive
import numpy as np
import matplotlib.pyplot as plt

# Montar Google Drive
drive.mount('/content/drive')

# Ruta completa al archivo en tu Drive
ruta = "/content/drive/MyDrive/GITTHUB/extraccion_señal_1.npy"

# Cargar la señal
senal_en_colab = np.load(ruta)

# Parámetros
fs = 4000
duracion = 3
t = np.arange(len(senal_en_colab)) / fs

# Graficar la señal
plt.plot(t, senal_en_colab)
plt.axis([0, duracion, -1, 2.5])
plt.grid()
plt.title(f"Señal Generada")
plt.show()
```
<img width="428" height="326" alt="Primera imagen" src="https://github.com/user-attachments/assets/5e94628f-48da-45ff-ab30-cce4af80cfbf" />


## 1.	Determine la frecuencia de Nyquist para la señal generada
La frecuencia de Nyquist se utiliza como referencia fundamental para garantizar un muestreo adecuado de la señal. Dado que corresponde a la mitad de la frecuencia de muestreo original, establece el límite máximo de información que puede analizarse sin que aparezca aliasing. A partir de este valor se define la nueva frecuencia de muestreo (4·Nyquist), lo que permite digitalizar la señal con mayor densidad de puntos, mejorando la resolución temporal y la representación en el dominio de la frecuencia sin alterar su contenido espectral real.
```python
# Frecuencia de Nyquist
fs = 4000  # frecuencia de muestreo usada
f_nyquist = fs / 2
print(f"Frecuencia de Nyquist = {f_nyquist} Hz")
```
Donde el resultado fue: Frecuencia de Nyquist = 2000.0 Hz

## 2.	Digitalice la señal usando una frecuencia de muestreo de 4 veces la frecuencia de Nyquist
La digitalización a una frecuencia de muestreo equivalente a 4·Nyquist permite obtener una señal con mayor densidad de muestras en el mismo intervalo de tiempo. Este sobre-muestreo no añade información nueva, pero mejora la resolución temporal y espectral, facilitando el análisis y la comparación con la señal original.
```python
from scipy.signal import resample

# Nueva frecuencia de muestreo
fs_digital = 4 * f_nyquist   # 8000 Hz

# Duración de la señal
duracion = len(senal_en_colab) / fs

# Número de muestras nuevas
N_new = int(duracion * fs_digital)

# Re-muestreo
senal_digital = resample(senal_en_colab, N_new)

t_digital = np.arange(N_new) / fs_digital

print(f"Muestras originales: {len(senal_en_colab)}, nuevas: {len(senal_digital)}")
```
Donde el resultado fue: Muestras originales: 24000, nuevas: 48000

### 3. Carcterizar la señal obteniendo: 
### a.	Media, mediana, desviación estándar, máximo, mínimo
La caracterización estadística de la señal digitalizada permite describir su comportamiento de manera cuantitativa. A través de medidas como la media, mediana, desviación estándar, máximo y mínimo, se obtiene información sobre la tendencia central, la dispersión y el rango de amplitudes de la señal
```python
# Estadísticos de la señal digitalizada
media = np.mean(senal_digital)
mediana = np.median(senal_digital)
desviacion = np.std(senal_digital)
maximo = np.max(senal_digital)
minimo = np.min(senal_digital)

print("Características de la señal digitalizada:")
print(f"Media: {media}")
print(f"Mediana: {mediana}")
print(f"Desviación estándar: {desviacion}")
print(f"Máximo: {maximo}")
print(f"Mínimo: {minimo}")
```
Donde el resultado fue:
Media: -0.12946811595299854
Mediana: -0.2387616875639651
Desviación estándar: 0.3806889271429698
Máximo: 2.2994220218191566
Mínimo: -0.6639772555790838
## b.	Clasifique la señal según su tipo (determinística/aleatoria, periódica/aparádica, analógica/digital).

La señal biológica analizada se clasifica como aleatoria, debido a que proviene de un proceso fisiológico no completamente predecible; aperiódica, ya que no presenta un patrón repetitivo exacto en el tiempo; y digital, pues aunque su origen es analógico, fue muestreada y procesada en el entorno computacional.

## 4.	Aplique la Transformada de Fourier a la señal y grafique:
La transformada de Fourier convierte la señal del dominio del tiempo al dominio de la frecuencia, mostrando las componentes espectrales que la conforman y su magnitud. Esto permite identificar las frecuencias dominantes, analizar su distribución y detectar patrones o ruidos no evidentes en la forma temporal.

## a.	La transformada de la señal
```python
from scipy.fft import fft, fftfreq


N = len(senal_digital)
fft_senal = fft(senal_digital)
frecuencias = fftfreq(N, 1/fs_digital)

fft_magnitud = np.abs(fft_senal[:N//2])
frecuencias_pos = frecuencias[:N//2]


plt.figure(figsize=(10,4))
plt.plot(frecuencias_pos, fft_magnitud)
plt.title("Transformada de Fourier de la señal")
plt.xlabel("Frecuencia [Hz]")
plt.ylabel("Magnitud")
plt.grid()
plt.show()
```
<img width="640" height="289" alt="transformada" src="https://github.com/user-attachments/assets/3419a98e-bb2f-415b-af0b-5f4d2ad56e9b" />

## b.	Densidad espectral de potencia 
La densidad espectral de potencia (PSD) permite analizar cómo se distribuye la potencia de la señal a lo largo de las diferentes frecuencias. Con ella se puede identificar en qué rangos se concentra la mayor energía espectral, facilitando la interpretación y comparación del contenido frecuencial de la señal.

```python
from scipy.signal import welch

frecs, psd = welch(senal_digital, fs=fs_digital, nperseg=1024)

plt.semilogy(frecs, psd)
plt.title("Densidad espectral de potencia")
plt.xlabel("Frecuencia [Hz]")
plt.ylabel("Potencia [V²/Hz]")
plt.grid()
plt.show()
```
<img width="434" height="338" alt="densidad" src="https://github.com/user-attachments/assets/3c487a52-fa25-4bbf-9da1-b95535834ff3" />



## c. Estadisticos en el dominio de la frecuencia 
Permite describir cómo se distribuye la energía de la señal en las distintas componentes espectrales. A través de la frecuencia media, mediana y la desviación estándar se cuantifica la concentración y dispersión del espectro, mientras que el histograma de frecuencias ofrece una representación visual de dicha distribución.
## i.	Frecuencia media
La frecuencia media corresponde al valor promedio de las componentes espectrales de la señal, ponderado por su energía. Funciona como un “centro de gravedad” del espectro y permite identificar en qué rango de frecuencias se concentra principalmente la información de la señal.

```python
# Frecuencia media
freq_media = np.sum(frecuencias_pos * fft_magnitud) / np.sum(fft_magnitud)
```
## ii.	Frecuencia mediana
La frecuencia mediana indica el valor de frecuencia que divide el espectro en dos partes con igual energía acumulada. Es una medida útil para resumir la distribución espectral de la señal y conocer hasta qué frecuencia se concentra la mitad de su energía total.

```python
# Frecuencia mediana
energia_acumulada = np.cumsum(fft_magnitud)
freq_mediana = frecuencias_pos[np.where(energia_acumulada >= energia_acumulada[-1]/2)[0][0]]
```
## iii.	Desviación estándar
La desviación estándar permite cuantificar la dispersión de la señal respecto a su valor medio. En el dominio del tiempo mide la variabilidad de la amplitud, mientras que en el dominio de la frecuencia indica si la energía está concentrada en torno a ciertas frecuencias o distribuida en un rango más amplio.

```python
# Desviación estándar
freq_std = np.sqrt(np.sum(((frecuencias_pos - freq_media)**2) * fft_magnitud) / np.sum(fft_magnitud))
```
Donde el resultado fue: 
Frecuencia media: 314.9952580356132 Hz
Frecuencia mediana: 61.5 Hz
Desviación estándar: 484.65549430365735 Hz
## iv.	Histograma de frecuencias
El histograma de frecuencias permite representar la distribución de la energía de la señal en distintos rangos del espectro. De esta forma, se identifica de manera visual en qué frecuencias se concentra la mayor parte de la información y se facilita la interpretación del comportamiento espectral de la señal.
```python
plt.hist(frecuencias_pos, bins=50, weights=fft_magnitud, color="skyblue", edgecolor="black")
plt.title("Histograma de frecuencias")
plt.xlabel("Frecuencia [Hz]")
plt.ylabel("Amplitud acumulada")
plt.show()
```
<img width="443" height="335" alt="histograma" src="https://github.com/user-attachments/assets/18dd56ef-0335-4725-9bee-d4a9b193b1a4" />

# DIAGRAMAS DE FLUJO 
## PARTE A
<img width="224" height="374" alt="parteA" src="https://github.com/user-attachments/assets/deac9c7c-cf06-416f-a24e-5e0f7d14a70b" />
## PARTE B
<img width="109" height="152" alt="parteb" src="https://github.com/user-attachments/assets/4afa9e9d-4c55-4e8a-926d-ed09a4e169c2" />
## PARTE C
<img width="113" height="227" alt="partec" src="https://github.com/user-attachments/assets/6f2cc9b2-84fd-4cac-b22b-59a74555b52b" />

