# Introducción

Este curso lo va a familiarizar con el uso adecuado de las herramientas computacionales modernas para la solución de problemas en ciencias e ingeniería. El curso se basa en el uso de Github y Python 

## Git y Github

[Git and GitHub learning resources](https://help.github.com/articles/git-and-github-learning-resources/)  
[Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

## Python y Anaconda

* [Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/)  

### Librerías en Python

Python es un lenguaje de programación de alto nivel ampliamente utilizado en el ámbito de la programación científica, modelamiento matemático, análisis de datos y visualización. El ecosistema de Python cuenta con muchos paquetes y librerías que proveen la capacidad de hacer operaciones sobre arreglos multidimensionales, operaciones matemáticas de alto nivel, graficación, manejo de archivos y mucho más. Para expandir las capacidades del lenguaje uno debe importar librerías en nuestros programas de Python.  

Para importar librerías en python se utiliza el comando `import` como se muestra en el siguiente segmento de código.  

```python
import numpy as np
```  

Arriba se utiliza `import` para cargar la librería `numpy` con el alias `np`. Para usar alguna función perteneciente a esa librería, debemos llamarla escribiendo el nombre de la función después del nombre de la librería y un punto así:  

```python
arreglox = np.linspace(0, 5, 10)
```  

En el código anterior se utiliza la función `linspace` para crear un arreglo con 10 números equidistantes entre 0 y 10 y asignarlo a la variable `arreglox`. Puede verificar que `arreglox` es efectivamente una variable de tipo `numpy.ndarray` utilizando el comando `type(arreglox)`. Defina varios tipos de variables y verifique su tipo utilizando la función `type`.  

### Espacios en blanco e indentación

Python utiliza indentación y espacios  para agrupar estructuras de programación. Por ejemplo, en el lenguage de programación C (similarmente en Java y, de hecho, en la mayoría de lenguages de programación) un bucle de repetición se esrbiría así:  

```c
for (i=0, i<5, i++){
  printf('Hola! \n')
}
```

En Matlab el mismo bucle se escribiría así:   

```matlab
for i=1:5
  fprintf('Hola! %i \n', i)
end
```  

En los dos ejemplos anteriores, noten que el bucle está delimitado por los corchetes '{}' en el caso de C o por el conjunto ```for - end``` en el caso de Matlab. También noten que la indentación al interior de los bucles es meramente decorativa y no cumple ningún propósito funcional. En Python los bloques de código están definidos por las indentaciones, esta es una de las características más peculiares del lenguaje. El bucle anterior en Python se vería así:  

```python
for i in range(5):
  print('Hola! {0:d}'.format(i))
```  

En el bloque de código anterior, la indentación de la línea que contiene la función ```print``` es lo que define que está dentro del bucle ```for```. Para aclarar esto, miremos un ejemplo un poco más complejo, un bucle dentro del otro:  

```python
for i in range(3):
    for j in range(3):
        print(i, j)
    print("Esta línea está dentro del bucle i, más no el bucle j")
```  

## Estructuras de datos para programación científica: arreglos multidimensionales (ndarray)

Como mencionamos en la introducción de la clase, los arreglos multidimensionales son las estructuras de datos básicas necesarias en muchas aplicaciones en programación científica y analisis de datos. La librería Numpy proporciona esta estructura de datos. Arriba habíamos declarado el arreglo ```arreglox``` que contenía 10 número entre 0 y 5. Para acceder a los valores de los elementos del arreglo se utilizan índices. Acá surge otra diferencia fundamental entre Python y Matlab, Python utiliza índices con base cero mientras Matlab utiliza índices con base uno. Es decir, para acceder al primer elemento del arreglo en Python utilizo ```arreglox[0]``` mientras en Matlab usaría ```arreglox(1)```. Es muy importante mantener esto en mente.  

Una operación que se hace con frecuencia en computación científica es la extracción de porciones de un arreglo. Por ejemplo, si quiere extraer los primeros tres elementos del arreglo ```arreglox```, se puede hacer mediante la declaración ```arreglox[0:3]```.  

Otro aspecto fundamental a tener en cuenta cuando programamos en Python es la forma en que se asignan los arreglos a otras variables. Considere por ejemplo el siguiente bloque de código:  

```python
a = np.linspace(1, 5, 5)
b = a
b[2] = 17
print(a)
```

El resultado de ejecutar el código anterior es [ 1.  2. 17.  4.  5.], lo cual no es del todo esperado. La asignación ```b = a```, asigna a ```b``` el mismo espacio en memoria que ```a``` y cualquier modificación a alguno de los dos, modificará el otro. Para hacer una copia del arreglo, como se haría en Matlab se debe usar el método ```copy``` así:  

```python
a = np.linspace(1, 5, 5)
b = a.copy()
b[2] = 17
print(a)
```

### Operaciones vectoriales

Creemos un nuevo arreglo ```x``` con valores entre 0 y 2\*pi.  

```python
x = np.linspace(0, 2*np.pi, 100)
```

El arreglo x contiene 100 valores equidistantes entre 0 y 2\*pi. Noten además que la librería Numpy también proporciona la variable pi. No es dificil imaginar que, en muchas aplicaciones en ciencias e ingeniería, uno puede necesitar aplicar la misma operación a todos y cada uno de los elementos de un arreglo. Por ejemplo, para graficar la función seno(x) se debe calcular el seno de todos y cada uno de los elementos del arreglo x. Una posibilidad es a través de un bucle de la siguiente forma:  

```python
senx_list = []
for x_ele in x:
  senx_list.append(np.sin(x_ele))
senx = np.array(senx_list)
```

No obstante el aterior código construye un arreglo con los valores correctos (y nos da ejemplos de algunas herramientas de programación en Python interesante y útiles) no es la forma más eficiente y *Pythonica* de hacer ese procedimiento. La forma más efectiva de construir el vector es uitlizar la función de manera vectorial así:

```python
senx = np.sin(x)
```

Para concluir esta discusión introductoria a la programación científica en Python, vale la pena introducir la forma de graficar en Python. Para los que tienen experiencia con Matlab, las funciones son muy similares. Supongamos que queremos graficar la función seno(x) que calculamos anteriormente. Primero debemos importar la librería que nos provee las funciones de graficación:  

```python
import matplotlib.pyplot as plt
```

El siguiente bloque de código construye una gráfica de la función seno(x) y la graba en un archivo de imágenes.

```python
plt.plot(x,senx)
plt.xlabel('$x$')
plt.ylabel('$\sin{(x)}$')
plt.savefig('senox.jpg')
plt.show()
```  

A continuación algunos enlaces a recursos para complementar la información acá presentada.  

* [Python For Engineers](http://pythonforengineers.com/python-for-scientists-and-engineers/)  
* [Python for Computational Science and Engineering](https://www.southampton.ac.uk/~fangohr/training/python/pdfs/Python-for-Computational-Science-and-Engineering.pdf)  
* [Numpy Tutorial](https://www.python-course.eu/numpy.php)  
* [From Python to Numpy](http://www.labri.fr/perso/nrougier/from-python-to-numpy/)  

El siguiente enlace en particular muestra las diferencias/similitudes entre Numpy y Matlab en el manejo de arreglos.  

* [NumPy for Matlab users](https://docs.scipy.org/doc/numpy-1.15.0/user/numpy-for-matlab-users.html)  

* [Intro to Data Structures in Pandas](https://pandas.pydata.org/pandas-docs/stable/dsintro.html)  

* [Numerical Tours in Python](http://www.numerical-tours.com/python/)  
* [Scipy Lecture Notes](http://www.scipy-lectures.org/)  
* [An introduction to Numpy and Scipy](https://engineering.ucsb.edu/~shell/che210d/numpy.pdf)  

## Lectura y escritura de datos en archivos de texto