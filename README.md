# Análisis Estadístico para Selección de Modelos Predictivos

Este repositorio contiene la implementación y evaluación de técnicas estadísticas para la selección robusta de modelos de aprendizaje automático, con un enfoque en el control de errores tipo I y tipo II. El proyecto explora cómo diferentes pruebas estadísticas pueden afectar la selección de modelos y la validez de las conclusiones experimentales.

## Contenido

- Implementación de clasificadores (regresión logística y k-NN)
- Test estadísticos para comparación de modelos:
  - Test de McNemar
  - Test t pareado 5x2 CV
- Análisis de descomposición sesgo-varianza 
- Visualizaciones de resultados

## Resumen del proyecto

Este estudio aborda el problema de la selección de modelos en aprendizaje automático, comparando dos clasificadores (regresión logística y k-NN) mediante técnicas estadísticas rigurosas. Los resultados muestran:

- k-NN supera a la regresión logística (0.787 vs 0.697 de precisión)
- Diferencias estadísticamente significativas:
  - Test de McNemar: χ² = 9.013, p-value = 0.003
  - Test t pareado 5x2 CV: |t| = 3.425, p-value = 0.019
- Análisis sesgo-varianza:
  - Regresión logística: alto sesgo (0.31), baja varianza (0.04)
  - k-NN: menor sesgo (0.22), mayor varianza (0.13)


## Tecnologías utilizadas

- Python 3.x
- NumPy, Pandas
- scikit-learn 
- Matplotlib, Seaborn

## Cómo ejecutar

1. Clonar el repositorio:
```bash
git clone https://github.com/oddissea/model-selection-stats.git
cd model-selection-stats
```

2. Instalar dependencias:
```bash
pip install -r requirements.txt
```

3. Ejecutar el notebook principal:
```bash
jupyter notebook model_selection_analysis.ipynb
```

## Fundamentos teóricos

El proyecto se basa en técnicas estadísticas fundamentales para la comparación de modelos de aprendizaje automático:

### Test de McNemar
Prueba no paramétrica que evalúa si dos clasificadores tienen tasas de error significativamente diferentes. Se construye una tabla de contingencia basada en las clasificaciones correctas e incorrectas de cada modelo.

### Test t pareado 5x2 CV
Método propuesto por Dietterich (1998) que realiza cinco repeticiones de validación cruzada de dos subconjuntos, controlando el error tipo I mientras considera la variabilidad debida a diferentes particiones de datos.

### Descomposición sesgo-varianza
Análisis que descompone el error de predicción en componentes interpretables:
- **Sesgo**: Error debido a suposiciones simplificadoras en el modelo
- **Varianza**: Error debido a la sensibilidad del modelo a fluctuaciones en los datos de entrenamiento

## Referencias

- Dietterich, T. G. (1998). Approximate Statistical Tests for Comparing Supervised Classification Learning Algorithms. Neural Computation, 10(7).
- Hastie, T., Tibshirani, R., & Friedman, J. (2009). The Elements of Statistical Learning: Data Mining, Inference, and Prediction (2nd ed.). Springer.
- Domingos, P. (2000). A Unified Bias-Variance Decomposition for Zero-One and Squared Loss. Proceedings of the Seventeenth International Conference on Machine Learning.

## Licencia

Este proyecto está bajo la licencia MIT - consulta el archivo [LICENSE](LICENSE) para más detalles.