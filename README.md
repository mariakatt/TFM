# README

## Proyecto: Modelo de Reconocimiento de Entidades y Sugerencias de Mejora en Textos

Este proyecto implementa un modelo de reconocimiento de entidades (NER) utilizando la librería `spaCy` para identificar términos específicos en textos y sugerir mejoras de lenguaje inclusivo.

### Requisitos

- Python 3.7+
- `spaCy`
- `es_core_news_lg` (modelo en español para spaCy)
- Google Colab (opcional, pero recomendado para montar Google Drive)

### Instalación

1. **Instalar spaCy** y descargar el modelo en español:
    ```bash
    pip install spacy
    python -m spacy download es_core_news_sm
    ```

2. **Montar Google Drive** (si se está utilizando Google Colab):
    ```python
    from google.colab import drive
    drive.mount('/content/drive')
    ```

3. **Estructura de carpetas**:
    - `TFM`: Carpeta principal en Google Drive.
    - `archivos_entrenamiento`: Contiene el archivo `train.txt` con los datos de entrenamiento.
    - `archivos_validacion`: Contiene el archivo `val.txt` con los datos de validación.

### Entrenamiento del Modelo

El modelo se entrena usando un conjunto de datos de entrenamiento con entidades previamente anotadas. El código permite especificar el número de iteraciones para el entrenamiento.

```python
entrenamiento = entrenar(data)
```

El modelo entrenado se guarda en la carpeta especificada en Google Drive (`/TFM/modelo`) y también en el directorio actual bajo el nombre `modelo`.

### Evaluación del Modelo

El modelo se evalúa utilizando un conjunto de datos de validación. Los resultados de la evaluación se imprimen para analizar la efectividad del modelo.


### Uso del Modelo

El modelo entrenado se puede utilizar para analizar nuevos textos. Se identifican entidades específicas y se sugieren mejoras de lenguaje inclusivo.

1. **Ingresar el texto a analizar**:
    ```python
    texto_input = input("Por favor, introduce el texto:")
    ```

2. **Visualizar las entidades reconocidas** en el texto:
    ```python
    displacy.render(doc, style='ent', jupyter=True)
    ```

3. **Sugerir mejoras** basadas en las entidades detectadas:
    ```python
    for ent in doc.ents:
        # Sugerencias según la entidad
    ```

### Sugerencias de Mejora

El modelo está programado para sugerir cambios en términos identificados como potencialmente excluyentes o inadecuados, proponiendo alternativas más inclusivas. Las entidades que se analizan incluyen términos como "alu" (alumnado), "profs" (profesorado), "inv" (equipo de investigación), entre otros.
