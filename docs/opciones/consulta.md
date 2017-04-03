# consulta
<br />

Como se indica en el apartado [Configuración](configuracion), IDErioja utiliza para la representación de la información almacenada en su base de datos geográfica, unos ficheros de configuración denominados *"Consultas"* que contienen las referencias, los atributos y la simbología de los datos a representar.

La opción `consulta` indica la referencia de la *Consulta de IDErioja* que se desea utilizar.

Este código es suministrado por la *Sección de Sistemas de Información Geográfica y Cartografía* del *Gobierno de La Rioja*.

En el apartado web *"[Mapas temáticos interactivos](https://www.iderioja.larioja.org/index.php?id=30&lang=es)"* se pueden obtener las referencias de todas las consultas disponibles.

La información asociada a la consulta, incluye la capa o conjunto de capas geográficas que se desean visualizar en el mapa, su simbología y los atributos asociados de cada una de ellas, así como el orden de las mismas.

El valor de la consulta utilizado por defecto es `null`.

<br />Notas:

(1) Función de uso exclusivo en el ámbito de consulta IDErioja.

<br />

### Código de ejemplo
<br />

El siguiente ejemplo utiliza la consulta de IDErioja: "*796249706e544633612b4776356352455470737a45413d3d*", correspondiente al *Mapa de los terrenos acotados de setas de La Rioja*.

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración consulta</title>
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
      "consulta": "796249706e544633612b4776356352455470737a45413d3d"
      // Terrenos acotados de setas
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

<br />

#### Salida gráfica
<br />

Mapa de los terrenos acotados de setas de La Rioja que se corresponde con la consulta 796249706e544633612b4776356352455470737a45413d3d. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_consulta)

![Terrenos acotados de setas de La Rioja](/img/opciones_consulta_salida_grafica.jpg "Terrenos acotados de setas de La Rioja")
