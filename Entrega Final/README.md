<img src="https://cursos.virtual.uniandes.edu.co/isis4219/wp-content/uploads/sites/162/2014/11/cropped-misisheader.png" ><br>
# Machine Learning Techniques - ISIS4219

Intersemestral 2020

**Proyecto de Aplicación: Identificación de melanomas a través de imágenes**

**Grupo 1 - Integrantes:**

- Daniela María Ortiz Sánchez - 201512150
- Camilo Andrés Ladino Baquero - 201820333
- Ramiro Vargas Salas - 201910642
- Mateo Laguna Guantiva - 201414158

## Entrega Final

### Conclusiones:

1. El problema de identificación de melanomas fue de gran complejidad debido principalmente al desbalance de los datos y la poca cantidad de imágenes pertenecientes a la clase de interés (aproximadamente 1.000 imágenes de melanomas de 30.000 imágenes en total).
2. La aplicación de *undersampling* sobre la clase mayoritaria, ayuda a mejorar el balance del conjunto de datos y a evitar el sesgo del modelo. Sin embargo, en un problema altamente desbalanceado como este, la pérdida de tanta información puede ocasionar un conjunto de datos demasiado reducido que dificulta el aprendizaje del modelo, en este caso se empleó una red convolucional.
3. La aplicación de *data augmentation* sobre la clase de minoritaria, ayuda a mejorar el balance del conjunto de datos. Sin embargo, al incrementar la cantidad de imágenes de forma considerable, la red convolucional requerirá más tiempo y más recursos computacionales para entrenarse. Tanto el tiempo como los recursos computacionales fueron una limitante del proyecto, por lo que se aplicó esta técnica en conjunto con *undersampling* para evitar tener un número elevado de imágenes.
4. Debido a los altos requerimientos de capacidad de cómputo necesarios para entrenar la red convolucional, sólo fue posible utilizar 7 de los 15 folds que conformaban el conjunto de datos de entrenamiento. Esto, sumado a los problemas de desbalance y pocas imágenes de la clase de interés, no permitió realizar múltiples iteraciones sobre el modelo y dedicar más tiempo a la etapa de optimización de hiperparámetros, con el fin de obtener un mejor modelo de clasificación de imágenes.
5. Si bien la extracción de características de las imágenes permitió probar más modelos y redujo significativamente los recursos computacionales necesarios para el entrenamiento de los modelos, no se obtuvieron los resultados esperados. Esto puede deberse tanto a los limitantes del problema original (poca representación de la clase minoritaria) como a la falta de experiencia a la hora de extraer las características.
6. El uso de técnicas para abordar el desbalanceo de clases (SMOTE) mejoró ligeramente los resultados en la estrategia de extracción de características. 

### Trabajos Futuros: 

1. Al eliminar la limitante de tiempo que se presentó durante el desarrollo del proyecto, es posible considerar la opción de entrenar la red convolucional empleando todo el conjunto de datos de entrenamiento aplicando las técnicas de *undersampling* y *data augmentation* acompañado de un mayor esfuerzo en la fase de optimización de hiperparámetros.
2. Haciendo uso de *transfer learning*, se puede emplear un modelo que haya sido pre-entrenado para dar solución a un problema de clasificación de impagenes similar a este. 
3. Una opción para abordar la limitante de los recursos computacionales puede ser aplicar reducción de la dimensionalidad (PCA o modelos con un objetivo similar) directamente a las matrices de los datos de las imágenes y luego con las componentes resultantes correr modelos menos complejos que la red convolucional. 
4. Aplicar mejores técnicas para la extracción de características con el apoyo del criterio médico.
