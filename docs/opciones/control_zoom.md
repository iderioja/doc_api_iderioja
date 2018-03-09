# control_zoom
<br />

La opción `control_zoom` configura la visualización en la esquina superior izquierda de la ventana, de los botones que se utilizan para aproximar o alejar el mapa.

El parámetro admite los siguientes valores:

- **`0`**- Oculta la visualización.
- **`1`**- Activa la visualización del control `+ -` del zoom (valor por defecto).  

<br />

### Código de ejemplo
<br />

El siguiente ejemplo muestra el código necesario para eliminar del mapa el control del zoom:

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración control_zoom</title>
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
      "control_zoom": 0
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

<br />

#### Salida gráfica
<br />

Ejemplo de mapa sin control de zoom. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_control_zoom)

![Ejemplo opción escala](/img/opciones_control_zoom_salida_grafica.jpg "Ejemplo opción control_zoom")
