# Discretización de Controladores
En esta clase, se va a analizar cómo convertir controladores analógicos en digitales, lo cual es fundamental para diseñar sistemas de control modernos. El objetivo es encontrar una forma de igualar o una equivalencia entre el espacio de Laplace y el espacio Z. Se explorarán varios métodos para lograr esta "discretización", cada uno con sus ventajas y desventajas, donde se pueden comparar y elegir el mejor método a utilizar.
## 1. Discretización de señales analógicas
Los diversos métodos de discretización buscan aproximar, a través de sistemas discretos, ciertas características dinámicas (como la respuesta en frecuencia o en el tiempo) de los sistemas analógicos.Dado que no existe un método "universalmente mejor", la selección de un enfoque puede basarse en la precisión y la facilidad de cálculo.
### 1.1. Invarianza al Impulso
Invarianza al impulso: Método de discretización donde se usa la respuesta al impulso de un sistema continuo $C(s)$ para obtener su equivalente discreto $C(z)$.

* Se utiliza la transformada de Laplace del impulso, donde $e(t)$ = $δ(t)$ y su transformada es $e(s)=1$
* Para un tiempo de muestreo suficientemente pequeño, la relación se obtiene como:
  
$$C(z) = T Z\({\mathcal{L}^{-1}\{C(s)\}\}_{t = kT})$$

### 1.2. Invarianza al Paso
Invarianza al paso: Técnica donde se busca obtener el equivalente discreto de un sistema continuo mediante la comparación de respuestas al escalón.
* Se parte de que la transformada Z de una función paso es:
  
$$Z(e^{t})=\frac{z}{z-1}$$

* Aplicando fracciones parciales y simplificaciones, se puede llegar a la función discreta correspondiente.

### 1.3. Método de Euler
Método de Euler hacia adelante: Aproximación discreta de la derivada utilizando la diferencia hacia adelante.
* La derivada discreta se define como:

$$\frac{dx(t)}{dt}\approx \frac{x(k+1)-x(k)}{T}$$

### 1.4. Método Trapezoidal (Tustin)
Método trapezoidal: Aproximación que proporciona una mejor precisión que Euler, utilizando una interpolación lineal para la integración numérica.
* La relación se da como:

$$s=\frac{2}{T}\frac{z-1}{z+1}$$



## 2. Teorema de Muestreo de Nyquist
Teorema de muestreo de Nyquist: Establece que la frecuencia de muestreo $f_{s}$ debe ser al menos el doble de la frecuencia máxima presente en la señal (frecuencia de Nyquist) para evitar aliasing.

>🔑*Aliasing:* es el efecto que causa que señales continuas distintas se tornen indistinguibles cuando se muestrean digitalmente.

Para evitar que la señal sufra de esto se sube la frecuencia de muestreo o agregando un filtro a la señal.
* La condición se expresa como:
  
$$f_{s}>2f_{N}$$
​

  debe ser al menos el doble de la frecuencia máxima presente en la señal (frecuencia de Nyquist) para evitar aliasing.
Utilice el símbolo '>' para crear bloques de texto. En la presente plantilla estas cajas están reservadas para resaltar las definiciones, las cuales deben ser breves, y la palabra o frase que se está definiendo debe estar en letra itálica. El inicio del bloque de texto debe realizarse con el emoji 🔑 .
>🔑 *Definición:* descripción precisa y clara del significado de una palabra, término, concepto o fenómeno. Es una explicación que establece los límites y el alcance de aquello que se está definiendo, aclarando su naturaleza, características esenciales y, en algunos casos, su relación con otros conceptos.

## 3. Subsecciones
Las subsecciones pueden utilizarse para sub dividir ciertos temas que se tienen en clases, por ejemplo si se está trabajandolos conversores D/A, puede ser necesario subdividir este en circuito de resistencias ponderadas y circuito de escalera R2R. 
### 3.1. Título de subsecciones
Para la creación de estas subsecciones debe utilizar un tamaño de letra más pequeño, por lo tanto utilice la etiqueta '###' 
### 3.2. Numeración de subsecciones
Siga la numeración de la sección seguida de un punto y luego el número de la subsección.

## 4. Ejemplos
Si en algún caso pretende dar un ejemplo explicativo ya sea a través de texto o através de ecuaciones matemáticos, utilizar la palabra 'Ejemplo' seguido de una numeración consecutiva dentro de la clase. Utilice el emoji 💡 antecediendo la palabra.

## 5. Ecuaciones
Para la edición de ecuaciones debe utilizar la etiqueta '$$' al comienzo y final de la ecuación para que la ecuación quede centrada ocupando una línea. Si se quiere que la ecuación quede integrada en el texto debe utilizar la etiqueta '$' al comienzo y final de la ecuación. Las ecuaciones pueden ser editadas utilizando el código LATEX, en el siguiente enlace encuentran un editor de ecuaciones que les genera el código. http://www.alciro.org/tools/matematicas/editor-ecuaciones.jsp . Sin embargo hay muchas otras herramientas que pueden utilizar para esto.

💡**Ejemplo 1:** si se va a representar la ecuación de la ley de Ohm se puede mostrar así $R=\frac{V}{I}$ o también,

$$R=\frac{V}{I}$$

## 6. Figuras
Todas las figuras que incluya deben ser generadas por ustedes, **no utilizar las figuras de las presentaciones**. Para incluir figuras puede seguir los siguientes pasos:
* Primero escribimos ![]().
* Después escribimos, dentro de los corchetes, el texto alternativo. Este es opcional y solo entra en acción cuando no se puede cargar la imagen correctamente.
* Después escribimos, dentro de los paréntesis, la ubicación del archivo (ya sea una url o una ubicación dentro de algun folder local). Se recomienda poner las imágenes en una carpeta que se llame imágenes dentro del repositorio github para que no tengan problemas al cargar las imágenes.

💡**Ejemplo 2:**

![Figura de prueba](images/plantilla/Captura2.PNG)

Figura 1. Figura de prueba

Incluya la respectiva etiqueta a modo de descripción de la figura y mantenga numeración consecutiva para todas las figuras de la clase.

## 7. Tablas
En caso de necesitar la inclusión de tablas para organizar información se recomienda el uso de la herramienta del siguiente enlace https://www.tablesgenerator.com/markdown_tables , la cual permite organizar la información dentro de la tabla y genera el código markdown automáticamente:

💡**Ejemplo 3:** 

| **Resultado** | **x = número de intentos hasta primer éxito** |
|---------------|-----------------------------------------------|
|       S       |                       1                       |
|       FS      |                       2                       |
|      FFS      |                       3                       |
|      ...      |                      ...                      |
|    FFFFFFS    |                       7                       |
|      ...      |                      ...                      |

Tabla 1. Tabla de ejemplo

Cada tabla debe llevar la etiqueta que describa su contenido y numeración consecutiva para todas las tablas

## 8. Código
Teniendo en cuenta que el curso requiere del desarrollo de código matlab, c, c++ u otro. Si requiere incluir pequeños segmentos de código en los apuntes hágalos de la siguiente manera:

💡**Ejemplo 4:**
```
var sumar2 = function(numero) {
  return numero + 2;
}
```

## 9. Ejercicios
Deben agregar 2 ejercicios con su respectiva solución, referentes a los temas tratados en cada una de las clases. Para agregar estos, utilice la etiqueta #, es decir como un nuevo título dentro de la clase con la palabra 'Ejercicios'. Cada uno de los ejercicios debe estar numerado y con su respectiva solución inmediatamente despues del enunciado. Antes del subtitulo de cada ejercicio incluya el emoji 📚

## 10. Conclusiones
Se exploraron los principales métodos de discretización de controladores, resaltando tanto sus aplicaciones prácticas como sus limitaciones. La discretización es esencial en el diseño de sistemas de control digital, y la elección del método adecuado depende de factores como la exactitud requerida y el costo computacional asociado.



## 11. Referencias
1.JDEIJ
2.
