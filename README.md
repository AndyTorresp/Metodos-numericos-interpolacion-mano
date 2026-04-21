# Metodos-numericos-interpolacion-mano
Comparativa entre inerpolacion polinomial global y splines cubicos para la reconstruccion de un contorno
# Reconstrucción del Contorno de una Mano

Este proyecto realiza una comparativa de metodos de interpolacion numerica para reconstruir la silueta de una mano a partir de un conjunto de puntos (xi, yi)

## Analisis de Resultados 

# 1. ¿Por que fallan los metodos de Lagrange, Newton y Matricial?
En la grafica de la izquierda (Polinomio Global) se observa que la curva se dispara y no sigue los puntos. Esto se debe a:
* *Fénomeno de Runge:* Al usar un número alto de puntos (n > 20), el polinomio global de grado alto genera oscilaciones salvajes en los extremos
* *Mal condicionamiento:* Los metodos globales (como la matriz de Vandermonde) son numericamente inestables para sistemas grandes

# 2. ¿Por que los Splines Cúbicos funcionan bien?
En la grafica de la derecha, la silueta es suave y precisa debido a:
* *Interpolación Segmentaria:* En lugar de un solo polinomio, se utilizan polinomios de grado 3 entre cada par de puntos
* *Continuidad:* Garantiza suavidad en la curva y estabilidad numerica, evitando las oscilaciones del metodo global

## Ejecución en MATLAB
El script `interpolacion_mano.m` genera ambas graficas para contrastar la estabilidad de los metodos
