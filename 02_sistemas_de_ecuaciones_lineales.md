## Sistemas de Ecuaciones Lineales

Las operaciones matriciales son fundamentales en la mayoría de los métodos usados en ingeniería y su dominio es requisito fundamental en la computación numérica. No es exagerado decir que resolver la gran mayoría de problemas en ciencia e ingeniería se reduce, de alguna forma u otra, a encontrar la solución de sistemas lineales de ecuaciones usando métodos numéricos. La solución de un sistema de ecuaciones lineales busca encontrar un vector solución **x** que al multiplicarse por una matriz **A** de como resultado un vector conocido **b**, **Ax** = **b**. Las cantidades **A**, **b** y **x** pueden tener una diversidad de significados físicos dependiendo del contexto matemático o físico del problema.  

[Numpy Linear Algebra](https://docs.scipy.org/doc/numpy/reference/routines.linalg.html)  

Al finalizar este módulo usted se ha familiarizado con los métodos numéricos para la solución de sistemas de ecuaciones, en particular, debe entender el costo computacional de cada una de las etapas de la solución y debe haberse familiarizado con el uso de funciones de la librería Scipy.linalg.  

Un tema importante que surgió en nuestra discusión de este módulo fue si los argumentos a las funciones en Python se pasan por valor o por referencia. Resulta que la respuesta es más complicada que lo que hablamos en clase. Para los interesados, la información más completa (pero compacta) que encontré está en [ésta página](https://stackoverflow.com/questions/986006/how-do-i-pass-a-variable-by-reference).  