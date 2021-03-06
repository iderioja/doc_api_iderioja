# popup
<br />

La opción `popup` permite definir la forma en la que se presentan los datos asociados a un elementos geográfico, cuando este es seleccionado.

El parámetro admite los siguientes valores:

- **`0`**- No muestra ninguna información asociada con el elemento geográfico seleccionado.
- **`1`**- Los atributos del elemento se visualizan mediante un bocadillo sobre la zona de mapa (valor por defecto).  
- **`2`**- Se muestran los atributos del elemento seleccionado mediante el despliegue de un panel lateral de información.

<br />*Notas*:

*(1)* La opción **`2`** está especialmente recomendada para dispositivos con pantallas de pequeño tamaño y en los casos en que existe un gran número de atributos o estos tienen una gran extensión.  
Esta opción establece automáticamente el valor de la opción [`panel_info`](opciones/panel_info) = `1`

*(2)* Para mejorar la visualización del panel lateral de información en los dispositivos móviles, se aconseja configurar el parámetro `viewport` en el apartado cabecera (head) del fichero html de la siguiente manera:

    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />  

<br />

### Código de ejemplo
<br />

El siguiente ejemplo muestra la configuración de la función *popup* actuando sobre una capa GeoJSON.

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
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

<br />

#### Salida gráfica
<br />

En este ejemplo, la función *popup* presenta los atributos del elemento selecionado en una cortina lateral.

En él se ha utilizado un fichero GeoJSON disponible en GitHub que contiene información de [pastelerías](https://raw.githubusercontent.com/lyzidiamond/learn-geojson/master/geojson/cupcakes.geojson), sobre el fondo cartográfico *[light_all](https://carto.com/location-data-services/basemaps/)* ofrecido por la compañía *Carto*. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_popup)

![Ejemplo opción popup](/img/opciones_popup_salida_grafica.jpg "Ejemplo opción popup")
