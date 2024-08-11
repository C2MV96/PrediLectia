# PrediLectia
PrediLectia v1 es un proyecto que implementa un modelo de predicción para bioprocesos utilizando Python. Este modelo se integra con Gradio para ofrecer una interfaz gráfica de usuario (GUI) simple y accesible, permitiendo a los usuarios interactuar con el modelo de manera intuitiva. En lugar de introducir los datos manualmente, PrediLectia utiliza un archivo Excel como fuente de entrada.

Características principales:
Modelos de Predicción: Incluye implementaciones de modelos de crecimiento microbiano y cinética de sustratos, como el modelo logístico, modelo de Gompertz, y modelo de Moser, entre otros.
Interfaz Gráfica con Gradio: Utiliza Gradio para crear una GUI que facilita la carga de un archivo Excel con los datos experimentales, permitiendo la visualización de resultados en tiempo real.
Análisis y Visualización: Incorpora funciones para ajustar los modelos a los datos experimentales, calcular errores, y generar gráficos que visualizan las predicciones en comparación con los datos observados.
Contenido del proyecto:
Importaciones: Configuración inicial e instalación de dependencias necesarias, incluyendo Gradio y bibliotecas científicas como NumPy, Pandas, y Matplotlib.
Definición de clases y métodos: Implementación de la clase BioprocessModel, que contiene métodos estáticos para diferentes modelos de predicción de biomasa, sustrato, y producto.
Configuración de la interfaz: Uso de Gradio para crear una interfaz que permite a los usuarios cargar un archivo Excel y visualizar los resultados de los modelos de predicción.
Instalación y uso:
Para utilizar PrediLectia v1, clona este repositorio e instala las dependencias necesarias. Luego, simplemente ejecuta el notebook para iniciar la interfaz de usuario con Gradio.

bash
Copiar código
pip install -r requirements.txt
jupyter notebook PrediLectia_Gradio_Final_v1.ipynb
Próximos pasos:
Mejoras en la interfaz: Ampliar las opciones de configuración y personalización disponibles en la GUI.
Optimización del modelo: Refinar los algoritmos de predicción para mejorar la precisión y eficiencia.
Documentación detallada: Incluir más ejemplos de uso y una guía detallada para nuevos usuarios.
