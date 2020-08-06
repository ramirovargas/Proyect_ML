<img src="https://cursos.virtual.uniandes.edu.co/isis4219/wp-content/uploads/sites/162/2014/11/cropped-misisheader.png" ><br>
# Machine Learning Techniques - ISIS4219

Intersemestral 2020

**Proyecto de Aplicación: Identificación de melanomas a través de imágenes**

**Grupo 1 - Integrantes:**

- Daniela María Ortiz Sánchez - 201512150
- Camilo Andrés Ladino Baquero - 201820333
- Ramiro Vargas Salas - 201910642
- Mateo Laguna Guantiva - 201414158

## Entrega 4

En esta entrega exponemos los principales cambios que realizamos en las dos vías que estamos implementando para la solución del problema.

1. Clasificación directa de las imágenes mediante redes convolucionales: implementamos la técnica del undersampling, junto con data augmentation con el fin de tener más ejemplos de la clase maligna. Corrimos un randomized grid search para calibrar los parámetros de la red neuronal y obtumimos un mejor desempeño respecto al obtenido en la entrega anterior.
2. Extracción de características de las imágenes y predicción: implementamos la técnica de SMOTE para realizar un oversampling en la clase minoritaria. Probamos de nuevo modelos de ensamblaje y hallamos un desempeño ligeramente mejor respecto a la entrega anterior. 
