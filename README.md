# DiploDatos2020: ¿Caro o Barato? Análisis de Precios de Almacén en un Contexto Inflacionario
Julieta Bergamasco y Sofía Luján
 
  El presente repositorio contiene notebooks y datasets utilizados en el proyecto de mentoría de la Diplomatura en Ciencia de Datos de FaMAF, edición 2020.

## Descripción
El dataset consiste en extracciones periódicas semanales de la página de Precios Claros (http://preciosclaros.gob.ar/), que contienen la lista de precios de un día de la semana para una serie de productos y proveedores seleccionados. Al momento de la elaboración de este proyecto ya hay cinco extracciones generadas, para las siguientes fechas: 12/04/20, 19/04/20, 26/04/20, 05/05/20 y 18/05/20.

Estos datos fueron obtenidos a partir de un scrapper (open source) disponibilizado por Open Data Córdoba (https://www.opendatacordoba.org/) y los csv fueron puestos a disposición en Kaggle (https://www.kaggle.com/tinnqn/precios-claros-precios-de-argentina).

Proveedores y productos están identificados con una foreing key relacionada con una entidad específica para cada uno de ellos:  sucursales.csv y productos.csv, respectivamente. Dentro de sucursales.csv se encuentra la descripción del proveedor, cadena a la que pertenece, provincia, localidad, latitud, longitud y tipo, entre otros datos.

Por otro lado, dentro de productos.csv se encuentra la descripción de los productos, así como también su formato (presentación), un dato clave al momento de comparar precios. Adicionalmente, existen columnas para identificar la categoría de cada producto. Sin embargo, para la mayoría de ellos, lamentablemente, es un dato faltante.

El objetivo final de este proyecto es encontrar una forma de identificar si un producto está caro o barato, pero no en una sucursal puntual, sino dada una región o ciudad.

## Este tema es interesante porque…
En contextos inflacionarios, se pierde la relación de precios y las señales que deberían enviar al mercado no funcionan. Es decir, la gente ya no puede distinguir fácilmente cuándo un bien en particular está caro o barato. En adición a esto, aparecen costos sociales relacionados a los cambios constantes en los precios y a la pérdida de tiempo que implica buscar el precio más bajo y entender si es un precio normal o exorbitante (en economía son los llamados costos de transacción, como por ejemplo costo de menú y costo de tiempo de compras o shopping time)

Trataremos de responder algunas de las siguientes preguntas:
- ¿Qué tan heterogéneos son los precios en el país y en la región? ¿Hay mucha variabilidad? ¿En dónde son más volátiles?

- ¿Cómo aumentan los precios nominales y cómo varían los precios relativos?

- ¿Cómo hacemos para comparar precios en distintos momentos del tiempo en un contexto inflacionario?

- ¿Qué región tiene en promedio los precios más bajos? ¿Qué cadena de sucursales tiene en promedio los precios más bajos?

- ¿Cómo definimos si un precio dado es caro o barato para cierto producto/región?

- ¿Cómo podemos armar una aplicación que nos oriente sobre si un precio es razonable o no?

## Los Datos
Si querés inspeccionar el conjunto de datos, lo encontrarás en el siguiente repositorio, donde también estará alojado el proyecto completo:

https://github.com/jbergamasco/DiploDatos2020. Pronto estará disponible una notebook con la primera aproximación a los datos.

## Hitos de la Mentoría
### 22/6 Práctico de Análisis y Visualización:
Inicialmente, elaborar un dataset único, descartando las columnas que no sumen información. Luego, visualizar fundamentalmente la dispersión de precios, calcular estadísticos básicos, análisis de distribución de precios, análisis de ubicación de sucursales testigo y de canasta de productos. Dispersión con diferente alcance geográfico: región, ciudad, barrio. Análisis de variables categóricas. Reexpresar en precios relativos (ya que no tenemos un índice de frecuencia semanal para deflactar) y realizar los mismos análisis. Comparar ambos resultados, entendiendo la diferencia entre precio nominal y precio relativo. Analizar evolución semanal de precios relativos y correlación de precios. Por último, presentación de un informe con principales conclusiones.

### 19/7 Práctico de Exploración y Curación
Decisión sobre cómo deben calcularse los precios en términos relativos (qué producto, qué formato, único para todo el dataset o por zona geográfica, etc). Homogeneizar unidades de medida, analizar la existencia de los ID de productos y sucursales en las correspondientes entidades, tratar de asignar una categoría de producto automáticamente a partir de TF aplicado al nombre de los productos y de clusterización, agrupar por cercanía geográfica en regiones, crear nuevas características si fuera necesario. Análisis de valores faltantes y toma de decisión sobre cómo completarlos o si se descartarán los registros, cuáles y por qué. Evaluación y tratamiento de outliers.

### 16/8 Práctico de Introducción al Aprendizaje Automático
Estimación de precios de productos (nominales y relativos), según sucursal y formato, utilizando técnica de regresión, primera aproximación a modelos. Comparar modelos aplicados.

### 13/9 Práctico de Aprendizaje Supervisado
Generar un baseline. Estimación de precios (relativos) de productos, según región y formato. Aplicar las diferentes técnicas utilizadas, para problemas de regresión (incluyendo redes neuronales), variando los parámetros e hiperparámetros posibles, así como las funciones de pérdida. Calcular las métricas aprendidas para tomar decisiones sobre cuál es el mejor modelo.

### 27/9 Práctico de Aprendizaje No Supervisado
Clusterización y aplicación de técnicas para detección de anomalías, que nos permita entender si un producto está caro o barato. Calcular las métricas correspondientes, según modelo aplicado.

### 6/11/2020 – 7/11/2020 Presentación de Mentorías
Dado todo lo visto en la diplomatura, se espera la elección de la técnica más apropiada para el caso. Explicación de por qué es la más apropiada, de acuerdo al objetivo planteado. Obtener las bases para una aplicación que indique si un producto está caro o barato, bajo determinados supuestos.
