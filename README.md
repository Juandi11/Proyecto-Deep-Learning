# Análisis de estabilidad de voltaje

Estos scrips tiene como función determinar si un sistema eléctrico es estabale por tensión o no, mediante el uso de un algoritmo de red neuronal tipo LSTM

## Estabilidad de tensión: 
Es la capacidad de un sistema eléctrico para mantener voltajes aceptables en todas las barras (puntos de interconexión) bajo condiciones normales y tras perturbaciones. Un sistema es estable en tensión si, tras una perturbación, los voltajes de las barras se recuperan a valores normales o se mantienen dentro de un rango aceptable sin una caída continua de voltaje.

## Sobre los datos
Los datos provienen de una simulación en el software DigSilent del ieee new england 39 bars test, en él se simularon 10000 perturbaciones. En el momento de la perturbación se miden las tensiones en las barras durante un tiempo de 10 segundos a una frecuencia de muestreo de 833 ms obteniendo 39 series con 1203 observaciones. Adicionamente se tiene un archivo con las etiquetas para cada serie indicando si es estable (0) o inestable (1). Para obtener esta etiqueta se usó el indice Liapunov.
Los datos pueden descargarse [aquí](https://github.com/Juandi11/Series_de_tiempo)


## Justificación
Para los operadores de red es importante simular la mayor cantidad de escenarios posibles, los cuales debido a la variedad de perturbaciones que existen pueden llevar muchas simulaciones y aumentar a medida que aumentan las barras en el sistema (nodos de conexión).



Para poder dedterminar la estabilidad del sistema se usa el indice lyapunov, sin embargo este requiere una ventana de tiempo de minimo 10s para poder hacer la clasificación (estable o inestable).

Para poder reducir el costo computacional de estas simulaciones bajar ventana de tiempo de simulación sería un avance, por tanto mediante la metodología implementada en los escrips de este repositorio se puede realizar esta clasificación (estable o inestable) usando una ventana de tiempo menor

## Video explicativo
[Ver video en YouTube](https://www.youtube.com/watch?v=kduSaWT7oGQ)
