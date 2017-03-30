# localizacion
<br />

La opción `localizacion` permite visualizar sobre el mapa la ubicación del usuario.

La función se activa con el valor **`1`**. Esta opción presenta en el visualizador un botón que permite ver sobre el mapa la posición del dispositivo. Si no se especifica un valor o este parámetro se configura con el valor **`0`**, no se muestra.

Este botón, que funciona como un interruptor, se encuentra inicialmente deseleccionado. Pulsando sobre él se geolocaliza en el mapa la ubicación del dispositivo mediante un punto azul y un círculo a su alrededor que informa sobre la precisión. Cuanto menor es el círculo alrededor del punto, mayor es la precisión con la que se ha calculado la posición.

Notas:

(1) - Para el correcto funcionamiento de esta función, es requisito imprescindible que previamente se encuentre activada en el dispositivo la opción de *"localización"*.
<br />

### Código de ejemplo
<br />

El siguiente ejemplo muestra la configuración para la activación del botón de localización:

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración localizacion</title>
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
      "localizacion": 1
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```
<br />

#### Salida gráfica
<br />

Detalle de mapa en el que se ha incluido el botón de localización.  [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_localizacion)

![Ejemplo opción localización](/img/opciones_localizacion_salida_grafica_01.jpg "Ejemplo opción localización")

<br />

Función de localización activada.

![Ejemplo activación de la localizacion](/img/opciones_localización_salida_grafica_02.jpg "Ejemplo activación de la localizacion")
