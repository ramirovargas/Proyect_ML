<img src="https://cursos.virtual.uniandes.edu.co/isis4219/wp-content/uploads/sites/162/2014/11/cropped-misisheader.png" ><br>
# Machine Learning Techniques - ISIS4219

Intersemestral 2020

**Proyecto de Aplicación: Identificación de melanomas a través de imágenes**

**Grupo 1 - Integrantes:**

- Daniela María Ortiz Sánchez - 201512150
- Camilo Andrés Ladino Baquero - 201820333
- Ramiro Vargas Salas - 201910642
- Mateo Laguna Guantiva - 201414158

## Entrega 3

La entrega consiste de tres desarrollos de código que se llevaron a cabo de manera simultánea y se proceden a explicar a continuación. Pero antes, unas aclaraciones sobre los comentarios que nos hizo la profesora en la última sesión que tuvimos del proyecto:

1. Construimos el código que nos permitiése transformar los archivos TFRecord suministrados por Kaggle en matrices que pudiesen entender los modelos que entrenaríamos. 
2. Tomamos en cuenta la recomendación de la profesora de separar un pequeño set del conjunto de train para poder obtener métricas, dado que Keggle al recibir el modelo no da mucha información acerca de qué tal fue su rendimiento. 
3. Se trabajó el tema del desbalance de las clases. En promedio, cada uno de los 15 folds de imágenes del conjunto de train contiene alrededor de 2000 imágenes. De esas, alrededor de entre el 3% y 4% son melanomas. Por ende, fue indispensable solucionar este problema antes de lograr implementar cualquier modelo. 
4. Se construyó el código para obtener la caracterización de las imágenes de acuerdo a los protocolos médicos.

La siguiente entrega cuenta con 3 archivos ipynb: 

1. El archivo Entrega_3_transformaciones.ipynb se encarga de trabajar el tema del desbalance de las clases. Se encarga de integrar el código que logra ubicar las imágenes con melanomas y les hace un proceso de data augmentation para pasar de un 3% a 4% de las imágenes a alrededor de un 25%. De 60-70 imágenes, a más de 700 imágenes aplicando transformaciones. El ideal era correr este algoritmo con las imágenes de los melanomas en los 15 folds y entrenar la red neuronal con las clases un poco más balanceadas, sin embargo, a lo largo de la entrega nos dimos cuenta que esto estaba tomando demasiado tiempo de procesamiento y no tendríamos los recursos computacionales y el tiempo suficiente para su ejecución. Por lo tanto, se inició un plan B.

2. El archivo Entrega_3_Undersampling se basa en la idea de en vez de incrementar nuestro conjunto de datos para solucionar el desbalance, restar imágenes que no tienen melanomas para tener un conjunto balanceado. Sabemos que no es lo ideal por la pérdida de información, pero nos permitía: 1) tener métricas de rendimiento al lograr ser ejecutado 2) solucionar el desbalance de clases. Se logró entrenar la red neuronal convolucional con 13 de los 15 folds de imágenes obteniendo métricas aceptables de alrededor de 0.63 de precisión y 0.84 de recall. Creemos que es una buena primera aproximación, no obstante, en algún momento creímos que nunca terminaría el entrenamiento del modelo y decidimos tener un plan C. 

3. El archivo Entrega 3 - Image Features contiene el algoritmo que extrae las características de las imágenes en términos de color, simetría, irregularidad de bordes, tamaño, etc. Todas estas características vienen dadas según recomendaciones médicas. La idea era que si el plan B no alcanzaba a ejecutarse, se procedería a hacer el modelo usando únicamente el dataframe de características de las imágenes. A pesar de que no fue necesario, sí se construyó todo el código y se realizaron modelos. Creemos que esta información podría ser útil para la profesora a la hora de darnos retroalimentación para la última entrega. 
