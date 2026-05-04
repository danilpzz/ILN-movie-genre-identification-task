# ILN Movie Genre Identification Task

Proyecto de clasificación multi-etiqueta de géneros cinematográficos a partir del título y la descripción de cada película.

## Descripción

El objetivo es predecir uno o varios géneros para cada película del conjunto de test.  
Cada entrada contiene:

- `movie_name`
- `description`

El conjunto de entrenamiento incluye además la columna `genre`, con una o varias etiquetas separadas por coma.

## Enfoque

Se probaron varios modelos:

1. **Baseline clásico**
   - TF-IDF sobre texto
   - Regresión logística One-vs-Rest

2. **RoBERTa-base**
   - Fine-tuning para clasificación multi-etiqueta
   - Salida sigmoide por género
   - Umbrales optimizados por clase sobre validación

3. **Ensemble**
   - Combinación de probabilidades de RoBERTa-base y TF-IDF + Logistic Regression
   - Optimización del peso del ensemble y de los umbrales por clase
