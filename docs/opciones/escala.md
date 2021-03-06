# escala
<br />

La opción `escala` permite mostrar en la esquina inferior izquierda del mapa, una barra con una *escala gráfica* de acuerdo con su nivel de detalle.

Esta opción puede tomar los siguientes valores:

- **`0`**- Oculta la visualización de la escala gráfica (valor por defecto).
- **`1`**- Activa la visualización de la escala gráfica.

<br />

### Código de ejemplo
<br />

El siguiente ejemplo muestra el código necesario para añadir al mapa una escala gráfica:

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración escala</title>
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
      "escala": 1
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

<br />

#### Salida gráfica
<br />

Detalle del mapa en el que se puede apreciar la escala gráfica. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_escala)

![Ejemplo opción escala](/img/opciones_escala_salida_grafica.jpg "Ejemplo opción escala")
