# minimapa
</br>

La opción `minimapa` muestra un pequeño *mapa guía* en la parte inferior derecha del mapa principal.

Este mapa de referencia indica con una veladura de color naranja la extensión geográfica representada en el mapa principal.

El usuario puede desplazar la visualización del mapa principal arrastrando el fondo cartográfico en el interior del mapa guía. Dentro del mapa guía también funcionan las operaciones de zoom asociadas a la rueda del ratón.

El mapa guía ofrece en su interior un botón que permite minimizar o recuperar su visualización.

El valor **`1`** activa la visualización del *mapa guía*. El valor **`0`** oculta la visualización, siendo este último el valor por defecto.

</br>
###Código de ejemplo
</br>

El siguiente ejemplo ofrece una visualización en la que se incluye un pequeño mapa guía:

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración minimapa</title>
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
      "minimapa": 1
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

</br>
####Salida gráfica
</br>

Representación de mapa con inclusión de la herramienta mapa guía en su esquina inferior-derecha. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_minimapa)

![Ejemplo opción minimapa](/img/opciones_minimapa_salida_grafica.jpg "Ejemplo opción minimapa")
