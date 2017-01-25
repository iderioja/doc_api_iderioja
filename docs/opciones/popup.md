# popup
</br>

La opción `popup` permite definir la forma en la que se presentan los datos asociados a un elementos geográfico, cuando este es seleccionado.

El parámetro admite los siguientes valores:

- **`0`**- No muestra ninguna información asociada con el elemento geográfico seleccionado.
- **`1`**- Los atributos del elemento se visualizan mediante un bocadillo sobre la zona de mapa (valor por defecto).  
- **`2`**- Se muestran los atributos del elemento seleccionado mediante el despliegue de una cortina lateral.

</br>Notas:

La opción `2` está especialmente recomendada para dispositivos con patallas de pequeño tamaño y en los casos en que existe un gran número de atributos o estos tienen una gran extensión.

</br>
### Código de ejemplo
</br>

El siguiente ejemplo muestra la configuración de la función *popup* actuando sobre una capa GeoJSON.

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <title>Ejemplo de configuración popup</title>
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
      "fondo_base": 800,
      "capa_geojson": [
        {"nombre": "CupCakes",
          "url": "https://raw.githubusercontent.com/lyzidiamond/learn-geojson/master/geojson/cupcakes.geojson", // CupCakes
        }
      ],
	  "popup": 2
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

</br>
#### Salida gráfica
</br>

En este ejemplo, la función *popup* presenta en una cortina lateral los atributos del elemento selecionado.

En él se ha utilizado un fichero GeoJSON disponible en GitHub que contiene información de [pastelerías](https://raw.githubusercontent.com/lyzidiamond/learn-geojson/master/geojson/cupcakes.geojson), sobre el fondo cartográfico *[light_all](https://carto.com/location-data-services/basemaps/)* ofrecido por la compañía *Carto*. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_popup)

![Ejemplo opción popup](/img/opciones_popup_salida_grafica.jpg "Ejemplo opción popup")
