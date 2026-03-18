# Insumos-Curso-Magnetotelúrica
Insumos del Curso de Magnetotelúrica Desde Cero: Fundamentos, Procesamiento e Interpretación de los Datos
# 🌍 Curso de Magnetotelúrica (MT) Desde Cero: Fundamentos, Procesamiento e Interpretación de Datos


Este repositorio contiene el desarrollo y los insumos utilizados en el curso como Estrategia de Apropiación Social del Conocimiento asociados al Proyecto 045-2025 titulado:

NUEVAS TECNOLOGÍAS COMPUTACIONALES PARA EL PROCESAMIENTO E INVERSIÓN CONJUNTA DE GRAVIMETRÍA, MAGNETOMETRÍA Y MAGNETOTELÚRICA MEDIANTE APRENDIZAJE PROFUNDO GUIADO POR PRINCIPIOS FÍSICOS PARA LA CARACTERIZACIÓN MULTICRITERIO

El proyecto es financiado por MINCIENCIAS y la Agencia Nacional de Hidrocarburos (ANH), y se desarrolla en alianza con instituciones académicas y de investigación nacionales.
**Dirigido por:** Geól. Cristina Lizcano, PhD (c) & Paul Goyes  
**Institución:** Universidad Industrial de Santander (UIS)  
**Apoyo:** MinCiencias - ANH – Agencia Nacional de Hidrocarburos | Contrato 045-2025  
**Estrategia de apropiación social del conocimiento**

---

## 📁 Estructura del Repositorio

```
📦 Insumos_Curso_MT/
├── 📂 DATOS_MT/                        # Datos crudos de campo
├── 📂 Parte 1_Procesamiento, Análisis e Inversión de Datos MT/
│   ├── 📂 Edi/                         # Archivos EDI exportados desde EMpower
│   ├── 📂 Edi_procesado/               # Archivos EDI procesados en MTPy
│   ├── 📂 figuras/                     # Figuras y gráficos generados
│   ├── 📂 h5/                          # Archivo h5 crudo (collection_crudo.h5)
│   ├── 📂 h5_procesado/                # Archivo h5 procesado
│   ├── 📓 1_Visualizacion.ipynb
│   ├── 📓 2_Preprocesamiento.ipynb
│   ├── 📓 3_Analisis.ipynb
│   └── 📓 4_Inversion1D.ipynb
├── 📂 Parte 2_Procesamiento, Análisis e Inversión de Datos MT/
├── 🐍 environment.yml                  # Entorno Conda con MTPy y SimPEG
└── 📄 READ ME.txt
```

---

## 📡 DATOS_MT

La carpeta `DATOS_MT` contiene los **datos crudos** adquiridos con el equipo de Magnetotelúrica en campo. Incluye:

- **Datos de calibración:** archivos de calibración del equipo MT utilizados para corregir la respuesta instrumental de los sensores.
- **Datos de grabación:** registros de las series de tiempo de los campos electromagnéticos naturales (componentes E y B) capturados durante las campañas de adquisición.

Estos datos son la entrada principal para el procesamiento en el software licenciado **EMpower (Phoenix Geophysics)**, a partir del cual se generan los archivos EDI que se trabajan en los notebooks.

---

## 📓 Parte 1 – Procesamiento, Análisis e Inversión de Datos MT

Esta carpeta contiene los **Jupyter Notebooks** utilizados durante el curso para el flujo completo de trabajo con datos magnetotelúricos usando la librería **MTPy**.

### Notebooks

| Notebook | Descripción |
|---|---|
| `1_Visualizacion.ipynb` | Carga y visualización de datos MT en formato EDI. Exploración de curvas de resistividad aparente y fase. |
| `2_Preprocesamiento.ipynb` | Preprocesamiento de datos: filtrado, rotación de ejes, evaluación de calidad y corrección de estática. |
| `3_Analisis.ipynb` | Análisis de dimensionalidad, descomposición de impedancias, fases invariantes y parámetros de Groom-Bailey. |
| `4_Inversion1D.ipynb` | Inversión 1D de datos MT usando **SimPEG**. Generación de modelos de resistividad en profundidad. |

### Carpetas de datos

- **`Edi/`** – Archivos `.edi` procesados y exportados directamente desde el software licenciado **EMpower de Phoenix Geophysics**.
- **`Edi_procesado/`** – Archivos `.edi` resultantes del procesamiento realizado en **MTPy**.
- **`h5/`** – Archivo `collection_crudo.h5` generado al importar los datos en `MTCollection` de MTPy.
- **`h5_procesado/`** – Archivo `.h5` resultante luego del preprocesamiento aplicado en los notebooks.
- **`figuras/`** – Figuras y gráficos generados durante el procesamiento y análisis.

---

## ⚙️ Instalación del Entorno

El archivo `environment.yml` contiene toda la configuración del entorno **Conda** con las librerías necesarias para ejecutar los notebooks, incluyendo **MTPy** y **SimPEG**.

### Requisitos previos

- [Anaconda](https://www.anaconda.com/download) o [Miniconda](https://docs.conda.io/en/latest/miniconda.html) instalado
- Python 3.11.*
- Sistema operativo: Windows, macOS o Linux

### Pasos de instalación

```bash
# 1. Abrir Anaconda Prompt (Windows) o Terminal (macOS/Linux)

# 2. Navegar al directorio donde se clonó este repositorio
cd ruta/al/repositorio

# 3. Crear el entorno conda desde el archivo yml
conda env create -f environment.yml

# 4. Activar el entorno
conda activate mtpy

# 5. Lanzar JupyterLab
jupyter lab
```

> ⚠️ **Nota:** La creación del entorno puede tardar varios minutos debido al tamaño de las dependencias (especialmente SimPEG). Se recomienda una conexión estable a internet.

### Verificar la instalación

Una vez activo el entorno, puedes verificar que las librerías principales están disponibles ejecutando en Python:

```python
import mtpy
import SimPEG
print("MTPy version:", mtpy.__version__)
print("SimPEG version:", SimPEG.__version__)
```

---

## 🛠️ Librerías Principales

| Librería | Uso en el curso |
|---|---|
| [MTPy](https://github.com/MTgeophysics/mtpy-v2) | Lectura, visualización, procesamiento y análisis de datos MT en formato EDI |
| [SimPEG](https://simpeg.xyz/) | Inversión 1D de datos MT |
| [JupyterLab](https://jupyterlab.readthedocs.io/) | Entorno interactivo para ejecutar los notebooks |

---

## 📌 Notas

- Los datos crudos en `DATOS_MT` fueron adquiridos con equipos **Phoenix Geophysics** y procesados inicialmente con el software licenciado **EMpower**.
- Los archivos EDI son el formato de intercambio estándar para datos MT y son la entrada a MTPy.
- Este material fue desarrollado en el marco del **Contrato 045-2025** de la ANH como parte de una estrategia de apropiación social del conocimiento.

---

## 📬 Contacto

Para preguntas o comentarios sobre el material del curso, puedes contactar a los organizadores a través de la **Universidad Industrial de Santander (UIS)**.

---

*Grupos organizadores: SIGAC · High Dimensional Signal Processing Research Group · GIGBA · CPS Research Group*
