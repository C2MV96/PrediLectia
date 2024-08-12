# PrediLectia v1

**PrediLectia v1** es un proyecto que implementa un modelo de predicción para bioprocesos utilizando Python. Este modelo está integrado con Gradio, ofreciendo una interfaz gráfica de usuario (GUI) simple y accesible, permitiendo a los usuarios interactuar con el modelo de manera intuitiva. PrediLectia utiliza un archivo Excel como fuente de entrada, evitando la necesidad de introducir datos manualmente.

## Características Principales

- **Modelos de Predicción:** Incluye implementaciones de modelos de crecimiento microbiano y cinética de sustratos, como el modelo logístico, modelo de Gompertz, y modelo de Moser, entre otros.
  
- **Interfaz Gráfica con Gradio:** Utiliza Gradio para crear una GUI que facilita la carga de un archivo Excel con los datos experimentales, permitiendo la visualización de resultados en tiempo real.
  
- **Análisis y Visualización:** Incorpora funciones para ajustar los modelos a los datos experimentales, calcular errores y generar gráficos que visualizan las predicciones en comparación con los datos observados.

## Contenido del Proyecto

1. **Importaciones:** Configuración inicial e instalación de dependencias necesarias, incluyendo Gradio y bibliotecas científicas como NumPy, Pandas y Matplotlib.

2. **Definición de Clases y Métodos:**

   - **Clase `BioprocessModel`:** Esta clase es el núcleo del proyecto, diseñada para encapsular los diferentes modelos de predicción utilizados en bioprocesos. Dentro de esta clase se definen varios métodos estáticos que corresponden a diferentes modelos de crecimiento microbiano y cinética de sustratos.

     - **Método `logistic_model(x, params)`:** Implementa el modelo logístico de crecimiento. Este modelo es ampliamente utilizado para describir el crecimiento microbiano en función del tiempo y se caracteriza por una fase de crecimiento exponencial seguida de una fase de desaceleración hasta alcanzar un estado estacionario.
     
     - **Método `gompertz_model(x, params)`:** Implementa el modelo de Gompertz, que es un modelo sigmoidal comúnmente utilizado para describir el crecimiento de poblaciones microbianas. Es especialmente útil en escenarios donde el crecimiento inicial es lento y se acelera después de un cierto tiempo.
     
     - **Método `moser_model(x, params)`:** Este método implementa el modelo de Moser, que es una modificación del modelo de Monod y es utilizado para describir la cinética de crecimiento de microorganismos en función de la concentración de sustrato.
     
     - **Método `fit_model(x, y, model)`:** Este método se utiliza para ajustar cualquiera de los modelos mencionados anteriormente a los datos experimentales. Recibe como parámetros los datos experimentales `x` (independiente) e `y` (dependiente), así como el modelo a ajustar. Utiliza técnicas de optimización para encontrar los mejores parámetros que minimicen el error entre las predicciones del modelo y los datos observados.
     
     - **Método `calculate_error(observed, predicted)`:** Este método calcula el error entre los datos observados y los predichos por el modelo. Se utilizan métricas comunes como el error cuadrático medio (MSE) y el error absoluto medio (MAE) para cuantificar la precisión del modelo.

     - **Método `generate_plots(x, y, model)`:** Este método se encarga de generar gráficos que comparan los datos observados con las predicciones del modelo. Es útil para visualizar cómo de bien el modelo ajusta los datos experimentales y permite identificar posibles desviaciones.

   - **Métodos adicionales:**
   
     - **`load_data_from_excel(file_path)`:** Función externa que se encarga de cargar los datos desde un archivo Excel. Esta función procesa los datos y los prepara para ser utilizados en los modelos de predicción.

     - **`preprocess_data(data)`:** Método que se encarga de la limpieza y preprocesamiento de los datos antes de ser ingresados al modelo. Este paso es crucial para asegurar la calidad de los datos y la fiabilidad de las predicciones.

     - **`export_results_to_excel(results, output_path)`:** Método que permite exportar los resultados del análisis y las predicciones a un archivo Excel, facilitando así su almacenamiento y revisión posterior.

3. **Configuración de la Interfaz:** Uso de Gradio para crear una interfaz que permite a los usuarios cargar un archivo Excel y visualizar los resultados de los modelos de predicción.

3. **Configuración de la Interfaz:** Uso de Gradio para crear una interfaz que permite a los usuarios cargar un archivo Excel y visualizar los resultados de los modelos de predicción.

## Instalación y Uso

Para utilizar **PrediLectia v1**, sigue estos pasos:

1. Clona este repositorio e instala las dependencias necesarias:

   ```bash
   pip install -r requirements.txt
