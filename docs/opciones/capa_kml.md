#capa_kml
</br>

Permite definir un *array* de archivos con la información geográfica a visualizar, expresados en formato [kml](https://developers.google.com/kml/documentation/?hl=es) (Keyhole Markup Language)

En esta opción es posible configurar la representación de los elementos geográficos mediante un conjunto de propiedades de estilo.

</br>
###Propiedades
</br>

Propiedad|Parámetro|Tipo|V.defecto|Descripción
:---|:---:|:---:|:---:|:---
*nombre*| |texto|(nulo)|Nombre de la capa geográfica.
*url*| |texto|(nulo)|**(Obligatorio)** URL absoluta o relativa en la que se ubica el fichero kml.
*estilo*| | | |Representación gráfica de polilíneas y polígonos
||*stroke*|booleano|true|Expresa si se quiere dibujar el trazado exterior (contorno) de un elemento gráfico.</br>Configurar como "no" si se quiere prescindir de los bordes en la representación de polígonos o círculos.
||*color*|texto|'#3388ff'|Color del trazo expresado en formato hexadecimal RGB #rrggbb.
||*weight*|entero|3|Anchura del trazo expresada en píxeles.
||*opacity*|número|1.0|Opacidad del trazo.</br>Rango de valores: de 0.0 (totalmente transparente) hasta 1.0 (totalmente opaco).
||*lineCap*|texto|'round'|Texto que define la forma que se utilizará para rematar el trazo.</br>Valores posibles: ['butt', 'round', 'square'](https://www.w3.org/TR/SVG/painting.html#StrokeLinecapProperty).
||*lineJoin*|texto|'round'|Texto que define la forma que se utilizará para rematar la esquina de un trazo.</br>Valores posibles: ['miter', 'round', 'bevel'](https://www.w3.org/TR/SVG/painting.html#StrokeLinejoinProperty).
||*dashArray*|texto|(nulo)|Cadena de texto que define el patrón de dibujo del trazo.</br>Se expresa mediante una lista de valores separada por comas o espacios en blanco, indicando estos la <longitud> o <porcentaje> que definen los trazados alternativos de líneas y huecos.</br>Si se indica un número impar de valores, se repite la lista hasta alcanzar un número par de valores. Por ejemplo '1,3,2' es equivalente a '1,3,2,1,3,2'.
||*dashOffset*|texto|(nulo)|Texto que expresa la distancia entre el comienzo del trazo y la representación del trazado.
||*fill*|booleano|depende|Esta variable permite colorear el interior de las formas gráficas.</br>El área a colorear es cualquier conjunto de áreas dentro del contorno de la forma, considerando el contorno como la línea perimetral de ancho cero. Para determinar el interior del elemento se tendrán en cuenta todas las subformas conforme a las reglas establecidas en la variable *fillRule*.</br>El valor 'true' activa el coloreado de las formas gráficas, en tanto que el valor 'false' deshabilita su coloreado.
||*fillColor*|texto|*|Color de relleno. El valor por defecto es el correspondiente a la variable *color*.
||*fillOpacity*|número|0.2|Opacidad del relleno.</br>Rango de valores: de 0.0 (totalmente transparente) hasta 1.0 (totalmente opaco).
||*fillRule*|texto|'evenodd'|Texto que define de qué manera se determina el interior de una forma gráfica.</br>Valores posibles: ['nonzero', 'evenodd'](https://www.w3.org/TR/SVG/painting.html#FillRuleProperty)
*icono*| | | |Representación gráfica de marcas e iconos
||*iconUrl*|texto|(nulo)|URL absoluta o relativa en la que se ubica la imagen del icono.
||*iconRetinaUrl*|texto|(nulo)|URL  absoluta o relativa en la que se ubica la imagen del icono, configurada para su uso en dispositivos que soportan el estándar "retina".
||*iconSize*|[x, y]|(nulo)|Tamaño de la imagen del icono (expresado en píxeles).
||*iconAnchor*|[x, y]|(nulo)|Coordenadas del "anclaje" del icono (relativas a su esquina superior-izquierda).</br>El icono se alineará con objeto de que este punto sea la ubicación geográfica del marcador.</br>Si se ha especificado el tamaño (*iconSize*), el valor utilizado por defecto es centrado.
||*popupAnchor*|[x, y]|(nulo)|Coordenadas del punto en las que se abrirá la ventana emergente, respecto al punto de anclaje del icono.
||*shadowUrl*|texto|(nulo)|URL del icono de sombreado.</br>Si no se especifica, no se utilizará sombreado.
||*shadowRetinaUrl*||texto|(nulo)|URL de la imagen "retina" utilizada para el sombreado del icono. Si no se especifica, no se utilizará sombreado.
||*shadowSize*|[x, y]|(nulo)|Tamaño de la imagen de sombreado (expresado en píxeles).
||*shadowAnchor*|[x, y]|(nulo)|Coordenadas del "anclaje" del sombreado (relativas a su esquina superior-izquierda).</br>Si no se especifica se utilizará el valor *iconAnchor*).

</br>
###Código de ejemplo
</br>

El siguiente ejemplo muestra la configuración para la inclusión de dos ficheros geográficos kml:

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <title>Ejemplo de configuración capa_kml</title>
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
      "capa_kml": [
        {
          "nombre": "Montañas del Mundo",
          "url": "https://raw.githubusercontent.com/tucnak/marble/66cf19efddf791e9ee74e842369f2a2bd75526d7/data/placemarks/elevplacemarks.kml",
          "icono":{
            iconUrl:'http://svn.openstreetmap.org/applications/share/map-icons/2020iconset/2020_st_triangle_2.svg',
            iconSize: [24, 24], // tamaño del icono
            iconAnchor: [12, 24], // punto geográfico respecto al xy del icono
            popupAnchor: [0, -24] // punto de anclaje de la burbuja de datos
          }
        },
        {
          "nombre": "Algerie_Telecom",
          "url": "https://raw.githubusercontent.com/stevesong/afterfibre-kml/master/Algeria/Algerie_Telecom/Algerie_Telecom.kml",
          "estilo": {
            "color": "#ff0000",
            "weight": 1,
            "opacity": 1
          }
        }
      ]
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

</br>
###Salida gráfica
</br>

Detalle de un mapa en el que se han incorporado dos archivos kml almacenados en GitHub. Uno de puntos, relativo a [montañas del mundo](https://github.com/tucnak/marble/blob/master/data/placemarks/elevplacemarks.kml), al cual se le ha aplicado una simbolización por medio de un icono, y otro que recoge el trazado de las [redes de telecomunicaciones de Argelia](https://github.com/stevesong/afterfibre-kml/blob/master/Algeria/Algerie_Telecom/Algerie_Telecom.kml), en el que también se han configurado algunas propiedades gráficas.

![Ejemplo opción capa_kml](/img/opciones_capa_kml_salida_grafica.jpg "Ejemplo opción capa_kml")