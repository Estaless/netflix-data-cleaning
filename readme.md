# 🎬 Netflix Data Cleaning & Analytics Pipeline

Este proyecto enfocado en la **Ingeniería de Datos** realiza un proceso de limpieza, transformación y estructuración (fase de Transformación de un ETL) sobre un conjunto de datos público de películas y series de Netflix. El objetivo es normalizar la información y dejarla lista para su consumo en tableros de Business Intelligence (Power BI).

---

## 🛠️ Tecnologías Utilizadas

*   **Python 3** (Lógica de transformación)
*   **Pandas** (Manipulación y limpieza de datos estructurados)
*   **VS Code / Jupyter Notebooks** (Entorno de desarrollo)
*   **Power BI** (Visualización y Analítica de datos)

---

## 🧼 Proceso de Limpieza y Transformación (ETL)

El script de Python aborda los siguientes desafíos de calidad de datos solicitados en la guía de requerimientos:

1.  **Tratamiento de Valores Nulos:** Se identificaron faltantes masivos en campos críticos como `director`, `cast` y `country`. Para evitar la pérdida del 30% del dataset, se aplicó una estrategia de imputación reemplazando los vacíos con etiquetas genéricas (*"Director Desconocido"*, *"Elenco No Disponible"*). Los registros con nulos residuales (menos de 20 filas) fueron eliminados.
2.  **Reducción de Dimensionalidad:** Se eliminaron las columnas `show_id` (identificador interno de negocio sin valor estadístico) y `description` (campo de texto libre/sinopsis largo) para optimizar el peso del archivo y mejorar el rendimiento del procesamiento.
3.  **Casteo de Tipos de Datos:** La columna `release_year` (año de lanzamiento) fue convertida explícitamente a tipo numérico entero (`Integer`) para garantizar un correcto ordenamiento cronológico y evitar formatos decimales erróneos.
4.  **Normalización de Atributos:** Dado que la columna `listed_in` contenía múltiples géneros separados por comas, se procesó la cadena de texto para extraer únicamente el primer valor, creando la columna derivada `genero_principal`.

---

## 📊 Visualización (Dashboard en Power BI)

Una vez exportado el archivo final limpio (`netflix_titles_limpio.csv`), se importó en Power BI Desktop donde se corrigieron errores residuales de consistencia temporal en Power Query y se diseñó un tablero interactivo que incluye:
*   Métricas clave de volumen total de catálogo.
*   Gráfico de barras con el Top de géneros más populares basado en la nueva columna transformada.
*   Línea de tiempo histórica para evaluar la evolución de lanzamientos de la plataforma.
