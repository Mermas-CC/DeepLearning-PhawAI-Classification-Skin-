# Clasificación de Lesiones de Piel con Transfer Learning

Este proyecto implementa y compara el rendimiento de tres modelos de aprendizaje profundo preentrenados (ResNet50, MobileNetV2 y EfficientNetB0) para la clasificación de lesiones cutáneas, utilizando el enfoque de **Transfer Learning**.

---

### **Ruta y Dataset**

* **Ruta Elegida:** Clasificación con modelos preentrenados (Transfer Learning).
* **Dataset:** HAM10000.
    * **Fuente:** Kaggle Hub, disponible en `kagglehub.dataset_download("kmader/skin-cancer-mnist-ham10000")`.
    * **Licencia:** ODC-By (Open Data Commons Attribution License).

---

### **Cómo ejecutar el código**

1.  **Entorno:** El código está diseñado para ser ejecutado en un entorno de Jupyter Notebook o Google Colab.
2.  **Hardware:** Es **altamente recomendable** usar una GPU para acelerar el entrenamiento. En Google Colab, asegúrate de ir a `Entorno de ejecución` > `Cambiar tipo de entorno de ejecución` y seleccionar `GPU`.
3.  **Descarga:** El notebook gestionará automáticamente la descarga del dataset de Kaggle Hub.

---

### **Cómo entrenar y evaluar**

1.  **Configuración inicial:** La sección `Setup` del notebook instala las bibliotecas necesarias y configura los parámetros globales.
2.  **Carga y preprocesamiento de datos:** La sección `Datos` descarga el dataset, carga la metadata, realiza las particiones estratificadas y aplica **data augmentation** para balancear el conjunto de entrenamiento. La sección `Preprocesamiento` define las transformaciones para las imágenes.
3.  **Entrenamiento:** La sección `Entrenamiento` contiene las funciones para crear, entrenar y validar los tres modelos (`ResNet50`, `EfficientNetB0`, `MobileNetV2`) usando **early stopping**. Solo ejecuta las celdas correspondientes a cada modelo para iniciar el entrenamiento.
4.  **Evaluación final:** La sección `Evaluación` evalúa el modelo entrenado en el conjunto de prueba (`test_loader`), generando un reporte de clasificación detallado, métricas macro (F1, Precision, Recall) y la matriz de confusión.

---

### **Generación de métricas y gráficos**

* **Métricas de entrenamiento:** Los gráficos de la curva de **pérdida (loss)** y **precisión (accuracy)** se generan automáticamente durante el entrenamiento y se muestran en el notebook.
* **Métricas de evaluación:** La sección `Evaluación` imprime el reporte de clasificación y las métricas macro. Además, genera y muestra la **matriz de confusión**.
* **Comparación final:** La sección `General` al final del notebook crea un gráfico comparativo de barras para visualizar y contrastar la precisión y la pérdida de validación final de los tres modelos, lo que permite identificar el de mejor rendimiento.
* **Guardado de resultados:** La sección `Guardado de resultados` exporta todas las métricas, gráficos y el modelo entrenado a una carpeta local llamada `results` para su posterior análisis.
