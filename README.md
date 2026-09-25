# tres-olas
Proyecto Tres Olas  Emmanuel y Salvador - Ironhack proyecto 1
Análisis de incidentes de tiburón relacionados con el surf en USA y Australia
1. Objetivo del proyecto
Este proyecto analiza 629 incidentes no provocados relacionados con personas practicando surf en USA y Australia entre 2000 y 2025, ambos años incluidos.
El objetivo es identificar dónde y cuándo se concentran los incidentes, qué perfiles aparecen con mayor frecuencia y qué diferencias existen en términos de mortalidad entre ambos países.
Los resultados se utilizan como base para orientar un servicio de información y formación dirigido a escuelas y centros de surf, permitiendo identificar zonas prioritarias, periodos en los que reforzar la comunicación y contenidos adaptados al contexto de cada territorio.
Hipótesis
Partimos de la hipótesis de que los incidentes presentan diferencias geográficas, estacionales y de mortalidad que justifican adaptar la información y la preparación de las escuelas de surf a cada territorio.
También analizamos si el verano concentra una mayor proporción de incidentes dentro de cada país, teniendo en cuenta las diferencias de hemisferio entre USA y Australia.

2. Contexto del negocio
El proyecto se plantea en el contexto de un servicio de información, prevención y formación para escuelas y centros de surf.
Una escuela de surf necesita adaptar sus medidas informativas y formativas al entorno en el que desarrolla su actividad. No todos los territorios presentan la misma distribución de incidentes, especies, horarios o características de las personas afectadas.
Por ello, el análisis busca responder a tres necesidades principales:
Identificar las zonas geográficas donde se concentra un mayor número de incidentes.
Determinar los periodos y franjas horarias en los que se producen más incidentes.
Detectar diferencias entre USA y Australia que permitan adaptar los contenidos de información y prevención.
A partir de estos resultados, el servicio podría priorizar determinados territorios y adaptar sus contenidos a las características observadas en cada uno.

3. Dataset
El análisis parte de un dataset de incidentes relacionados con tiburones.
Después de aplicar los filtros y procesos de limpieza, se obtiene una tabla final de:
629 registros
12 columnas
Periodo: 2000–2025
Países: USA y Australia
Actividad: surfing
Tipo de incidente: unprovoked
Variables principales
Variable
Descripción
date_clean
Fecha del incidente después de la limpieza
season
Estación del año
year
Año del incidente
time_group
Franja horaria: mañana, tarde o noche
country
País
state
Estado o territorio
sex
Sexo de la persona afectada
age
Edad
activity
Actividad realizada
type
Tipo de incidente
species_clean
Especie o grupo de especie identificado
life
Resultado del incidente: superviviente o fallecido

Codificación de la variable life
Para facilitar el análisis de mortalidad:
life = 1 → superviviente
life = 0 → fallecido
Los porcentajes obtenidos representan la distribución y mortalidad de los incidentes incluidos en este análisis, no el riesgo absoluto de sufrir un ataque al practicar surf.

4. Calidad y limpieza del dato
Antes del análisis se realizó un proceso de limpieza y homogeneización de las variables.
Principales procesos realizados
Eliminación de columnas que no eran necesarias para el análisis.
Revisión y tratamiento de valores nulos.
Homogeneización de formatos de fechas.
Recuperación del año cuando fue necesario a partir de la información disponible.
Homogeneización de categorías de países, estados y actividades.
Selección de USA y Australia.
Selección de actividades relacionadas con surfing.
Selección de incidentes unprovoked.
Homogeneización de la variable fatal.
Creación de grupos horarios.
Limpieza y agrupación de especies.
Creación de estaciones diferenciadas para USA y Australia según su hemisferio.
En la variable de fecha, la mayoría de los registros disponían de una fecha completa. Cuando fue necesario, se utilizó la información disponible en year para completar determinados registros.
En time, los valores se agruparon en mañana, tarde y noche. Los valores ausentes fueron asignados a la franja predominante utilizada durante la limpieza.
La variable de especie también requirió una importante normalización debido a la variedad de descripciones originales. Tras la limpieza, white shark es la categoría identificada con mayor frecuencia, mientras que una parte de los registros permanece como unknown.

5. Preguntas clave
El análisis se estructura alrededor de las siguientes preguntas:
Distribución geográfica
¿Cuántos incidentes de surf no provocados se registraron en USA y Australia entre 2000 y 2025?
¿Qué país concentra más incidentes?
¿Qué estados presentan una mayor concentración?
¿Qué localizaciones aparecen con mayor frecuencia?
Mortalidad
¿Qué porcentaje de los incidentes fueron fatales y no fatales?
¿Existen diferencias entre USA y Australia?
¿Cómo varía la mortalidad según la franja horaria?
¿Qué especies presentan más incidentes y cuáles aparecen asociadas a incidentes fatales?
Especies
¿Qué especie aparece con mayor frecuencia?
¿Qué especies aparecen en cada país?
¿Cómo se distribuyen por estado y localización?
¿Qué especies aparecen asociadas a los incidentes fatales?
Temporalidad
¿Cuál es la media de incidentes por año?
¿Qué meses concentran más incidentes?
¿Qué estación concentra más incidentes?
¿Se comportan USA y Australia de la misma manera cuando comparamos sus estaciones?
Perfil de las personas afectadas
¿Qué edades aparecen con mayor frecuencia?
¿Qué rangos de edad concentran más incidentes?
¿Qué sexo aparece con mayor frecuencia?
¿Cómo se relacionan edad y sexo con la frecuencia de los incidentes?
Horarios
¿En qué franja horaria se producen más incidentes?
¿Existe una diferencia en la mortalidad según la hora?
Evolución temporal
¿Qué año registró más incidentes?
¿En qué mes y estación se produjeron?
¿En qué país, estado y localización?
¿Se observa una tendencia creciente o decreciente entre 2000 y 2025?

6. Proceso de análisis
El análisis se desarrolló mediante las siguientes etapas:
1. Selección de los datos
Se cargó el dataset original y se seleccionaron:
USA y Australia.
Periodo 2000–2025.
Actividades relacionadas con el surf.
Incidentes clasificados como unprovoked.
2. Limpieza y transformación
Se revisaron los valores nulos y formatos de:
Fecha.
Año.
Hora.
Tipo.
Mortalidad.
País.
Estado.
Localización.
Actividad.
Edad.
Especie.
También se crearon variables derivadas como:
date_clean
time_group
season
species_clean
life
3. Análisis exploratorio
Se realizaron comparaciones por:
País.
Estado.
Estación.
Año.
Mes.
Franja horaria.
Sexo.
Edad.
Especie.
4. Comparación entre países
Las comparaciones se realizan siempre entre USA y Australia, teniendo en cuenta que las estaciones deben interpretarse según el hemisferio correspondiente.
5. Interpretación de negocio
Finalmente, los resultados se relacionan con la propuesta de un servicio de información y formación para escuelas y centros de surf.

7. Resultados e insights
El análisis final contiene 629 incidentes y 12 variables.
Distribución geográfica
Dentro del conjunto analizado, aparecen diferencias claras en la distribución por estados.
En USA, Florida representa aproximadamente el 30,4 % de los incidentes registrados dentro del país en la distribución mostrada por el análisis, seguida por California y Hawaii, ambas alrededor del 6,6 %.
En Australia, New South Wales representa aproximadamente el 27,1 %, seguido por Western Australia, con aproximadamente un 10,9 %.
Esto permite identificar determinados estados como puntos relevantes para estudiar una posible priorización territorial del servicio.
Especies
Después de la limpieza de la variable species, la distribución muestra:
white shark: 350 registros
unknown: 153
tiger shark: 35
multiple possible species: 22
bronze whaler: 19
bull shark: 15
blacktip shark: 14
wobbegong shark: 8
spinner shark: 6
Otras especies: registros minoritarios.
La categoría white shark es, por tanto, la especie/grupo identificado con mayor frecuencia en el dataset limpio. La existencia de 153 registros como unknown debe tenerse en cuenta al interpretar las comparaciones por especie.
Franja horaria
Tras agrupar las horas y completar los valores ausentes, la distribución obtenida es:
Tarde: 389 incidentes
Mañana: 233 incidentes
Noche: 7 incidentes
Por tanto, la tarde concentra la mayor parte de los incidentes del dataset analizado.
En la comparación con life, los registros de la tarde presentan una distribución aproximada de 97,2 % de supervivientes y 2,8 % de fallecidos. En la mañana, la distribución es aproximadamente 93,1 % de supervivientes y 6,9 % de fallecidos.
Estos porcentajes describen la muestra analizada y no deben interpretarse como una probabilidad causal de mortalidad asociada a la hora.
Estacionalidad
La distribución por estación muestra diferencias entre ambos países.
En USA aparecen:
Invierno: 40
Otoño: 173
Primavera: 96
Verano: 123
Desconocida: 5
En Australia:
Invierno: 45
Otoño: 42
Primavera: 50
Verano: 51
Desconocida: 4
La comparación debe realizarse teniendo en cuenta que las estaciones fueron asignadas según el hemisferio de cada país.
Perfil por sexo y edad
El análisis incluye variables de sexo y edad para estudiar el perfil de las personas afectadas.
Los datos muestran una presencia mayoritaria de hombres en las combinaciones de edad analizadas, aunque la interpretación debe realizarse junto con la distribución de la muestra y los valores disponibles para cada grupo.

8. Recomendaciones de negocio
A partir de los patrones observados, la propuesta de servicio puede plantearse de forma diferenciada por territorio y momento.
1. Adaptar el servicio al territorio
Los resultados muestran que la distribución de incidentes no es homogénea entre estados. Por ello, la estrategia de implantación puede considerar diferentes contenidos y prioridades según el territorio.
2. Reforzar la comunicación en determinados periodos
La distribución temporal permite identificar los meses y estaciones con mayor concentración de incidentes para planificar campañas de información antes y durante dichos periodos.
3. Adaptar los contenidos a cada país
USA y Australia presentan distribuciones estacionales diferentes. La comunicación no debería utilizar necesariamente el mismo calendario para ambos países.
4. Incorporar información sobre especies
La identificación de especies puede utilizarse como elemento educativo dentro de los contenidos de las escuelas, especialmente cuando existen diferencias relevantes entre territorios.
5. Utilizar la franja horaria como elemento informativo
La concentración de incidentes durante la tarde puede incorporarse como contexto dentro de los materiales de prevención y formación, sin interpretarla como una relación causal con la mortalidad.

9. Limitaciones
El análisis presenta varias limitaciones que deben tenerse en cuenta:
El dataset recoge incidentes registrados, por lo que no necesariamente representa todos los incidentes que ocurrieron.
El número de incidentes no equivale directamente al nivel de riesgo de una zona, ya que no disponemos de información sobre el número de surfistas, horas practicadas o número de sesiones de surf por territorio.
La variable de especie contiene una cantidad relevante de registros unknown, lo que limita las comparaciones entre especies.
Algunos registros originales presentan fechas, horas o descripciones incompletas.
Parte de los valores ausentes se han completado mediante decisiones de limpieza, por lo que estos valores no deben interpretarse como información observada directamente.
La comparación entre estados no tiene en cuenta diferencias de población, número de surfistas o volumen de actividad.
El análisis identifica asociaciones y distribuciones dentro de la muestra, pero no permite establecer relaciones causales.

10. Próximos pasos
Para ampliar el análisis sería interesante incorporar información adicional que permita contextualizar el número de incidentes.
Datos adicionales
Número de surfistas por país y estado.
Número de sesiones de surf.
Horas de actividad en el agua.
Población de cada territorio.
Evolución de la actividad de surf entre 2000 y 2025.
Información meteorológica y condiciones del mar.
Nuevos análisis
Una ampliación especialmente relevante sería estudiar si el posible crecimiento de la actividad de surf se ha traducido en un aumento de incidentes.
Para ello, sería necesario comparar por año:
actividad de surf → número de incidentes → exposición al riesgo
Esto permitiría diferenciar entre un aumento absoluto de incidentes y un posible aumento del riesgo relativo.
También sería interesante desarrollar:
Análisis geográfico mediante mapas.
Comparación de tasas de mortalidad.
Análisis de tendencias anuales.
Segmentación por rangos de edad.
Análisis conjunto de país + estado + especie.
Dashboard interactivo para escuelas y centros de surf.


12. Conclusión
El análisis de los 629 incidentes registrados entre 2000 y 2025 permite observar diferencias entre USA y Australia en términos de distribución geográfica, temporal, horaria, perfil de las personas afectadas y especies identificadas.
Estos patrones proporcionan una primera base para diseñar un servicio de información y formación para escuelas de surf con un enfoque territorial y temporal, adaptando los contenidos a las características observadas en cada zona.
La principal línea de ampliación consiste en incorporar datos sobre la exposición a la actividad de surf, ya que el número absoluto de incidentes por sí solo no permite medir el riesgo real de cada territorio.
