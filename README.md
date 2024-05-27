# Preparación de datos para ML
## Parte 1 Fundamentos
Descubriremos la importancia de preparar los datos, técnicas de preparacion y hablaremos de las mejores practicas para evitar perdida de datos.

En este notebook aprenderemos:
- Cada proyecto de modelado en machine learning es diferente, pero hay pasos comunes que se pueden realizar en cada proyecto.
- La preparacion de los datos envuelve exponer lo desconocido debajo de una estructura de un problema de machine learning.
- Los pasos antes y después en la preparación de los datos en un proyecto puede informar que métodos de preparación de datos aplicar, o por lo menos explorar.

### Proceso aplicado de Machine Learining
Este proceso conciste en una serie de pasos. Los pasos son los mismos pero pueden cambiar de nombre en otra definición de este concepto. Los pasos los escribiremos secuenciales pero podremos saltar de atras hacia adelante entre estos pasos en un projecto dado. Este proceso se divide en cuatro pasos de alto nivel:
- **Definir el problema**: este paso se considera para aprender del proyecto en manos y las tareas de preparación. Por ejemplo, es regresión, calsificación o agrupamiento o de algun otro tipo?. Esto envuelve la recoleccion de datos que se cree sera util para una predicción y definir la forma en que esta tomará. También envuelve hablar con los accionistas o personas expertas en el dominio de esta data. Este paso también involucra hacer un resumen estadistico y visualización de los datos
- **Preparar los datos**: Este paso se refiere a transformar los datos crudos que fueron recolectados en una forma que se pueda usar para modelamiento. Esto se refiere a tecnicas de adición, eliminacion o trasformación de nuestra data.
- **Evaluación del modelo**: este paso trata de evaluar el modelo en tus datos. Esto envuelve elegir metricas de rendimiento para evaluar las habilidades del modelo, estableciendo un punto base con el cual el modelo sera comparado y técnicas de remuestreo para dividir los datos en entrenamiento y testeo para simular como se desarrolla el modelo final. Es común usar más la validación cruzada que el remuestreo y freceuntemente se repite este proceso para mejorar la robustes del resultado.
- **Finalización del modelo**: este paso se preocupa en seleccionar y usar el modelo final. Esto se llama selección de modelo y envuelve evaluaciones adicionales de los modelos canditos en un conjunto de datos de validación, o la selección a travéz de otros criterios específicos del proyecto, como la complejidad del  modelo. Desúes de esto llegara la etapa de  despliegue en donde se integrara con un sistema de produccion y se diseñara una agenda para monitorear y mantener el modulo.

  #### Preparacion de los datos
Em los projectos de modelado, como regresión o clasificación, la data cruda  no se puede usar directamente. Esto es ya que:
- Los algoritmos de aprendisaje requieren datos en formato de números
- Algunos almoritmos de aprendizaje automatico imponen requisitos en los datos.
- Ruido estadistico y error en los datos necesite corregirse.
- Relaciones nolineales complejas puede ser testeada de la data.
De esta manejra los datos crudos debes ser pre-procesados antes de empesar a ajustar y evaluar modelos. 
**Nos podemos referir a la preparación de los datos como la transformación de datos crudos a una forma más adecuada para el modelaje.**
Esto es especifico segun nuestros datos, el objetivo del proyecto, y que algoritmo usaremos para modelar los datos. No obstante, hay tareas estandar que se pueden usar o explorar durante la preparación para modelos de aprendizaje automatico estas incluyen: 
- **Limpieza de datos**: identificar y correjir errores o equivocaciones en los datos.
- **Selección de caracteristicas**: Identificar las cariables de entrada ( o variables explicativas) que son ma´s relevantes para el modelo.
- **Transformación de los dato**: Cambiar la escala o la distribución de las variables.
- **Ingeniería de caracteristicas**: Extraer nuevas variables de los datos disponibles.
- **Reducción de dimensiones**: Crear projecciones compactas de los datos.

Lo anterior trata de descubrir como exponer la estructura detras de los datos para poder usar un algoritmo de aprenizaje. Esto es como una luz en la oscuridad. Por lo tanto, exponer lo desconociso debajo de una estructura de datos es un proceso de descubrimiento, junto con descubrir el mejor rendimiento para el projecto de aprendizaje.

#### ¿Comó escoger las técnicas para la preparacion de los datos?
En princio esta tarea es desafiante, pero si miramos la preparacion de los datos en el contecto como una parte del proyecto se vuelve más sencillo. Los pasos de un proyecto de modelado predictivo antes y después de la etapa de preparación de datos informan sobre la preparación de datos que puede ser necesaria. Los pasos antes de preparar los datos involucran definir el problema. Y como parte de definir el problema, esto también envuelva subtareas tales como:
- Reunir datos del dominio del problema.
- Dicutir el proyecto con expertos en la materia.
- Seleccionar las variables para ser usadas como entrada y salida para un modelo predictivo.
- Revisar los datos que han sido recolectados.
- Resumir la data que ha sido recolectada con metodos estadisticos.
- Visualizar los datos recolectados usando gráficos y diagramas.

La información conocida de la data puede ser usada para seleccionmar y configurar los metodos para la preparación de los datos. Por ejemplo, las gráficas de los datos pueden ayudar a identificar si hay variables con valores extremos (outlier). Esto puede ayudar en operaciones para limpiar los datos. Esto puede ayudar a determinar si las transformaciones de datos que cambian la distribución de probabilidad de las variables serían apropiadas. Metodos estadisticos, como estadistica descriptiva, se pueden ausar para determinar si es posible que se requieran operaciones de escalado. Test de hipotesis estadisticas se usan para determinar si una variable coincide con una probabilidad de distribución data. 
Gráficas y estadistica se usa para determinar si hay variables que se relacionen, y si es asi, que tanto, dando insights en si hay variables que sean redundantes o irrelevantes para la variable objetivo. Como tal, puede haber mucha interacción entre la definición del problema y la preparación de los datos. También puede haber interancción entre la preparación de los datos y la evaluación del modelo. La evaluación del modelo envuelve sub-tareas como:
- Seleccionar una metrica de rendimiento para evaluar las habilidades del modelo predictivo.
- Seleccionar un procedimiento de evaluación de modelos
- Seleccionar algoritmos a evaluar
- Ajustar los hiperparametros del algoritmo 
- Combinar modelos predictivos en conjuntos

La información conocida sobre la elección de algoritmos y el descubrimiento de algoritmos de buen rendimiento también puede servir de base para la selección y configuración de métodos de preparación de datos. Por ejemplo, la elección de un algoritmo puede imponer requerimientos y expectativas del tipo y forma de los datos de entrada. Esto puede acarrear a que las variables tengan distribuciones especificas, la eliminacion de variables de ingresao correlacionadas, y/o variavles que no esten relacionadas con nuestra variable objetivo. 

La elección de la metrica de rendiumiento también requiere preparación cuidadosa de la variable objetivo para cumplir con las expectativas, como un puntaje de un modelo regresivo basado en la predicción del error usando una unidad de medida especifica, requerir la inversión de cualquier transformación de escalado aplicada a esa variable para el modelado. Estos ejemplos, y más, no estan solos. En cambio, es fuertemente influenciada por las tareas realizadas ambas antes y después de la preparación de los datos. Esto pone de manifiesto la naturaleza altamente iterativa de cualquier proyecto de modelado predictivo.
