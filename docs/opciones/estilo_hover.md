# estilo_hover
<br />

Se denomina *hover* (en inglés 'planear') a la función que permite resaltar un elemento geográfico de tipo *línea* o *polígono*, cuando pasa el puntero sobre él.

La opción `estilo_hover` permite definir los parámetros de simbolización necesarios para realzar la visualización del elemento.

Se define solamente una sola vez, aplicándose a todas las capas geográficas del mapa.

<br />*Notas*:

*(1)* En caso de no definir alguno de los parámetros posibles, se utilizan por defecto los valores que se indican en la tabla.

<br />

### Propiedades
<br />

Propiedad|Parámetro|Tipo|V.defecto|Descripción
:---|:---|:---|:---:|:---
`estilo_hover`| | | |Representación gráfica de la función *hover*
||`color`|texto|'#ff7800'|Color del trazo expresado en formato hexadecimal RGB #rrggbb.</br>Se puede expresar también mediante su nombre ([lista de colores](https://www.w3.org/TR/SVG/types.html#ColorKeywords)).
||`weight`|entero|2|Anchura del trazo expresada en píxeles.
||`opacity`|número|0.5|Opacidad del trazo.</br>Rango de valores: de 0.0 (totalmente transparente) hasta 1.0 (totalmente opaco).
||`fillColor`|texto|(*color*)|Color de relleno expresado en formato hexadecimal RGB #rrggbb.</br>Se puede expresar también mediante su nombre ([lista de colores](https://www.w3.org/TR/SVG/types.html#ColorKeywords)).</br>El valor por defecto es el correspondiente al parámetro *color*.
||`fillOpacity` |número|0.2|Opacidad del relleno.</br>Rango de valores: de 0.0 (totalmente transparente) hasta 1.0 (totalmente opaco).

<br />

### Código de ejemplo
<br />

El siguiente ejemplo muestra la configuración de la función *hover* actuando sobre una capa GeoJSON.

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración estilo_hover</title>
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
      "estilo_hover": {
           "color": "red",
           "weight": 2,
      },
      "capa_geojson": [
        {"nombre": "Departamentos de Francia",
         "url": "https://raw.githubusercontent.com/gregoiredavid/france-geojson/master/departements.geojson",
         "estilo": {
           "color": "darkorange",
           "weight": 1,
           "opacity": 0.3
          }
        }
      ]
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

<br />

#### Salida gráfica
<br />

La función hover del ejemplo resalta los elementos que se encuentran por debajo del puntero mediante un borde regruesado de color rojo. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_estilo_hover)

![Ejemplo opción estilo_hover](/img/opciones_estilo_hover_salida_grafica.jpg "Ejemplo opción estilo_hover")
