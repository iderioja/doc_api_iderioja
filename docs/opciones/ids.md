# ids
<br />

Todos los elementos de la Base de Datos Geográfica del Gobierno de La Rioja disponen de un *Identificador* único y persistente, lo que en términos informáticos se conoce abreviadamente como *ID*.

Dado que en algunas ocasiones es necesario mapear exclusivamente un elemento geográfico o una colección específica de ellos, se ha incorporado una función que permite seleccionar un array de elementos para su representación en base a sus identificadores.

La opción `ids` permite definir la lista de elementos a representar entre los incluidos en una determinada *consulta* IDErioja.

<br />*Notas*:

*(1)* Función de uso exclusivo en el ámbito de consulta IDErioja.

*(2)* Esta opción debe ir precedida siempre por la opción `consulta`.

*(3)* Muestra solamente los elementos con el *ID* indicado, dentro del GeoJSON.

<br />

### Código de ejemplo
<br />

El siguiente ejemplo se representan dos elementos, con los identificadores: *1530324* y *1531877*, entre los incluidos en la consulta de IDErioja: "*796249706e544633612b4776356352455470737a45413d3d*", correspondiente al *Mapa de los terrenos acotados de setas de La Rioja*.

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración ids</title>
    <style>
      body, html{
        height: 100%;
        border: 0;
        padding: 0;
        margin: 0;
      }
      #map{
        width: 100%;
        height: 100%;
      }
    </style>
  </head>
  <body>
    <div id="map"></div>
  </body>
  <script>
    var iderioja_config = {
      "consulta": "796249706e544633612b4776356352455470737a45413d3d",   // Terrenos acotados de setas
      "ids": [
        1530324,
        1531877
      ]
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

<br />

#### Salida gráfica
<br />

Visualización de dos elementos incluidos en el mapa de los terrenos acotados de setas de La Rioja. [(visualizarejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_ids)

![Dos elementos de los acotados de setas de La Rioja](/img/opciones_ids_salida_grafica.jpg "Dos elementos de los acotados de setas de La Rioja")
