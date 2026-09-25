
# Tres Olas

**Emmanuel y Salvador · Ironhack · Proyecto 1**

Análisis de incidentes con tiburones relacionados con el surf en USA y Australia.

## 1. Objetivo del proyecto

Analizamos 629 incidentes no provocados relacionados con personas practicando surf en USA y Australia entre 2000 y 2025, ambos años incluidos.

Nuestro objetivo es identificar:

- Dónde y cuándo se concentran los incidentes.
- Qué perfiles aparecen con mayor frecuencia.
- Qué diferencias existen entre ambos países.
- Qué proporción de los incidentes tiene un resultado mortal.

Utilizamos los resultados para orientar una propuesta de información y formación dirigida a escuelas y centros de surf.

### Hipótesis

Partimos de la hipótesis de que existen diferencias geográficas, estacionales y de mortalidad que justifican adaptar la información y la preparación de las escuelas a cada territorio.

También comprobamos si el verano concentra más incidentes que las otras estaciones dentro de cada país, teniendo en cuenta las diferencias de hemisferio.

## 2. Contexto del negocio

Tres Olas es una propuesta de servicio de información y formación para escuelas y centros de surf.

Buscamos ayudar a las escuelas a adaptar sus contenidos al entorno en el que desarrollan su actividad.

El análisis responde a tres necesidades:

- Identificar los territorios con mayor concentración de incidentes registrados.
- Reconocer las estaciones y franjas horarias con más registros.
- Detectar diferencias entre países que permitan adaptar los contenidos educativos.

Proponemos una aplicación de consulta de información histórica y talleres impartidos por profesionales de emergencias.

## 3. Dataset

Partimos de un dataset de incidentes relacionados con tiburones.

Después de aplicar los filtros y la limpieza, obtenemos el siguiente conjunto de datos:

| Característica | Valor |
| --- | --- |
| Registros | 629 |
| Columnas | 12 |
| Periodo | 2000–2025, ambos incluidos |
| Países | USA y Australia |
| Actividad | `surfing` |
| Tipo de incidente | `unprovoked` |

### Variables principales

| Variable | Descripción |
| --- | --- |
| `date_clean` | Fecha del incidente después de la limpieza |
| `season` | Estación del año según el hemisferio |
| `year` | Año del incidente |
| `time_group` | Franja horaria: mañana, tarde o noche |
| `country` | País |
| `state` | Estado o territorio |
| `sex` | Sexo de la persona afectada |
| `age` | Edad |
| `activity` | Actividad realizada |
| `type` | Tipo de incidente |
| `species_clean` | Especie o categoría asignada durante la limpieza |
| `life` | Resultado del incidente |

### Codificación de `life`

- `life = 1`: superviviente.
- `life = 0`: fallecido.

Los porcentajes describen los incidentes incluidos en el análisis. No representan el riesgo absoluto de sufrir un ataque al practicar surf.

El análisis geográfico final llega a país y estado. La columna `Location` no forma parte de la tabla final.

## 4. Calidad y limpieza de los datos

Antes de analizar los datos, revisamos sus formatos, categorías y valores ausentes.

### Procesos realizados

- Eliminamos columnas que no necesitábamos.
- Seleccionamos USA y Australia.
- Seleccionamos el periodo 2000–2025.
- Agrupamos las actividades relacionadas con surf.
- Seleccionamos los incidentes clasificados como `unprovoked`.
- Unificamos nombres de países y estados.
- Revisamos y tratamos los valores ausentes.
- Unificamos los formatos de fecha.
- Utilizamos el año disponible para completar determinadas fechas.
- Agrupamos las horas en mañana, tarde y noche.
- Revisamos la edad y el sexo.
- Unificamos el resultado del incidente en la variable `life`.
- Agrupamos las descripciones de especies.
- Calculamos las estaciones según el hemisferio de cada país.

### Fechas y estaciones

Convertimos las fechas a un formato común.

Cuando fue posible, utilizamos la información de `year` para completar registros incompletos.

Asignamos las estaciones según el país, porque USA y Australia pertenecen a hemisferios diferentes.

Los registros sin una estación identificable quedaron como `desconocida`.

### Horarios

Agrupamos las horas en tres franjas:

- Mañana.
- Tarde.
- Noche.

Los valores ausentes se asignaron a la franja más frecuente utilizada durante la limpieza.

### Edad

Completamos las edades ausentes con la edad media.

Estos valores son estimaciones incorporadas durante la limpieza.

### Especies

Unificamos las distintas descripciones en categorías comparables.

Algunos valores se completaron con la categoría más frecuente. Otros permanecieron como `unknown`.

Por ello, las categorías finales reflejan tanto la información original como las decisiones de limpieza.

## 5. Preguntas del análisis

### Distribución geográfica

- ¿Cuántos incidentes se registraron en cada país?
- ¿Qué país concentra más registros?
- ¿Qué estados presentan una mayor concentración?

### Mortalidad

- ¿Qué porcentaje de los incidentes fue mortal?
- ¿Qué diferencias encontramos entre USA y Australia?
- ¿Cómo cambia la proporción de casos mortales según la franja horaria?
- ¿Qué especies aparecen asociadas a los fallecimientos?

### Especies

- ¿Qué categoría aparece con mayor frecuencia?
- ¿Qué especies aparecen en cada país?
- ¿Cómo se distribuyen por estado?
- ¿Qué porcentaje de los fallecidos corresponde a cada especie?

### Estaciones y evolución temporal

- ¿Cuántos incidentes se registraron por año?
- ¿Qué meses y estaciones concentran más incidentes?
- ¿El verano presenta el máximo dentro de cada país?
- ¿Qué año tuvo más registros?
- ¿Cómo evolucionaron los incidentes durante el periodo?

### Perfil de las personas afectadas

- ¿Qué edades aparecen con mayor frecuencia?
- ¿Qué rangos de edad concentran más incidentes?
- ¿Qué sexo aparece con mayor frecuencia?
- ¿Cómo se distribuyen los registros por edad y sexo?

### Horarios

- ¿En qué franja horaria se registraron más incidentes?
- ¿Qué proporción de los incidentes de cada franja fue mortal?

## 6. Proceso de análisis

### 6.1. Selección de los datos

Cargamos el dataset original y seleccionamos:

- USA y Australia.
- Años comprendidos entre 2000 y 2025.
- Actividades agrupadas como `surfing`.
- Incidentes clasificados como `unprovoked`.

### 6.2. Limpieza y transformación

Revisamos los formatos y valores de las columnas seleccionadas.

Creamos o transformamos las siguientes variables:

- `date_clean`
- `time_group`
- `season`
- `species_clean`
- `life`

### 6.3. Análisis exploratorio

Agrupamos y comparamos los registros por:

- País.
- Estado.
- Año.
- Mes.
- Estación.
- Franja horaria.
- Sexo.
- Edad.
- Especie.

Calculamos recuentos, porcentajes y medidas descriptivas.

### 6.4. Comparación entre países

Comparamos USA y Australia utilizando el total adecuado para cada pregunta.

Para estudiar qué estación concentra más incidentes dentro de un país, utilizamos como referencia el total de incidentes de ese país.

### 6.5. Interpretación de negocio

Relacionamos los resultados con una propuesta de información y formación para escuelas y centros de surf.

## 7. Resultados principales

### 7.1. Distribución por país

| País | Incidentes | Porcentaje del total |
| --- | ---: | ---: |
| USA | 437 | 69,48 % |
| Australia | 192 | 30,52 % |
| **Total** | **629** | **100 %** |

USA concentra la mayor parte de los registros analizados.

### 7.2. Distribución por estado

Los siguientes porcentajes se calculan sobre el total de incidentes del país correspondiente.

| País | Estado | Incidentes | Porcentaje dentro del país |
| --- | --- | ---: | ---: |
| USA | Florida | 266 | 60,87 % |
| USA | California | 58 | 13,27 % |
| USA | Hawaii | 58 | 13,27 % |
| Australia | New South Wales | 104 | 54,17 % |
| Australia | Western Australia | 42 | 21,88 % |

Florida y New South Wales son los estados con más registros dentro de sus respectivos países.

Estos resultados nos dan un criterio para proponer una primera prueba del servicio en ambos territorios.

### 7.3. Mortalidad

| País | Incidentes | Supervivientes | Fallecidos | Porcentaje de casos mortales |
| --- | ---: | ---: | ---: | ---: |
| USA | 437 | 431 | 6 | 1,37 % |
| Australia | 192 | 171 | 21 | 10,94 % |
| **Total** | **629** | **602** | **27** | **4,29 %** |

USA registra más incidentes, pero Australia presenta una mayor proporción de casos mortales dentro de su conjunto de registros.

### 7.4. Distribución por especie

| Especie o categoría | Incidentes | Porcentaje del total |
| --- | ---: | ---: |
| `white shark` | 350 | 55,64 % |
| `unknown` | 153 | 24,32 % |
| `tiger shark` | 35 | 5,56 % |
| `multiple possible species` | 22 | 3,50 % |
| `bronze whaler` | 19 | 3,02 % |
| `bull shark` | 15 | 2,38 % |
| `blacktip shark` | 14 | 2,23 % |
| `wobbegong shark` | 8 | 1,27 % |
| `spinner shark` | 6 | 0,95 % |
| `other named species` | 4 | 0,64 % |
| `sandtiger shark` | 2 | 0,32 % |
| `blacktip reef shark` | 1 | 0,16 % |

La categoría `white shark` es la más frecuente en la tabla final.

Los 153 registros clasificados como `unknown` representan el 24,32 % del total y deben tenerse en cuenta al interpretar las comparaciones.

### 7.5. Fallecidos por especie

| Especie o categoría | Fallecidos | Porcentaje de los 27 fallecidos |
| --- | ---: | ---: |
| Tiburón blanco | 22 | 81,48 % |
| Especie desconocida | 3 | 11,11 % |
| Tiburón tigre | 2 | 7,41 % |
| **Total** | **27** | **100 %** |

Estos porcentajes se calculan sobre los 27 fallecidos.

No representan el porcentaje de ataques mortales de cada especie.

### 7.6. Franjas horarias

| Franja horaria | Incidentes | Porcentaje del total |
| --- | ---: | ---: |
| Tarde | 389 | 61,84 % |
| Mañana | 233 | 37,04 % |
| Noche | 7 | 1,11 % |

La tarde concentra la mayor parte de los incidentes registrados.

| Franja horaria | Fallecidos | Porcentaje de casos mortales dentro de la franja |
| --- | ---: | ---: |
| Mañana | 16 | 6,87 % |
| Tarde | 11 | 2,83 % |
| Noche | 0 | 0,00 % |

La mañana presenta una mayor proporción de casos mortales entre los incidentes analizados.

Estos resultados describen la muestra y no demuestran que la hora sea la causa de las diferencias.

### 7.7. Estacionalidad

| Estación | USA: incidentes | USA: porcentaje | Australia: incidentes | Australia: porcentaje |
| --- | ---: | ---: | ---: | ---: |
| Primavera | 96 | 21,97 % | 50 | 26,04 % |
| Verano | 123 | 28,15 % | 51 | 26,56 % |
| Otoño | 173 | 39,59 % | 42 | 21,88 % |
| Invierno | 40 | 9,15 % | 45 | 23,44 % |
| Desconocida | 5 | 1,14 % | 4 | 2,08 % |

Los porcentajes se calculan sobre el total de cada país.

- En USA, el otoño concentra más incidentes.
- En Australia, el verano presenta el máximo, con un solo caso más que la primavera.
- La hipótesis de que el verano concentra más incidentes en ambos países no se cumple.

Las estaciones se asignaron según el hemisferio correspondiente.

### 7.8. Perfil por sexo y edad

Estudiamos las variables de sexo y edad para describir a las personas afectadas.

Observamos una presencia mayoritaria de hombres en las combinaciones de edad analizadas.

La interpretación debe tener en cuenta la distribución de los registros y las edades completadas durante la limpieza.

## 8. Recomendaciones de negocio

### 8.1. Adaptar el servicio al territorio

Proponemos contenidos específicos por país y estado.

Florida y New South Wales serían los territorios iniciales para probar el servicio por su concentración de registros dentro de cada país.

### 8.2. Adaptar el calendario de comunicación

Proponemos utilizar las diferencias estacionales para planificar contenidos informativos.

El mismo calendario no resulta adecuado para ambos países.

### 8.3. Incorporar información sobre especies

La distribución de especies puede utilizarse como contenido educativo adaptado a cada zona.

Por ejemplo, en Hawái, el tiburón tigre aparece en el 53,45 % de los incidentes analizados del estado.

### 8.4. Ofrecer formación con profesionales

Proponemos complementar la información histórica con talleres impartidos por profesionales de emergencias.

### 8.5. Validar la propuesta con escuelas

Antes de desarrollar el servicio completo, proponemos probar:

- Una versión sencilla de la aplicación.
- Un taller con profesionales.
- La utilidad de los contenidos para las escuelas.
- El interés en contratar el servicio.

Mediríamos el uso de la aplicación, el aprendizaje de los participantes y la disposición a pagar.

## 9. Limitaciones

- El dataset contiene incidentes registrados y puede no recoger todos los ocurridos.
- El número de incidentes no equivale al riesgo de una zona.
- No disponemos del número de surfistas, sesiones ni horas de actividad por territorio.
- Una parte importante de los registros tiene una especie desconocida.
- Algunos datos originales presentan fechas, horas o descripciones incompletas.
- Parte de los valores ausentes se completó durante la limpieza.
- Los valores asignados no son observaciones recuperadas de la fuente.
- Las comparaciones entre estados no tienen en cuenta el volumen de actividad de surf.
- El análisis describe asociaciones y distribuciones, pero no establece relaciones causales.

## 10. Próximos pasos

### Datos adicionales

Sería útil incorporar:

- Número de surfistas por país y estado.
- Número de sesiones de surf.
- Horas de actividad en el agua.
- Evolución de la práctica del surf.
- Información meteorológica.
- Condiciones del mar.

### Nuevos análisis

Proponemos ampliar el trabajo con:

- Mapas de distribución geográfica.
- Análisis de tendencias anuales.
- Comparaciones de mortalidad.
- Segmentación por rangos de edad.
- Análisis conjunto de país, estado y especie.
- Un panel interactivo para escuelas de surf.

También sería interesante comparar la evolución de la actividad de surf con la evolución de los incidentes.

Esto permitiría distinguir entre un aumento del número de incidentes y un posible cambio en el riesgo por sesión o por hora de actividad.

## 11. Conclusión

El análisis de 629 incidentes registrados entre 2000 y 2025 muestra diferencias entre USA y Australia en la distribución geográfica, las estaciones, los horarios y las especies asociadas.

La hipótesis de que el verano concentra más incidentes en ambos países no se cumple: en USA, el máximo se registra en otoño; en Australia, en verano, con una diferencia mínima frente a primavera.

Estos resultados orientan Tres Olas hacia una propuesta de información local y formación para escuelas y centros de surf.

El siguiente paso es probar el servicio con escuelas y comprobar su utilidad y viabilidad comercial.