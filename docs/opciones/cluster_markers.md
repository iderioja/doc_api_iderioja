# cluster_markers
</br>

Los *cluster_markers* son asociaciones visuales de elementos puntuales/símbolos, con objeto de que estos sean representados en el mapa de forma agrupada.

El objeto de esta funcionalidad es evitar un efecto visual de *empastado* cuando el número de elementos a representar resulta muy denso para una determinada escala de visualización.

Estableciendo la opción `cluster_markers` al valor **`1`** se activa el clustering de visualización, el valor **`0`** lo desactiva, siendo este último el valor por defecto.

La funcionalidad de clustering que ofrece la *API js IDErioja*, está preconfigurada para un determinado nivel de agrupamiento y escalas de activación. Si desea modificar estos valores, se deberá utilizar el plugin original [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster) con objeto de hacer uso de los parámetros de configuración que este ofrece.

</br>
### Código de ejemplo
</br>
Ejemplo de clustering visual aplicado al *Mapa de Estaciones de Medición de La Rioja* (consulta=4d4b792f6469754163366644435862454d7a314e47773d3d):

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <title>Ejemplo de configuración cluster_markers</title>
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
      "consulta": "4d4b792f6469754163366644435862454d7a314e47773d3d",
      "cluster_markers": 1
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

</br>
####Salida gráfica
</br>

Utilización del clustering para la representación visual simplificada de conjuntos de elementos. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_cluster_markers)

![Ejemplo opción cluster_markers](/img/opciones_cluster_markers_salida_grafica.jpg "Ejemplo opción cluster_markers")
