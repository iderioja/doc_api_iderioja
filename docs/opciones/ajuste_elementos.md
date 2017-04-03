# ajuste_elementos
<br />

Esta opción `ajuste_elementos`, permite ajustar la extensión del mapa en base a los elementos del GeoJSON que se haya cargado:

  - 0 = sin ajuste
  - 1 = con ajuste a los elementos (opción por defecto)

<br />

### Código de ejemplo
<br />

El siguiente ejemplo muestra la configuración para la desactivación del *ajuste_elementos*, manteniendo la visualización en el nivel de zoom (7) establecido:

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración ajuste_elementos</title>
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
        "consulta": "677068547155355572794f69435762462b4c487854673d3d",
        "zoom_inicial": 7,
        "ajuste_elementos": 0
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

<br />

#### Salida gráfica
<br />

Visualización del ejemplo anterior (ajuste desactivado). [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_ajuste_elementos_1)

![Ejemplo opción ajuste_elementos desactivado](/img/opciones_ajuste_elementos_salida_grafica_1.jpg "Ejemplo opción ajuste_elementos desactivado")

<br />

Visualización del ejemplo anterior pero en este caso, con la opción de ajuste de elementos activada. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_ajuste_elementos_2)

![Ejemplo opción ajuste_elementos activado](/img/opciones_ajuste_elementos_salida_grafica_2.jpg "Ejemplo opción ajuste_elementos activado")
