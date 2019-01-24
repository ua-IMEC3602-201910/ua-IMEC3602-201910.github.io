# Introducción

Este curso lo va a familiarizar con el uso adecuado de las herramientas computacionales modernas para la solución de problemas en ciencias e ingeniería. El curso se basa en el uso de Github y Python 

## Git y Github

[Git and GitHub learning resources](https://help.github.com/articles/git-and-github-learning-resources/)  
[Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

## Python y Anaconda

* [Python For Engineers](http://pythonforengineers.com/python-for-scientists-and-engineers/)  
* [Python for Computational Science and Engineering](https://www.southampton.ac.uk/~fangohr/training/python/pdfs/Python-for-Computational-Science-and-Engineering.pdf)  
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

## Estructuras de datos para programación científica: Numpy, Scipy y Pandas

* [Numpy Tutorial](https://www.python-course.eu/numpy.php)  
* [An introduction to Numpy and Scipy](https://engineering.ucsb.edu/~shell/che210d/numpy.pdf)  
* [Numerical Tours in Python](http://www.numerical-tours.com/python/)  
* [NumPy for Matlab users](https://docs.scipy.org/doc/numpy-1.15.0/user/numpy-for-matlab-users.html)  
* [From Python to Numpy](http://www.labri.fr/perso/nrougier/from-python-to-numpy/)  
* [Scipy Lecture Notes](http://www.scipy-lectures.org/)  
* [Intro to Data Structures in Pandas](https://pandas.pydata.org/pandas-docs/stable/dsintro.html)  

## Lectura y escritura de datos en archivos de texto