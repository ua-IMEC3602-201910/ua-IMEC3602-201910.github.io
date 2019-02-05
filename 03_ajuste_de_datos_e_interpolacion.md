## Ajuste de Datos e Interpolación

### Interpolación

Uno de los métodos más usados para la interpolación de grupos de datos discretos es el de los Splines Cúbicos. Siguiendo el procedimiento de la Sección 3.3 del libro de Kiusalaas 1.) implemente un algoritmo para interpolar datos discretos mediante Splines Cúbicos. Utilice las funciones de Scipy para la solución de sistemas de ecuaciones utilizadas en la tarea anterior para implementar la función.  

2.) Estudie la función [scipy.interpolate.interp1d](https://docs.scipy.org/doc/scipy/reference/generated/scipy.interpolate.interp1d.html#scipy.interpolate.interp1d) de Scipy. Esta función con la opción ```kind='cubic'``` realiza una interpolación como la que usted implementó. Verifique que los resultados son similares a los suyos para algunas funciones, por ejemplo, una función sinusoidal y una exponencial como se muestra en el ejemplo al final de la documentación de [scipy.interpolate.interp1d](https://docs.scipy.org/doc/scipy/reference/generated/scipy.interpolate.interp1d.html#scipy.interpolate.interp1d). Utilice la metodología disponible en [esta página](https://stackoverflow.com/questions/14261474/how-do-i-write-a-function-that-returns-another-function) para los llamados a su función sean iguales a los de [scipy.interpolate.interp1d](https://docs.scipy.org/doc/scipy/reference/generated/scipy.interpolate.interp1d.html#scipy.interpolate.interp1d), es decir, que la interpolación devuelva una función que puede aproximar los valores deseados de la función.  

3.) Utilizando la función [scipy.interpolate.interp1d](https://docs.scipy.org/doc/scipy/reference/generated/scipy.interpolate.interp1d.html#scipy.interpolate.interp1d) resuelva los ejercicios 3.3.12 y 3.3.17.

### Regresión por mínimos cuadrados

La regresión por mínimos cuadrados es importante en muchas aplicaciones en ingeniería. Por ejemplo, permite encontrar parámetros adecuados para modelar sistemas físicos. Estudie la sección 3.4 del libro de Kiusalaas. 1.) Implemente la función ```polyFit``` como se muestra en la sección. En donde sea posible, trate de reemplazar bucles ```for``` por expresiones vectorizadas.  
2.) Estudie la función [numpy.polynomial.polynomial.polyfit](https://docs.scipy.org/doc/numpy-1.15.0/reference/generated/numpy.polynomial.polynomial.polyfit.html#numpy.polynomial.polynomial.polyfit). Compare los resultados de su función con los de [numpy.polynomial.polynomial.polyfit](https://docs.scipy.org/doc/numpy-1.15.0/reference/generated/numpy.polynomial.polynomial.polyfit.html#numpy.polynomial.polynomial.polyfit) para resolver, por ejemplo, los ejemplos mostrados al final de la documentación.  

3. Utilizando la función [numpy.polynomial.polynomial.polyfit](https://docs.scipy.org/doc/numpy-1.15.0/reference/generated/numpy.polynomial.polynomial.polyfit.html#numpy.polynomial.polynomial.polyfit) resuelva los ejercicios 3.4.9 y 3.4.14.  


### Transformada de Fourier

