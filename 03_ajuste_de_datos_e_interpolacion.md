## Ajuste de Datos e Interpolación

### Interpolación

Uno de los métodos más usados para la interpolación de grupos de datos discretos es el de los Splines Cúbicos. Siguiendo el procedimiento de la Sección 3.3 del libro de Kiusalaas 1.) implemente un algoritmo para interpolar datos discretos mediante Splines Cúbicos. Utilice las funciones de Scipy para la solución de sistemas de ecuaciones utilizadas en la tarea anterior para implementar la función.  

2.) Estudie la función [scipy.interpolate.interp1d](https://docs.scipy.org/doc/scipy/reference/generated/scipy.interpolate.interp1d.html#scipy.interpolate.interp1d) de Scipy. Esta función con la opción `kind='cubic'` realiza una interpolación como la que usted implementó. Verifique que los resultados son similares a los suyos para algunas funciones, por ejemplo, una función sinusoidal y una exponencial como se muestra en el ejemplo al final de la documentación de [scipy.interpolate.interp1d](https://docs.scipy.org/doc/scipy/reference/generated/scipy.interpolate.interp1d.html#scipy.interpolate.interp1d). Utilice la metodología disponible en [esta página](https://stackoverflow.com/questions/14261474/how-do-i-write-a-function-that-returns-another-function) para los llamados a su función sean iguales a los de [scipy.interpolate.interp1d](https://docs.scipy.org/doc/scipy/reference/generated/scipy.interpolate.interp1d.html#scipy.interpolate.interp1d), es decir, que la interpolación devuelva una función que puede aproximar los valores deseados de la función.  

3.) Utilizando la función [scipy.interpolate.interp1d](https://docs.scipy.org/doc/scipy/reference/generated/scipy.interpolate.interp1d.html#scipy.interpolate.interp1d) resuelva los ejercicios 3.3.12 y 3.3.17.

#### Vectorización de Funciones

Para los que han avanzado en el desarrollo de la solución, es posible que se hayan encontrado con un problema a la hora de correr la función de interpolación con un vector como entrada. El error puede estar relacionado con la inconsistencia en comparar un arreglo con un número flotante. Este error se debe a que algunas de las funciones que ustedes están definiendo con base en el libro, son funciones escalares, es decir, que reciben un escalar y devuelven un escalar. Por ejemplo, noten que la función `evalSpline` recibe un escalar y devuelve un escalar; la lógica interna de la función depende de que el argumento de entrada sea un escalar.  

Este error se puede solventar de varias maneras. Por ejemplo, ustedes pueden solo llamar la función de interpolación con escalares (por ejemplo, usando `for` para recorrer el arreglo con todos los valores que quieren interpolar).  

Sin embargo, la solución más *pro* es *vectorizar* la función de interpolación. Esto se puede lograr mediante la función [numpy.vectorize](https://docs.scipy.org/doc/numpy/reference/generated/numpy.vectorize.html) la cual recibe una función escalar y devuelve una función vectorizada. La función que deben vectorizar es la función que están devolviendo para el cálculo de la interpolación.  

#### [scipy.linalg.solve_banded](https://docs.scipy.org/doc/scipy/reference/generated/scipy.linalg.solve_banded.html)

Cómo hemos mencionado varias veces en clase, uno de los objetivos de estos talleres es desarrollar experiencia mediante la adaptación de los algoritmos del libro a 1.) Python 3 y 2.) para utilizar las funciones disponibles en Scipy en lugar de las funciones del libro.  

En este ejercicio particularmente, Kiusalaas utilizar las funciones propias `LUdecomp3` y `LUsolve3` para solucionar un sistema de ecuaciones tridiagonal. Lo que les he pedido es que reemplacen estas funciones por la función [scipy.linalg.solve_banded](https://docs.scipy.org/doc/scipy/reference/generated/scipy.linalg.solve_banded.html) disponible en *Scipy.linalg*. Esta función es genérica para resolver sistemas de ecuaciones bandeados, es decir, que tiene elementos diagonales diferentes de cero con algún *ancho de banda*. Es importante que revisen bien la documentación de la función y adapten el código para funcionar bien con esta función y verifiquen su funcionamiento.  

### Regresión por mínimos cuadrados

La regresión por mínimos cuadrados es importante en muchas aplicaciones en ingeniería. Por ejemplo, permite encontrar parámetros adecuados para modelar sistemas físicos. Estudie la sección 3.4 del libro de Kiusalaas. 1.) Implemente la función `polyFit` como se muestra en la sección. En donde sea posible, trate de reemplazar bucles `for` por expresiones vectorizadas.  
2.) Estudie la función [numpy.polynomial.polynomial.polyfit](https://docs.scipy.org/doc/numpy-1.15.0/reference/generated/numpy.polynomial.polynomial.polyfit.html#numpy.polynomial.polynomial.polyfit). Compare los resultados de su función con los de [numpy.polynomial.polynomial.polyfit](https://docs.scipy.org/doc/numpy-1.15.0/reference/generated/numpy.polynomial.polynomial.polyfit.html#numpy.polynomial.polynomial.polyfit) para resolver, por ejemplo, los ejemplos mostrados al final de la documentación.  

3.) Utilizando la función [numpy.polynomial.polynomial.polyfit](https://docs.scipy.org/doc/numpy-1.15.0/reference/generated/numpy.polynomial.polynomial.polyfit.html#numpy.polynomial.polynomial.polyfit) resuelva los ejercicios 3.4.9 y 3.4.14.  


### Transformada de Fourier

