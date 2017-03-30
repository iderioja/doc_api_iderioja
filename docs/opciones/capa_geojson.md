# capa_geojson
<br />

La opción `capa_geojson` permite definir un *array* de archivos locales o de servidores externos que contienen las capas geográficas a visualizar.

Los datos geográficos deberán estar expresados en formato [GeoJSON](http://geojson.org/).

Si el fichero GeoJSON es conforme con el formato [GeoJSON CSS](http://wiki.openstreetmap.org/wiki/Geojson_CSS) definido por [OpenStreetMap](https://www.openstreetmap.org), se utilizará por defecto la simbolización que venga definida en el fichero de datos para cada uno de sus elementos. En el caso de que se especifiquen propiedades de *estilo* y/o *icono*, estas modificarán a las contenidas en el fichero GeoJSON CSS.

<br />Notas:

(1) Para datos que pudieran mapearse desde una carpeta *'Public'* de *Dropbox*, se informa [según lo anunciado por esta compañía](https://www.dropbox.com/es/help/16), que a partir del 15 de marzo de 2017 la carpeta *Public* se ha convertido automáticamente en una carpeta estándar.

<br />
###Propiedades
<br />

En esta opción además de las propiedades `nombre` y `url`, es posible configurar la representación de los elementos geográficos mediante un conjunto de parámetros de estilo.

Propiedad|Parámetro|Tipo|V.defecto|Descripción
:---|:---|:---|:---:|:---
`nombre`| |texto|(nulo)|Nombre de la capa geográfica.
`url`| |texto|(nulo)|**(Obligatorio)** URL absoluta o relativa en la que se ubica el fichero GeoJSON.
`estilo`| | | |Representación gráfica de polilíneas y polígonos
||`stroke`|booleano|'true'|Expresa si se quiere dibujar el trazado exterior (contorno) de un elemento gráfico.</br>Configurar como 'false' si se quiere prescindir de los bordes en la representación de polígonos o círculos.
||`color`|texto|'#ff7800'|Color del trazo expresado en formato hexadecimal RGB #rrggbb.</br>Se puede expresar también mediante su nombre ([lista de colores](https://www.w3.org/TR/SVG/types.html#ColorKeywords)).
||`weight`|entero|2|Anchura del trazo expresada en píxeles.
||`opacity`|número|0.5|Opacidad del trazo.</br>Rango de valores: de 0.0 (totalmente transparente) hasta 1.0 (totalmente opaco).
||`lineCap`|texto|'round'|Texto que define la forma que se utilizará para rematar el trazo.</br>Valores posibles: ['butt', 'round', 'square'](https://www.w3.org/TR/SVG/painting.html#StrokeLinecapProperty).
||`lineJoin`|texto|'round'|Texto que define la forma que se utilizará para rematar la esquina de un trazo.</br>Valores posibles: ['miter', 'round', 'bevel'](https://www.w3.org/TR/SVG/painting.html#StrokeLinejoinProperty).
||`dashArray`|texto|(nulo)|Cadena de texto que define el patrón de dibujo del trazo.</br>Se expresa mediante una lista de valores separada por comas o espacios en blanco, indicando estos la *longitud* o *porcentajes* de los trazados alternativos de líneas y huecos. Si se usa un *porcentaje*, este representa una distancia como un porcentaje con respecto a la ventana de visualización actual.</br>Los valores negativos son erróneos. Si la suma de los valores es cero, el trazo se renderizará como si se hubiera especificado el valor nulo.</br>Si se indica un número impar de valores, se repite la lista hasta alcanzar un número par de valores. Por ejemplo '1,3,2' es equivalente a '1,3,2,1,3,2'.
||`dashOffset`|texto|(nulo)|Texto que expresa la distancia en *longitud* o *porcentaje* entre el comienzo del trazo y la representación del trazado. Si se usa un *porcentaje*, este representa una distancia como un porcentaje con respecto a la ventana de visualización actual.
||`fill`|booleano|'true'|Esta variable define si se procede a colorear el interior de las formas gráficas.</br>El área a colorear es cualquier conjunto de áreas dentro del contorno de la forma, considerando el contorno como la línea perimetral de ancho cero.</br>Para determinar el interior del elemento se tendrán en cuenta todas las subformas conforme a las reglas establecidas en la variable *fillRule*.</br>El valor 'true' activa el coloreado de las formas gráficas, en tanto que el valor 'false' deshabilita su coloreado.
||`fillColor`|texto|(*color*)|Color de relleno expresado en formato hexadecimal RGB #rrggbb.</br>Se puede expresar también mediante su nombre ([lista de colores](https://www.w3.org/TR/SVG/types.html#ColorKeywords)).</br>El valor por defecto es el correspondiente al parámetro *color*.
||`fillOpacity` |número|0.2|Opacidad del relleno.</br>Rango de valores: de 0.0 (totalmente transparente) hasta 1.0 (totalmente opaco).
||`fillRule`|texto|'evenodd'|Texto que define de qué manera se determina el interior de una forma gráfica.</br>Valores posibles: ['nonzero', 'evenodd'](https://www.w3.org/TR/SVG/painting.html#FillRuleProperty)
`icono`| | | |Representación gráfica de marcas e iconos
||`iconUrl`|texto|[Símbolo por defecto](https://apigeo.larioja.org/images/marker-icon.png)|URL absoluta o relativa en la que se ubica la imagen del icono.
||`iconRetinaUrl`|texto|[Símbolo por defecto](https://apigeo.larioja.org/images/marker-icon-2x.png)|URL  absoluta o relativa en la que se ubica la imagen del icono, configurada para su uso en dispositivos que soportan el estándar "retina".
||`iconSize`|[x, y]|[25,41]|Tamaño de la imagen del icono (expresado en píxeles).
||`iconAnchor`|[x, y]|[12,41]|Coordenadas del "anclaje" del icono (relativas a su esquina superior-izquierda).</br>El icono se alineará con objeto de que este punto sea la ubicación geográfica del marcador.</br>Si se ha especificado el tamaño (*iconSize*), el valor utilizado por defecto es centrado.
||`popupAnchor`|[x, y]|[1,-34]|Coordenadas del punto en las que se abrirá la ventana emergente, respecto al punto de anclaje del icono.
||`shadowUrl`|texto|[Símbolo por defecto](https://apigeo.larioja.org/images/marker-shadow.png)|URL del icono de sombreado.</br>Si no se especifica, no se utilizará sombreado.
||`shadowRetinaUrl`||texto|(nulo)|URL de la imagen "retina" utilizada para el sombreado del icono. Si no se especifica, no se utilizará sombreado.
||`shadowSize`|[x, y]|(nulo)|Tamaño de la imagen de sombreado (expresado en píxeles).
||`shadowAnchor`|[x, y]|(nulo)|Coordenadas del "anclaje" del sombreado (relativas a su esquina superior-izquierda).</br>Si no se especifica se utilizará el valor *iconAnchor*.

<br />
### Código de ejemplo 1
<br />

El siguiente ejemplo muestra la configuración para una capa GeoJSON que contiene los datos geográficos de los [Departamentos de Francia](https://raw.githubusercontent.com/gregoiredavid/france-geojson/master/departements.geojson), que se encuentra almacenada en un repositorio GitHub.

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración capa_geojson</title>
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
      "capa_geojson": [
        {"nombre": "Departamentos de Francia",
         "url": "https://raw.githubusercontent.com/gregoiredavid/france-geojson/master/departements.geojson",
          "estilo": {
            "color": "#ff0000",
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

En este caso, la visualización de los polígonos de los [departamentos de Francia](https://raw.githubusercontent.com/gregoiredavid/france-geojson/master/departements.geojson) se ha personalizado definiendo su color, grosor de línea y transparencia. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_capa_geojson)

![Ejemplo opción capa_geojson](/img/opciones_capa_geojson_salida_grafica.jpg "Ejemplo opción capa_geojson")

<br />
### Código de ejemplo 2
<br />

El siguiente ejemplo muestra la configuración para la representación de dos capas GeoJSON CSS: [*Medios contra incendios forestales*](https://raw.githubusercontent.com/iderioja/doc_api_iderioja/master/datos_ejemplo/medios_lucha_contra_incendios_forestales.geojson) y [*Parque Natural Sierra de Cebollera (La Rioja)*](https://raw.githubusercontent.com/iderioja/doc_api_iderioja/master/datos_ejemplo/parque_natural_sierra_de_Cebollera.json).

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración capa_geojson_css</title>
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
      "capa_geojson": [
        {"nombre": "Medios contra incendios forestales",
         "url": "https://raw.githubusercontent.com/iderioja/doc_api_iderioja/master/datos_ejemplo/medios_lucha_contra_incendios_forestales.geojson"
         // GeoJSON CSS incluye simbología
        },
        {"nombre": "Parque Natural Sierra de Cebollera",
         "url": "https://raw.githubusercontent.com/iderioja/doc_api_iderioja/master/datos_ejemplo/parque_natural_sierra_de_Cebollera.json"
         // GeoJSON CSS incluye simbología
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

Por tratarse ambas capas de ficheros GeoJSON CSS, estas se representan según la simbología que se encuentra definida en los propios ficheros de datos. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_capa_geojson_css)


![Ejemplo opción capa_geojson](/img/opciones_capa_geojson_css_salida_grafica.jpg "Ejemplo opción capa_geojson")
