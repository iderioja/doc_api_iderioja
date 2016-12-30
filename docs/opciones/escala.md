# escala
</br>

La opción `escala` permite mostrar en la esquina inferior izquierda del mapa, una barra con una *escala gráfica* de acuerdo con su nivel de detalles.

El valor *`1`* activa la visualización de la escala gráfica. El valor *`0`* oculta la visualización, siendo este último el valor por defecto.

</br>
###Código de ejemplo
</br>

El siguiente ejemplo muestra el código necesario para la incorporación al mapa de una escala gráfica:

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
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

</br>
####Salida gráfica
</br>

Detalle del mapa en el que se puede apreciar la visualización de la escala gráfica. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_escala)

![Ejemplo opción escala](/img/opciones_escala_salida_grafica.jpg "Ejemplo opción escala")
