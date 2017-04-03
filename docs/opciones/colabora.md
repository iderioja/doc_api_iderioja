# colabora
<br />

La opción `colabora` añade un control que permite una vez activado por el usuario, pulsar en el mapa y capturar la coordenada del punto seleccionado.

Esta opción puede tomar dos valores posibles:

  - 0 = No muestra el control (valor por defecto)
  - 1 = Visualiza el control.

<br />Notas:

(1) El botón no tiene ningún estilo determinado para facilitar así su personalización en las aplicaciones.

(2) En el ámbito de *IDErioja* se utiliza este control para ofrecer a los usuarios un formulario de recogida y envío de sugerencias.

<br />

### Código de ejemplo
<br />

El siguiente ejemplo muestra el código necesario para incluir en el mapa el control *colabora*:

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración colabora</title>
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
      "colabora": 1
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

<br />

#### Salida gráfica
<br />

Ejemplo de mapa con el control *colabora*. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_colabora)

![Ejemplo opción colabora](/img/opciones_colabora_salida_grafica.jpg "Ejemplo opción colabora")
