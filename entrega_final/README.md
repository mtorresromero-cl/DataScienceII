# 🚗 Clasificación de Canales de Denuncia – Vehículos Mal Estacionados (CABA 2024)

### 📍 Descripción
A partir de técnicas de análisis exploratorio de datos (EDA) y Machine Learning, se desarrollan modelos predictivos para clasificar el canal de denuncia (**Boti/WhatsApp, app, web y canales telefónicos/presenciales**) en función de variables temporales, geográficas y contextuales.

El objetivo es generar **insights accionables** que contribuyan a:
- Mejorar la **gestión de atención ciudadana**.  
- Optimizar la **asignación de recursos** según horario y zona.  
- Potenciar la **experiencia de usuario (UX)** en canales digitales.

---

### 🧩 Estructura del proyecto

- BA_Vehiculos_Mal_Estacionados_2024.ipynb
- data/
- models/
- outputs/
- README.md

---

### 📊 Dataset
- **Fuente:** [Portal de Datos Abiertos GCBA – Sistema Único de Atención Ciudadana (BA Colaborativa, 2024)](https://data.buenosaires.gob.ar/)
- **Base de datos:** https://cdn.buenosaires.gob.ar/datosabiertos/datasets/atencion-ciudadana/sistema-unico-atencion-ciudadana/sistema-unico-de-atencion-ciudadana-2024.csv
- **Conjunto:** Sistema Único de Atención Ciudadana – BA Colaborativa (2024)  
- **Subset:** registros con categoría o tipo “vehículo(s) mal estacionado(s)”  
- **Tamaño:** ~170.000 registros tras limpieza y filtrado  

---

### ⚙️ Metodología
1. **Carga y filtrado de datos:** obtención desde la API y almacenamiento local.  
2. **Limpieza y transformación:** normalización de coordenadas, tratamiento de nulos y creación de variables derivadas (hora, día, mes, franja horaria, fin de semana, barrio, bounding box).  
3. **Análisis exploratorio (EDA):** visualizaciones y estadísticas descriptivas.  
4. Modelado: comparación de modelos supervisados (Dummy, Random Forest y HistGradientBoosting) mediante validación cruzada estratificada.
5. Optimización: ajuste de hiperparámetros del modelo seleccionado mediante RandomizedSearchCV.
6. Evaluación: métricas de accuracy, F1 macro y balanced accuracy sobre un conjunto holdout (20%).


---

### 🧠 Resultados principales
- **Mejor modelo:** HistGradientBoostingClassifier (optimizado)
- **Accuracy (holdout):** ~0.76
- **F1 macro:** ~0.74
- **Balanced accuracy:** ~0.72
- **Variables más influyentes:** coordenadas geográficas (lat/long), hora del día, barrio y franja horaria.

**Principales insights:**
- **Boti/WhatsApp** es el canal dominante, reflejando una fuerte preferencia por la mensajería instantánea.
- Existen patrones temporales claros (pico al mediodía).
- La dimensión territorial es clave para entender la elección del canal.
- El modelo permite anticipar la demanda por canal, útil para planificación operativa y diseño de UX.

---

### 🧰 Tecnologías utilizadas
- **Lenguaje:** Python 3.10+  
- **Librerías principales:**  
  `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `pyproj`, `joblib`  

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

