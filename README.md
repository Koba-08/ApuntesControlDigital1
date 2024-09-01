# Discretización de Controladores
En esta clase, se va a analizar cómo convertir controladores analógicos en digitales, lo cual es fundamental para diseñar sistemas de control modernos. El objetivo es encontrar una forma de igualar o una equivalencia entre el espacio de Laplace y el espacio Z. Se explorarán varios métodos para lograr esta "discretización", cada uno con sus ventajas y desventajas, donde se pueden comparar y elegir el mejor método a utilizar.
## 1. Discretización de señales analógicas
Los diversos métodos de discretización buscan aproximar, a través de sistemas discretos, ciertas características dinámicas (como la respuesta en frecuencia o en el tiempo) de los sistemas analógicos.Dado que no existe un método "universalmente mejor", la selección de un enfoque puede basarse en la precisión y la facilidad de cálculo.
### 1.1. Invarianza al Impulso
Invarianza al impulso: Método de discretización donde se usa la respuesta al impulso de un sistema continuo $C(s)$ para obtener su equivalente discreto $C(z)$.

* Se utiliza la transformada de Laplace del impulso, donde $e(t)$ = $δ(t)$ y su transformada es $e(s)=1$
* Para un tiempo de muestreo suficientemente pequeño, la relación se obtiene como:
  
$$C(z) = T Z\left\{L^{-1}\left\{C(s)\right\}_{t=KT}\right\}$$

### 1.2. Invarianza al Paso
Invarianza al paso: Técnica donde se busca obtener el equivalente discreto de un sistema continuo mediante la comparación de respuestas al escalón.
* Se parte de que la transformada Z de una función paso es:
  
$$Z(e^{t})=\frac{z}{z-1}$$

* Aplicando fracciones parciales y simplificaciones, se puede llegar a la función discreta correspondiente.

### 1.3. Método de Euler
#### 1.3.1.Método de Euler hacia adelante 
Aproximación discreta de la derivada utilizando la diferencia hacia adelante.
* La derivada discreta se define como:

$$\frac{dx(t)}{dt}\approx \frac{x(k+1)-x(k)}{T}$$

Y al calcular y aplicar la transformada Z se obtiene: $s\approx \frac{z-1}{T}$

Con la cual podemos ver que un controlador en tiempo continuo no necesariamente es estable en tiempo discreto

#### 1.3.2.Método de Euler hacia atras 
Es la aproximación discreta de la derivada utilizando la diferencia hacia atras.
* La derivada discreta se define como:

$$\frac{dx(t)}{dt}\approx \frac{x(k)-x(k-1)}{T}$$ 

Y al calcular y aplicar la transformada Z se obtiene: $s\approx \frac{1-z^{-1}}{T}=\frac{z-1}{Tz}$

### 1.4. Método Trapezoidal (Tustin)
Método trapezoidal: Aproximación que proporciona una mejor precisión que Euler, utilizando una interpolación lineal para la integración numérica.
* La relación se da como:

$$s=\frac{2}{T}\frac{z-1}{z+1}$$



## 2. Teorema de Muestreo de Nyquist
Teorema de muestreo de Nyquist: Establece que la frecuencia de muestreo $f_{s}$ debe ser al menos el doble de la frecuencia máxima presente en la señal (frecuencia de Nyquist) para evitar aliasing.

>🔑*Aliasing:* es el efecto que causa que señales continuas distintas se tornen indistinguibles cuando se muestrean digitalmente.

Para evitar que la señal sufra de esto se sube la frecuencia de muestreo o agregando un filtro a la señal.
* La condición se expresa como:   $f_{s}>2f_{N}$
   

​

## 10. Conclusiones
Se exploraron los principales métodos de discretización de controladores, resaltando tanto sus aplicaciones prácticas como sus limitaciones. La discretización es esencial en el diseño de sistemas de control digital, y la elección del método adecuado depende de factores como la exactitud requerida y el costo computacional asociado.



## 11. Referencias
1.https://upcommons.upc.edu/bitstream/handle/2117/188948/sec_tema_4_control_digital_1314a_ocw-5203.pdf
2.http://lcr.uns.edu.ar/fvc/NotasDeAplicacion/FVC-RodrigoBarco.pdf
