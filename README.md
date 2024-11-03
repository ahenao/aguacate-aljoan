# aguacate-aljoan
Mini Proyecto UOC_1

Organizacion de equipo

1. Siempre se trabaja en su propia rama
2. Desde local se hace push a su propia rama
3. En github se verifica en la rama que este bien y se hace merge a la rama dev
4. Andres es el que hace los merge a main
5. Las tareas estan en el backlog, se asignan a uno y se ponen en in progress una vez que se comienza con ellas
6. Hacer commit con frecuencia de cambios, y push al menos una vez al día, o al terminar una tarea
7. Un jupyter por tarea/issue
8. Reuniones diarias para verificar avances y problemas

##Analisis de los datos csv

La información incluye los codigos de clasificación de aguacates usando codigos PLU (codigo de búsqueda de precio en íngles).

Estos codigos son de la variedad Hass:
- 4046 - Hass Small
- 4225 - Hass Large
- 4770 - Hass Extra Large

Existen codigos adicionels Hass: 
- 94046 - Organic Hass Small
- 94225 - Organic Hass Large
- 94770 - Organic Hass Extra Large

Codigos de la variedad GEM
- 3509 - variedad GEM de todos los tamaños
- 93509 -veriedad GEM organic de todos los tamaños

Codigos de la variedad Greenskins
- 4222 - Greenskin Small
- 94222 - Organic Greenskin Small
- 4224 - Greenskin Large
- 94224 - Organic Greenskin Large

Referencia:
https://californiaavocado.com/retail/avocado-plus/#:~:text=PLU%20numbers%20are%20used%20to,the%20regular%20four%2Ddigit%20code.

EL *avocado.csv* que estamos analizando solo incluye los codigos PLU Hass para avocado convencionales, aunque tiene otra columna de clasificación para avocado convencional y organico usando los mismo codigos.

Otro punto de interes es que ciertas variedades, como el Hass, tienden a dar buenos rendimientos solo en años alternos. Después de una temporada con un bajo rendimiento, debido a factores como el frío (al cual el aguacate no tolera bien), los árboles tienden a producir abundantemente en la siguiente temporada. Esta cosecha abundante agota los carbohidratos almacenados, lo que resulta en un menor rendimiento en la siguiente temporada, y así se establece el patrón de alternancia en la producción.

Referencia:
https://www.agmrc.org/commodities-products/fruits/avocados#:~:text=They%20are%20thought%20to%20have,followed%20by%20Florida%20and%20Hawaii.

Durante temporadas de bajo rendimiento de los arboles, se compensa la baja producción local (EE.UU) con las importaciones de aguacates procedentes de otros paises como Mejico.

En los datos de avocado.csv, se observa un incremento en los precios del aguacate durante el año 2017. Hemos intentado investigar las causas:

La volatilidad del mercado de aguacates en 2017 se debió a varios factores clave:
(https://www.bbc.com/mundo/noticias-49209380)

Alta demanda global: El consumo de aguacates aumentó significativamente en países como Estados Unidos, Europa y Asia.
Este “boom” del aguacate se debió a su popularidad en la gastronomía y su versatilidad en diferentes platos.

Problemas climáticos: En California, uno de los principales productores de aguacates, hubo una ola de calor que afectó la floración y redujo la producción a la mitad. Esto creó una escasez que elevó los precios.

Transición de cosechas: Hubo un período de transición entre la cosecha anterior y la nueva, lo que también contribuyó a la escasez temporal y al aumento de precios.

Dependencia de México: México es el mayor productor de aguacates del mundo, y cualquier interrupción en su suministro, ya sea por razones climáticas, huelgas o problemas logísticos, afecta significativamente el mercado global.

Estos factores combinados llevaron a una gran volatilidad en los precios del aguacate durante 2017, lo que se reflejó en los datos de ventas utilizados

## utils

Función en data.py: obtener_nuevo_avocado() devuelve el nuevo dataframe con la clasificación de regiones, agrupaciones y ciudades

Para usar los módulos de utils en scripts se hace 
```
from utils.data import obtener_nuevo_avocado()
```
y para usarlos desde jupyter notebook, hay que agregar el path:

```
import sys, os
sys.path.append('../../../aguacate-aljoan/')  # Adjust to the path where utils is located
from utils.data import obtener_nuevo_avocado

nuevo__df = obtener_nuevo_avocado()
```
