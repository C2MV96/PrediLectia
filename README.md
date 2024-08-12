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

3. **Configuración de la Interfaz con Gradio:**

   Gradio es una biblioteca de Python que permite crear interfaces gráficas de usuario (GUI) de manera rápida y sencilla para aplicaciones de machine learning y procesamiento de datos. En **PrediLectia v1**, Gradio se utiliza para facilitar la interacción del usuario con el modelo de predicción de bioprocesos, permitiendo cargar datos, configurar parámetros y visualizar resultados en tiempo real, todo desde una interfaz web accesible.

   - **Carga de Archivos Excel:** La interfaz de Gradio está diseñada para permitir que los usuarios carguen archivos Excel directamente desde su dispositivo. Este archivo contiene los datos experimentales que serán utilizados por los modelos de predicción. La funcionalidad de carga está implementada mediante el componente `gr.inputs.File`, que acepta archivos `.xlsx` y los prepara para ser procesados por el backend.

   - **Selección de Modelos:** Una vez cargado el archivo Excel, la interfaz permite al usuario seleccionar el modelo de predicción que desea aplicar a los datos. Esta selección se realiza a través de un menú desplegable (`gr.inputs.Dropdown`), que incluye opciones como el modelo logístico, Gompertz y Moser. El usuario puede elegir el modelo más adecuado según las características de sus datos experimentales.

   - **Parámetros del Modelo:** Gradio permite que el usuario ajuste los parámetros del modelo directamente desde la interfaz. Estos parámetros pueden incluir valores iniciales, límites de optimización, y otros ajustes específicos del modelo seleccionado. Esta funcionalidad se implementa con campos de entrada como `gr.inputs.Slider` y `gr.inputs.Textbox`, proporcionando un control detallado sobre la configuración del modelo.

   - **Ejecución y Visualización:** Al configurar los parámetros y seleccionar el modelo, el usuario puede ejecutar la predicción presionando un botón de acción (`gr.Button`). Gradio procesará los datos utilizando el modelo seleccionado y mostrará los resultados en tiempo real. Los resultados incluyen gráficos interactivos generados con Matplotlib que comparan los datos experimentales con las predicciones del modelo, permitiendo una visualización clara del ajuste del modelo.

   - **Exportación de Resultados:** Una vez que el usuario está satisfecho con los resultados, la interfaz permite exportar los resultados a un archivo Excel. Este archivo contendrá las predicciones generadas por el modelo, junto con los parámetros utilizados y las métricas de error calculadas. Esta función está integrada en la interfaz con Gradio para facilitar la exportación de los datos procesados.

   - **Interfaz Amigable:** Toda la configuración está orientada a ser intuitiva y fácil de usar, incluso para usuarios que no tienen experiencia técnica avanzada. Gradio permite empaquetar todas estas funcionalidades en una interfaz web que se puede ejecutar localmente o desplegar en un servidor para acceso remoto.

   - **Demostración en Tiempo Real:** La interfaz permite a los usuarios ver cómo los cambios en los parámetros del modelo afectan los resultados en tiempo real. Esto es posible gracias a la capacidad de Gradio para actualizar dinámicamente los gráficos y resultados conforme se ajustan los parámetros, proporcionando una experiencia interactiva y educativa.

  

## Instalación y Uso

Para utilizar **PrediLectia v1**, sigue los pasos detallados a continuación. Estos pasos te guiarán desde la clonación del repositorio hasta la ejecución de la interfaz gráfica de usuario (GUI) con Gradio para comenzar a realizar predicciones de bioprocesos.

### Requisitos Previos

Antes de comenzar, asegúrate de tener lo siguiente:

- **Python 3.7 o superior:** PrediLectia está desarrollado en Python, por lo que necesitarás tener instalado Python en tu sistema. Puedes descargarlo desde [python.org](https://www.python.org/downloads/).

- **Jupyter Notebook:** PrediLectia se ejecuta en un entorno de Jupyter Notebook, que es una herramienta interactiva para el desarrollo y ejecución de código Python. Si no tienes Jupyter Notebook instalado, puedes instalarlo siguiendo las instrucciones de la [documentación oficial](https://jupyter.org/install).

### Paso 1: Clonar el Repositorio

Primero, clona el repositorio de PrediLectia desde GitHub en tu máquina local. Abre tu terminal o línea de comandos y ejecuta el siguiente comando:

```bash
git clone https://github.com/tu-usuario/PrediLectia.git
```

Esto descargará todos los archivos del proyecto en un directorio llamado `PrediLectia` en tu sistema.

### Paso 2: Crear y Activar un Entorno Virtual (Opcional)

Es recomendable crear un entorno virtual para evitar conflictos de dependencias con otras bibliotecas de Python instaladas en tu sistema. Para crear un entorno virtual, sigue estos pasos:

1. Navega al directorio del proyecto:

   ```bash
   cd PrediLectia
   ```

2. Crea un entorno virtual:

   ```bash
   python -m venv venv
   ```

3. Activa el entorno virtual:

   - En Windows:

     ```bash
     .\venv\Scripts\activate
     ```

   - En macOS/Linux:

     ```bash
     source venv/bin/activate
     ```

### Paso 3: Instalar Dependencias

Con el entorno virtual activado (o sin él, si decidiste no usar uno), instala las dependencias necesarias ejecutando el siguiente comando:

```bash
pip install -r requirements.txt
```

Este comando instalará todas las bibliotecas listadas en el archivo `requirements.txt`, incluyendo Gradio, NumPy, Pandas, Matplotlib, y otras necesarias para el funcionamiento de PrediLectia.

### Paso 4: Ejecutar el Notebook de PrediLectia

Una vez que las dependencias estén instaladas, puedes ejecutar el notebook que contiene la interfaz y lógica del proyecto. Para hacerlo, sigue estos pasos:

1. Inicia Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

2. En el navegador que se abrirá automáticamente, navega hasta el archivo `PrediLectia_Gradio_Final_v1.ipynb` y haz clic en él para abrirlo.

### Paso 5: Interactuar con la Interfaz de Usuario

Dentro de Jupyter Notebook, ejecuta las celdas del archivo `PrediLectia_Gradio_Final_v1.ipynb` en orden. Esto inicializará la interfaz de usuario con Gradio.

- **Carga de Datos:** Utiliza la interfaz para cargar un archivo Excel con tus datos experimentales.
  
- **Configuración del Modelo:** Selecciona y configura el modelo de predicción que deseas aplicar.
  
- **Ejecución:** Ejecuta el modelo y visualiza los resultados directamente en la interfaz, que incluirá gráficos y métricas de error.
  
- **Exportación:** Si estás satisfecho con los resultados, utiliza la opción de exportación para guardar los datos predichos en un nuevo archivo Excel.

### Paso 6: Desactivar el Entorno Virtual (Si Aplicable)

Si has utilizado un entorno virtual, puedes desactivarlo una vez que hayas terminado de trabajar con PrediLectia ejecutando:

```bash
deactivate
```

### Troubleshooting

- **Problemas de Instalación:** Si encuentras problemas durante la instalación de dependencias, asegúrate de que tu versión de Python sea compatible y que las versiones de las bibliotecas especificadas en `requirements.txt` estén actualizadas.

- **Errores de Ejecución:** Si ocurren errores al ejecutar el notebook, verifica que todos los pasos anteriores se hayan seguido correctamente y que las celdas se ejecuten en el orden correcto.

- **Actualizaciones:** Si realizas actualizaciones en el código o las dependencias, asegúrate de reinstalar las dependencias con `pip install -r requirements.txt` para evitar incompatibilidades.

---

Siguiendo estos pasos, deberías poder instalar y utilizar PrediLectia v1 de manera efectiva en tu entorno local. Si tienes alguna pregunta o encuentras problemas durante el proceso, no dudes en consultar la documentación adicional o abrir un issue en GitHub.
