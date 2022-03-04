# Notas de tidymodels

Basadas en [Tidy Modeling with R](https://www.tmwr.org/) (tmwr).

`tidymodels` es un metapaquete compuesto de los siguientes paquetes:

- [`recipes`]() para pre-procesamiento
- [`parsnip`]() para modelar
- [`yardstick`]() para evaluar la ejecución del modelo
- [`rsample`]() para dividir y muestrear y evaluar
- [`tune`]() para mejorar y ajustar parámetros de modelos
  

## Taxonomía de modelos

De acuerdo a [tmwr](https://www.tmwr.org/software-modeling.html#software-modeling), los modelos se dividen en:

- *Descriptivos*, que sirven para "describir o ilustrar características de datos", y puede ser visual o mostrar artefactos. Por ejemplo, modelos no paramétricos como LOESS (*locally estimated scatterplot smoothing*) suele ser usado para indicar una tendencia o encontrar alguna estructura dada.
- *Inferenciales*, que son usados para la toma de decisiones (e.g., para responder positiva o negativamente a una pregunta, que usualmente toman la forma de una hipótesis del tipo $H_0: \theta_1 - \theta_2 = 0$). Usualmente estos modelos producen un resultado probabilístico, como un valor p, intervalo de confianza o, si se usan métodos bayesianos, una probabilidad posterior. A diferencia de los modelos descriptivos, los modelos inferenciales requieren de asunciones sobre los datos, como por ejemplo, asunciones distribucionales o formas funcionales (e.g., si los errores se distribuyen normalmente, si la esturctura de los datos es lineal o cuadrática, etc).
- *Predictivos*, los cuales sirven básicamente para anticipar un resultado basado en un modelo entrenado y refinado con datos pasados. Si el modelo tiene la forma `f(x) ~ x` y estimamos $f$, queremos predecir *nuevos* valores $\hat f(x_{\text{new}})$ no observados anteriormente a partir de nuevos valores de $x$, y además también queremos saber qué tan precisas pueden ser esas predicciones, con lo cual cuantificamos la incertidumbre. En este modelo, "el problema es uno de *estimación* en lugar de inferencia". La pregunta que se desea contestar acá no es del tipo "¿será $\hat f(x_{\text{new}}) > \theta$?" sino "¿cuál será el valor de $\hat f(x_{\text{new}})$?". Si se trata de un producto del que un vendedor quiere aprovisionarse, también desería saber un margen de error para su compra.

## Glosario

- Feature extraction: factores derivados a partir de un conjunto de datos originales. El conjunto de datos puede ser reducido a un conjunto menor que represente y contenga la información relevante del conjunto original. Ejemplos
  - ICA, PLS, PCA.
- Feature selection
- Normalización
- Escalar
- Matriz de diseño