# PrediLectia v1

**PrediLectia v1** es un proyecto que implementa un modelo de predicción para bioprocesos utilizando Python. Este modelo está integrado con Gradio, ofreciendo una interfaz gráfica de usuario (GUI) simple y accesible, permitiendo a los usuarios interactuar con el modelo de manera intuitiva. PrediLectia utiliza un archivo Excel como fuente de entrada, evitando la necesidad de introducir datos manualmente.

## Características Principales

- **Modelos de Predicción:** Incluye implementaciones de modelos de crecimiento microbiano y cinética de sustratos, como el modelo logístico, modelo de Gompertz, y modelo de Moser, entre otros.
  
- **Interfaz Gráfica con Gradio:** Utiliza Gradio para crear una GUI que facilita la carga de un archivo Excel con los datos experimentales, permitiendo la visualización de resultados en tiempo real.
  
- **Análisis y Visualización:** Incorpora funciones para ajustar los modelos a los datos experimentales, calcular errores y generar gráficos que visualizan las predicciones en comparación con los datos observados.

## Contenido del Proyecto

1. **Importaciones:** Configuración inicial e instalación de dependencias necesarias, incluyendo Gradio y bibliotecas científicas como NumPy, Pandas y Matplotlib.
   
2. **Definición de Clases y Métodos:** Implementación de la clase `BioprocessModel`, que contiene métodos estáticos para diferentes modelos de predicción de biomasa, sustrato y producto.
   
3. **Configuración de la Interfaz:** Uso de Gradio para crear una interfaz que permite a los usuarios cargar un archivo Excel y visualizar los resultados de los modelos de predicción.

## Instalación y Uso

Para utilizar **PrediLectia v1**, sigue estos pasos:

1. Clona este repositorio e instala las dependencias necesarias:

   ```bash
   pip install -r requirements.txt
