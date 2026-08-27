# Optimización de decisiones de compra — NovaPlas Hogar

Proyecto de la asignatura Programación para Analítica de Datos — Universidad Central (2026-2).

## El problema

NovaPlas Hogar es una empresa comercializadora de productos plásticos para el hogar, con un portafolio de 1000 SKU. Este proyecto responde la pregunta del caso: 

**¿qué productos deben comprarse, en qué cantidad, y si la compra es conveniente en costo y presupuesto?**

## Cómo ejecutar el notebook

1. Abre `NovaPlas_Hogar.ipynb` en [Google Colab](https://colab.research.google.com) (subiéndolo directamente o abriéndolo desde GitHub).
2. Corre las celdas en orden, de arriba hacia abajo (Entorno de ejecución → Ejecutar todas).
3. Los 5 CSV se cargan automáticamente desde este repositorio: el notebook los lee directo desde GitHub usando `pd.read_csv()` sobre la URL "raw" de cada archivo.
4. Al final, se genera y descarga automáticamente un archivo Excel con la solución (`Reporte_compras_novaplas_<fecha>.xlsx`).

## Qué hace el notebook

1. Carga los 5 CSV desde GitHub.
2. Lee los parámetros del negocio (días del mes, límite de aumento de costo, presupuesto) y arma un diccionario de tiempos de entrega por proveedor.
3. Limpia el inventario: identifica y excluye los productos con dato de inventario inválido (`#N/D`).
4. Calcula la venta mensual promedio de cada producto a partir del histórico 2025.
5. Une catálogo, ventas, inventario y tiempos de entrega en una sola tabla.
6. Corrige valores atípicos de Stock de seguridad (datos inconsistentes con la demanda real).
7. Calcula demanda, punto de reorden, necesidad de compra y conveniencia de costo para cada SKU.
8. Prioriza la compra recomendada según el presupuesto disponible.
9. Presenta resultados agregados (total general y por proveedor) y un gráfico de la distribución de compra por proveedor.
10. Exporta la solución final a un archivo Excel con 3 hojas (compra aprobada, resumen por proveedor, y todos los productos), descargado automáticamente con la fecha del día.

## Librerías usadas

- `pandas` — lectura y manipulación de datos tabulares.
- `numpy` — cálculos numéricos vectorizados.
- `matplotlib` — visualización (gráfico de torta).
- `openpyxl` — exportación a Excel.

## Fuente de datos

Los 5 archivos CSV en `data/` provienen del caso de estudio "NovaPlas Hogar".

## Uso de inteligencia artificial generativa

Este proyecto se desarrolló con apoyo de un asistente de IA (Claude, Anthropic), usado como herramienta de aprendizaje para entender y practicar estructuras de código (listas, tuplas, diccionarios, funciones, arreglos de NumPy, máscaras booleanas, filtrado con pandas, entre otras).
