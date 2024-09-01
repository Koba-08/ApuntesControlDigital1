# Estabilidad en Sistemas Discretos
La estabilidad en sistemas discretos es un aspecto clave en el área del control digital. Un sistema se considera estable cuando su salida se mantiene dentro de ciertos límites al aplicarse una entrada limitada. Existen diferentes enfoques para analizar la estabilidad, como la estabilidad absoluta, la estabilidad asintótica y la estabilidad BIBO. Además, se exploran métodos para evaluar la estabilidad, entre ellos el criterio de Jury, que es especialmente relevante para sistemas discretos.
## 1. Estabilidad Absoluta
>🔑 Definición: La estabilidad absoluta es la capacidad de un sistema para mantener su salida dentro de límites establecidos cuando se le aplica una entrada limitada.

En sistemas discretos, la estabilidad absoluta se determina observando la respuesta del sistema ante una entrada escalón. Si la salida refleja las mismas características que la entrada, el sistema se considera absolutamente estable.

## 2. Comparación entre el Espacio LaPlace y el Espacio Z
El espacio LaPlace es un dominio matemático usado para el análisis de sistemas continuos, mientras que el espacio Z se emplea para el análisis de sistemas discretos.
### 2.1. Fronteras de Estabilidad
En el espacio LaPlace, la estabilidad se delimita por el eje vertical, mientras que en el espacio Z, la ubicación de los polos dentro de un círculo unitario determina la estabilidad.

💡Ejemplo 1: Análisis de la estabilidad de un sistema en el espacio Z.
Para el sistema dado con la función de transferencia 

$$G(z)=\frac{4}{z^{3}-7.8z^{2}+13.4z+3}$$

la solución del polinomio característico revela polos en $z=5,z=3 y z=0.2$  ,lo que indica que el sistema es inestable, ya que dos de los polos están fuera del círculo unitario.

## 3. Estabilidad Asintótica
>🔑 Definición: La estabilidad asintótica describe a un sistema cuya respuesta tiende a cero con el paso del tiempo, independientemente de las condiciones iniciales.

Para que un sistema sea asintóticamente estable, su respuesta a cualquier entrada inicial debe disminuir a cero en estado estable.

## 4. Estabilidad BIBO
Un sistema es BIBO estable si su salida se mantiene dentro de ciertos límites cuando se aplica una entrada acotada.

## 5. Test de Jury
El criterio de Jury es un método utilizado para determinar la estabilidad de un sistema discreto mediante el análisis del polinomio característico de su función de transferencia, sabiendo que el polinomio de una función de transferencia en z tiene esta forma:

$$D(z)=a_{0}Z^{n}+a_{1}Z^{n-1}+...+a_{n-1}Z+a_{n}$$

* Es imprescindible emplear el criterio de Jury para determinar la estabilidad de un sistema, para esto se deben cumplir una serie de condiciones las cuales son:
* $a_{0}> 0$
* $|a_{n}| < a_{0}$
* $P(z)|_{z=1} >0$
* $P(z)|_{z=-1} >0 para n par$ y
* $P(z)|_{z=-1} <0 para n impar$
* Construir el arreglo de Jury
* Cumplir con las condiciones de estabilidad del arreglo de Jury


## 6. Conclusiones
En esta lección, hemos explorado la importancia de la estabilidad en sistemas discretos para asegurar un comportamiento predecible y controlado. A través de ejemplos prácticos y la aplicación del criterio de Jury, se ha demostrado cómo evaluar la estabilidad de un sistema en el dominio Z.

## 7. Referencias
1.Visioli, A. Digital Control Engineering. 2nd Edition. Elsevier. 2013.
