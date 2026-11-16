# HMM para Análisis de Sentimientos en Redes Sociales

**Actividad didáctica 2-M2 · Modelo Oculto de Markov · Estándar Q1**  
**IU Digital de Antioquia**

**Estudiante:** Ciro Antonio Carrillo Mendoza  
**Grupo:** Grupos de trabajo 35  
**Asignatura:** Simulación  
**Lenguaje de programación:** Python

---

## 📌 1. Descripción del proyecto

Proyecto académico de carácter práctico-experimental orientado a la aplicación de modelos probabilísticos, simulación estocástica y programación en Python mediante la implementación de un **Modelo Oculto de Markov (HMM, Hidden Markov Model)** para el análisis de sentimientos en redes sociales.

El simulador modela la evolución de sentimientos mediante tres estados ocultos: Positivo, Neutral y Negativo, y tres posibles observaciones: Alegre, Normal y Triste.

El objetivo es comprender el funcionamiento de los modelos de Markov, analizar la relación entre estados ocultos y observaciones, y estudiar experimentalmente el comportamiento de diferentes configuraciones probabilísticas.

## 🎯 2. Objetivos

### Objetivo general

Implementar y analizar un Modelo Oculto de Markov aplicado a la simulación de sentimientos en publicaciones de redes sociales, utilizando Python y herramientas de análisis estadístico.

### Objetivos específicos

- Comprender la estructura y funcionamiento de un HMM.
- Simular secuencias de estados ocultos y observaciones.
- Analizar la influencia de las matrices de transición, emisión y distribución inicial.
- Comparar diferentes escenarios probabilísticos.
- Aplicar análisis estadístico y sensibilidad a los resultados.
- Implementar experimentos reproducibles y documentados.

## 🧠 3. Modelo probabilístico

El sistema utiliza un HMM compuesto por tres estados ocultos y tres observaciones.

### Estados ocultos

| Estado   | Descripción                         |
| -------- | ----------------------------------- |
| Positivo | Representa un sentimiento positivo. |
| Neutral  | Representa un sentimiento neutral.  |
| Negativo | Representa un sentimiento negativo. |

### Observaciones

| Observación | Descripción                               |
| ----------- | ----------------------------------------- |
| Alegre      | Expresión asociada a emociones positivas. |
| Normal      | Expresión neutral o informativa.          |
| Triste      | Expresión asociada a emociones negativas. |

### Parámetros del modelo

El modelo se define mediante tres componentes:

- **A:** matriz de transición entre estados ocultos.
- **B:** matriz de emisión de observaciones condicionadas al estado oculto.
- **π:** distribución inicial de los estados.

El escenario E1 utiliza exactamente las matrices A, B y π establecidas en el enunciado de la actividad.

Los escenarios E2, E3 y E4 corresponden a extensiones experimentales que permiten estudiar diferentes configuraciones del modelo.

## 🛠️ 4. Tecnologías utilizadas

| Tecnología       | Aplicación                                    |
| ---------------- | --------------------------------------------- |
| Python           | Lenguaje de programación.                     |
| Google Colab     | Entorno de ejecución en la nube.              |
| Jupyter Notebook | Desarrollo y documentación interactiva.       |
| NumPy            | Cálculo numérico y simulación probabilística. |
| Pandas           | Manipulación y análisis de datos.             |
| SciPy            | Herramientas estadísticas y probabilísticas.  |
| Matplotlib       | Visualización gráfica.                        |
| Seaborn          | Visualización estadística.                    |
| Markdown         | Documentación del proyecto.                   |
| Git y GitHub     | Control de versiones y publicación.           |

## 📂 5. Estructura del proyecto

```text
HMM_Sentimientos_Redes_Sociales/
│
├── HMM_Sentimientos_Redes_Sociales.ipynb
│
├── docs/
│   └── Carrillo_Ciro_Markov.docx
│
├── resultados/
│   ├── resultados_crudos.csv
│   ├── resumen_estadistico.csv
│   ├── simulacion_base_30_tweets.csv
│   ├── sensibilidad_p.csv
│   ├── sensibilidad_q.csv
│   ├── baum_welch_reinicios.csv
│   ├── fig0.png
│   ├── ...
│   ├── fig9.png
│   └── entorno.txt
│
├── requirements.txt
│
└── README.md
```

### Descripción de los archivos

| Archivo                                 | Descripción                                                                                          |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `HMM_Sentimientos_Redes_Sociales.ipynb` | Notebook principal con código documentado, simulaciones y resultados.                                |
| `docs/Carrillo_Ciro_Markov.docx`        | Documento académico estructurado como artículo.                                                      |
| `resultados_crudos.csv`                 | Resultados de 4 escenarios con 1000 réplicas cada uno.                                               |
| `resumen_estadistico.csv`               | Estadísticas descriptivas, desviación estándar, mínimos, máximos e intervalos de confianza del 95 %. |
| `simulacion_base_30_tweets.csv`         | Simulación de 30 publicaciones con tweets sintéticos.                                                |
| `sensibilidad_p.csv`                    | Resultados del análisis de sensibilidad asociado al parámetro P.                                     |
| `sensibilidad_q.csv`                    | Resultados del análisis de sensibilidad asociado al parámetro Q.                                     |
| `baum_welch_reinicios.csv`              | Resultados de 20 reinicios del algoritmo Baum-Welch.                                                 |
| `fig0.png` – `fig9.png`                 | Figuras generadas durante el análisis, con resolución de 300 dpi.                                    |
| `entorno.txt`                           | Versiones de Python y de las librerías utilizadas.                                                   |
| `requirements.txt`                      | Dependencias necesarias para ejecutar el proyecto.                                                   |

## ▶️ 6. Cómo ejecutar el proyecto

### Google Colab

1. Abrir el archivo `HMM_Sentimientos_Redes_Sociales.ipynb` en Google Colab.
2. Seleccionar **Entorno de ejecución → Ejecutar todo**.
3. Esperar a que finalicen las simulaciones y los análisis.
4. Consultar los resultados generados en la carpeta `resultados/`.
5. Descargar el archivo `resultados.zip`, generado por el notebook.

### Ejecución local

1. Clonar o descargar el repositorio.
2. Instalar las dependencias:

   ```bash
   pip install -r requirements.txt
   ```

3. Abrir el notebook mediante Jupyter Notebook o JupyterLab.
4. Ejecutar las celdas en orden.

## 🔁 7. Reproducibilidad experimental

El proyecto incorpora mecanismos de reproducibilidad para garantizar que los experimentos puedan repetirse bajo las mismas condiciones.

- **Semilla global:** `42`.
- **Semilla individual de cada réplica:** `[42, escenario, réplica]`.
- **Verificación:** mediante una aserción dentro del notebook.
- **Registro de versiones:** Python y librerías en `resultados/entorno.txt`.
- **Número de experimentos:** 1000 réplicas por escenario.
- **Escenarios experimentales:** E1, E2, E3 y E4.

Estas condiciones permiten comparar los resultados y verificar la consistencia de las simulaciones.

## 📊 8. Resultados y análisis

El proyecto contempla:

- Simulación de secuencias de estados y observaciones.
- Comparación de cuatro escenarios probabilísticos.
- Análisis estadístico de 1000 réplicas por escenario.
- Estimación de intervalos de confianza del 95 %.
- Análisis de sensibilidad de parámetros.
- Evaluación de reinicios del algoritmo Baum-Welch.
- Representación gráfica de los resultados.
- Simulación de un caso base con 30 publicaciones.

Los resultados permiten explorar cómo las variaciones en las probabilidades de transición y emisión afectan el comportamiento del modelo y la generación de observaciones asociadas a los sentimientos.

## 🔗 9. Enlaces de interés y entrega

| Recurso               | Enlace                                                                                                |
| --------------------- | ----------------------------------------------------------------------------------------------------- |
| Repositorio GitHub    | [enlace](https://github.com/cirocarrillo01/HMM-Redes-sociales-Sentimientos)                           |
| Notebook Google Colab | [enlace](https://colab.research.google.com/drive/1C26-AVE0zlahAEOblf0l5sBzCC7DlpyJ#scrollTo=f7a7cdd5) |
| Video pitch           | [enlace](https://youtu.be/1jJRRQ1m1Mk)                                                                |
| Documento académico   | `docs/Carrillo_Ciro_EA2.docx`                                                                         |

## 👨‍🎓 10. Autor

**Ciro Antonio Carrillo Mendoza**

IU Digital de Antioquia  
Actividad didáctica 2-M2 · Simulación

---

> **Nota:** Este proyecto fue desarrollado con fines académicos como parte de las actividades de la asignatura Simulación. Su propósito es fortalecer las competencias en modelado probabilístico, simulación estocástica, programación científica y análisis estadístico mediante la aplicación de Modelos Ocultos de Markov.
