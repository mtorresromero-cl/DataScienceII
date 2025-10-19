# 🚗 Clasificación de Canales de Denuncia – Vehículos Mal Estacionados (CABA 2024)

### 📍 Descripción
Este proyecto analiza las denuncias por **vehículos mal estacionados** registradas en la **Ciudad Autónoma de Buenos Aires (CABA)** durante el año **2024**, utilizando datos abiertos del **Sistema Único de Atención Ciudadana – BA Colaborativa**.

A partir de técnicas de **análisis exploratorio de datos (EDA)** y **Machine Learning**, se desarrollan modelos predictivos para **clasificar el canal de denuncia** (app, web o presencial/teléfono) en función de variables **temporales, geográficas y contextuales**.

El objetivo es generar **insights accionables** que contribuyan a:
- Mejorar la **gestión de atención ciudadana**.  
- Optimizar la **asignación de recursos** según horario y zona.  
- Potenciar la **experiencia de usuario (UX)** en canales digitales.

---

### 🧩 Estructura del proyecto

BA_Vehiculos_Mal_Estacionados_2024.ipynb # Notebook principal  
data/ # Datos originales y procesados  
models/ # Modelos entrenados (.joblib)  
outputs/ # Gráficos, métricas e informes  
README.md # Descripción del proyecto  


---

### 📊 Dataset
- **Fuente:** [Portal de Datos Abiertos GCBA](https://data.buenosaires.gob.ar/)
- **Base de datos:** https://cdn.buenosaires.gob.ar/datosabiertos/datasets/atencion-ciudadana/sistema-unico-atencion-ciudadana/sistema-unico-de-atencion-ciudadana-2024.csv
- **Conjunto:** Sistema Único de Atención Ciudadana – BA Colaborativa (2024)  
- **Subset:** registros con categoría o tipo “vehículo(s) mal estacionado(s)”  
- **Tamaño:** ~170.000 registros tras limpieza y filtrado  

---

### ⚙️ Metodología
1. **Carga y filtrado de datos:** obtención desde la API y almacenamiento local.  
2. **Limpieza y transformación:** normalización de coordenadas, tratamiento de nulos y creación de variables derivadas (hora, día, mes, franja horaria, fin de semana, barrio, bounding box).  
3. **Análisis exploratorio (EDA):** visualizaciones y estadísticas descriptivas.  
4. **Modelado:** comparación de cinco modelos supervisados (Logistic Regression, Random Forest, XGBoost, CatBoost y HistGradientBoosting).  
5. **Evaluación:** métricas de *accuracy*, *F1 macro* y *balanced accuracy*.  
6. **Interpretación:** análisis de *feature importance* y conclusiones ejecutivas.

---

### 🧠 Resultados principales
- **Mejor modelo:** `HistGradientBoostingClassifier`  
- **Accuracy:** 0.765  
- **F1 macro:** 0.61  
- **Balanced accuracy:** 0.55  
- **Variables más influyentes:** hora, latitud/longitud, barrio, franja horaria, día de semana.  

**Principales insights:**
- La app móvil es el canal dominante (digitalización consolidada).  
- La web aumenta su uso durante noches y fines de semana (segmentación horaria).  
- Conocer los picos por canal permite una gestión adaptativa de recursos.  
- El modelo predice el canal con buena precisión, útil para planificación y UX.

---

### 🧰 Tecnologías utilizadas
- **Lenguaje:** Python 3.10+  
- **Librerías principales:**  
  `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `pyproj`, `joblib`  

---

### 🚀 Cómo ejecutar el proyecto
1. Clonar este repositorio:
   ```bash
   git clone https://github.com/<tu-usuario>/BA_Vehiculos_Mal_Estacionados.git
   cd BA_Vehiculos_Mal_Estacionados

---

🧾 Licencia:   
Este proyecto se publica bajo la licencia MIT.  
Los datos utilizados pertenecen al Gobierno de la Ciudad Autónoma de Buenos Aires y se distribuyen bajo sus términos de uso público.

👤 Autor:  
Miguel Torres Romero  
Cientista político  
Mg. (c) en Investigación en Ciencias Sociales, UBA.  
📧 hola@migueltorresromero.com  
🌐 https://www.migueltorresromero.com  

⭐ Créditos:  
Proyecto desarrollado en el marco del curso Data Science – Coderhouse (2025).  
Inspirado en la búsqueda de soluciones basadas en datos para mejorar la convivencia urbana en CABA.
