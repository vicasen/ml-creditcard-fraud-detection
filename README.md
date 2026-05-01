# Detección de Fraude en Transacciones con Tarjeta de Crédito

Este proyecto tiene como objetivo detectar transacciones fraudulentas con tarjetas de crédito utilizando modelos de Machine Learning, abordando el problema del fuerte desbalanceo de clases.

Se comparan distintos enfoques supervisados y no supervisados para evaluar cuál ofrece mejor rendimiento en términos de recall y F1-score, métricas clave en problemas de fraude.

---

## Dataset

Fuente: Kaggle – Credit Card Fraud Detection Dataset (2013 European card transactions)

El dataset **no está incluido en este repositorio** debido a su tamaño.

👉 Puedes descargarlo aquí:
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

Después de descargarlo, coloca el archivo `creditcard.csv` en la carpeta:

### Descripción del dataset

Número de muestras: 284 807
Número de variables: 30 variables numéricas y 1 variable objetivo CLASS
Descripción: 
    Dataset altamente desbalanceado que contiene transacciones reales de tarjetas de crédito realizadas en 2013. 
    Las variables V1–V28 son componentes principales obtenidas mediante PCA para preservar el anonimato de los datos, junto con *Time*, *Amount* y la etiqueta *Class* que indica si la transacción es fraudulenta '1' o legítima '0'.

---

## Tecnologías utilizadas

- Python  
- pandas  
- numpy  
- matplotlib  
- seaborn  
- scikit-learn  
- imbalanced-learn (SMOTE)

---

## Modelado

Modelos utilizados:

- Logistic Regression  
- Random Forest  
- Gaussian Naive Bayes  
- Isolation Forest  
- Local Outlier Factor  
- HistGradientBoostingClassifier  

Técnicas aplicadas:

- Estandarización de datos (StandardScaler)  
- División train/test  
- Manejo de desbalanceo con SMOTE  
- Evaluación con métricas (accuracy, precision, recall, F1-score)  

---

## Resultados

### Regresión logística
TP (Fraude detectado)           :     33  
TN (Legítima correcta)          : 56,832  
FP (Falsa alarma)               :     32  
FN (Fraude no detectado)        :     65  

Accuracy            : 0.9983  
Precision           : 0.5077  
Recall              : 0.3367  
F1 Score            : 0.4049  

---

### Naive Bayes
TP : 75 | TN : 56,256 | FP : 608 | FN : 23  

Accuracy            : 0.9889  
Precision           : 0.1098  
Recall              : 0.7653  
F1 Score            : 0.1921  

---

### Random Forest
TP : 59 | TN : 56,854 | FP : 10 | FN : 39  

Accuracy            : 0.9991  
Precision           : 0.8551  
Recall              : 0.6020  
F1 Score            : 0.7066  

---

### HistGradientBoosting
TP : 71 | TN : 56,852 | FP : 12 | FN : 27  

Accuracy            : 0.9993  
Precision           : 0.8554  
Recall              : 0.7245  
F1 Score            : 0.7845  

---

### Isolation Forest
TP : 13 | TN : 9,521 | FP : 479 | FN : 479  

F1 Score muy bajo → no adecuado para este dataset sin ajuste

---

### Local Outlier Factor
TP : 19 | TN : 9,527 | FP : 473 | FN : 473  

F1 Score muy bajo → no adecuado para este dataset sin ajuste

---

## Conclusiones

- Los modelos supervisados superan claramente a los no supervisados.
- HistGradientBoostingClassifier obtiene el mejor equilibrio entre precision y recall.
- Random Forest también presenta resultados sólidos.
- Los modelos no supervisados no son adecuados para este dataset sin más ajuste.
- Debido al desbalanceo, accuracy no es una métrica fiable; se prioriza recall.

---

## Estructura del proyecto

```bash
ml-creditcard-fraud-detection/
├── data/
│   ├── creditcard.csv
│   └── creditcard_limpio.csv
├── notebooks/
├── README.md
└── requirements.txt

```

## Cómo ejecutar el proyecto

```bash

git clone https://github.com/vicasen/ml-creditcard-fraud-detection.git
cd ml-creditcard-fraud-detection
pip install -r requirements.txt
jupyter notebook

```
Abrir el archivo `ml_fraud_detection_creditcard.ipynb` en el navegador.

---

## Autor

Nombre: **[Víctor Asenjo Pascual]**
GitHub: https://github.com/vicasen

---

