<img src="https://cursos.virtual.uniandes.edu.co/isis4219/wp-content/uploads/sites/162/2014/11/cropped-misisheader.png" ><br>
# Machine Learning Techniques - ISIS4219

Intersemestral 2020

**Proyecto de Aplicación: Identificación de melanoma a travez de imagenes**

**Grupo 1 - Integrantes:**

- Daniela María Ortiz Sánchez - 201512150
- Camilo Andrés Ladino Baquero - 201820333
- Ramiro Vargas Salas - 201910642
- Mateo Laguna Guantiva - 201414158

1. **Contexto del problema**

El melanoma es la forma de cáncer de piel más rara y peligrosa. Se estima que en el 2018 se presentaron 287,723 casos nuevos de esta enfermedad en el mundo, causando 60,712 muertes (Bray, F et al., 2018). Según The Skin Cancer Foundation, a pesar de la alta mortalidad que puede causar esta enfermedad, si se detecta a tiempo, casi siempre tiene cura.

Para el diagnóstico, los dermatólogos examinan las lesiones en la piel de sus pacientes y determinan cuáles de ellas pueden ser melanomas. Los sistemas actuales de Inteligencia Artificial que apoyan esta labor diagnóstica no tienen en cuenta imágenes de &quot;contexto&quot;, es decir, que pertenezcan al mismo paciente, lo cual evidencia una limitación en los métodos que hasta el momento se han empleado para apoyar las decisiones de los médicos. Se espera que al tener en cuenta dicha información contextual proveída por varias imágenes de lesiones del mismo paciente, la tarea de detección temprana de los melanomas pueda mejorar significativamente, apoyada por modelos de aprendizaje estadístico.

1. **Objetivos**

**Objetivo general:** diseñar y aplicar una metodología específica para el desarrollo de un sistema de predicción de melanomas en lesiones de la piel, con base en datos e imágenes de contexto de diversos pacientes.

**Objetivos específicos:**

- Realizar un análisis inicial de los datos e imágenes de las lesiones, con el fin de identificar posibles outliers, registros faltantes y el comportamiento de las variables.
- Realizar un preprocesamiento de las imágenes de las lesiones con el fin de identificar sus características, las cuales se emplearán para el entrenamiento de los modelos.
- Limpiar la base de datos de acuerdo con el análisis inicial realizado, aplicar las transformaciones adecuadas, seleccionar y/o agregar variables mediante feature engineering.
- Seleccionar un conjunto de técnicas de aprendizaje estadístico para clasificación (entre ellas Redes Neuronales Convolucionales), calibrar sus parámetros y entrenarlos con el conjunto de entrenamiento.
- Aplicar los modelos seleccionados en el conjunto de test y elegir el que evidencia el mejor desempeño de acuerdo con las métricas de evaluación de modelos para clasificación.

1. **Fuente de datos**

El problema seleccionado para el proyecto proviene de la competencia de Kaggle: SIIM-ISIC Melanoma Classification, donde se proveen los datos para resolver el problema. La colección de imágenes de las lesiones y demás datos de los pacientes proviene de un archivo público de la asociación ISIC (International Skin Imaging Collaboration), en conjunto con la SIIM (Society for Imaging Informatics in Medicine).

Sitio de la competencia: [SIIM-ISIC Melanoma Classification](https://www.kaggle.com/c/siim-isic-melanoma-classification/overview)

1. **Descripción de los datos**

Se cuenta con un total de 108 GB entre los datos de imágenes originales jpeg y procesados al formato tfrec (para este formato, las imágenes fueron redimensionadas a 1024x1024). Para el caso del formato jpeg, se cuentan con alrededor de 11000 imágenes para el conjunto de prueba (test set) y alrededor de 33000 imágenes para el conjunto de entrenamiento (train set).

Además de la colección de imágenes, se provee un set de metadata con los campos descritos en la siguiente tabla (la columna Test/Train indica si la variable aparece en ambos conjuntos de datos o solo en el conjunto de entrenamiento).

| **Variable** | **Tipo** | **Descripción** | **Test/Train** |
| --- | --- | --- | --- |
| Image name | String (caracter) | Código de identificación de la imagen, el cual hace referencia al nombre del archivo de la imagen. | Test y train |
| Patient ID | String (caracter) | Identificador único del paciente. | Test y train |
| Sex | String (caracter) | Sexo del paciente (hombre, mujer o desconocido) | Test y train |
| Age | Número entero | Edad aproximada del paciente en el momento en el que se tomó la imagen. | Test y train |
| Anatomic site | String (caracter) | Ubicación en el cuerpo de la imagen tomada (torso, cabeza, extremidad superior o inferior, etc.). | Test y train |
| Diagnosis | String (caracter) | Diagnóstico de la lesión: desconocido o nuevo (lunar). | Solo en train |
| Benign / Malignant | String (caracter) | Indica si la lesión es benigna o maligna (melanoma). Esta es la variable respuesta. | Solo en train |

1. **Tarea de aprendizaje y justificación**

La tarea de aprendizaje que emplearemos es **clasificación binaria** , debido a que el objetivo principal es predecir si una imagen dada de una lesión de piel corresponde o no a un melanoma, con base en las características de la imagen y del paciente (edad, sexo, sitio de la lesión, etc.). La base de datos es apropiada pues se tienen ejemplos tanto de imágenes con lesiones benignas y malignas (melanomas), como también imágenes de contexto (diferentes imágenes de un mismo paciente).

1. **Criterios de éxito**

Se espera aplicar un modelo con una alta capacidad predictiva, medida a partir del área bajo la curva ROC (AUC) y la sensibilidad (recall). La solución propuesta, debe desempeñarse mejor que los modelos convencionales utilizados que no tienen en cuenta información de contexto, teniendo el potencial de apoyar apropiadamente las decisiones de los dermatólogos.

1. **Referencias bibliográficas**

Bray, F., Ferlay, J., Soerjomataram, I., Siegel, R., Torre, L., &amp; Jemal, A. (2018). Global cancer statistics 2018: GLOBOCAN estimates of incidence and mortality worldwide for 36 cancers in 185 countries [Article]. _Ca-a Cancer Journal For Clinicians_, _68_(6), 394-424. [https://doi.org/10.3322/caac.21492](https://doi.org/10.3322/caac.21492)

Melanoma. (n.d.) Skin Cancer Foundation. [https://cancerdepiel.org/cancer-de-piel/melanoma](https://cancerdepiel.org/cancer-de-piel/melanoma)
