# fondo_base
<br />

La opción `fondo_base` especifica el fondo cartográfico que se utilizará en el mapa, seleccionando una de entre las siguientes opciones disponibles:

|Nombre|fondo_base|Valor|Tipo|url
:---|:---|:---:|:---:|:---
IDErioja - Mapa base|`"iderioja-base"`|`0`|TS|https://ts0.larioja.org/mb.php?z={z}&x={x}&y={y}
IDErioja - Mapa base|`"iderioja-base"`|`1`|TS|https://ts0.larioja.org/mb.php?z={z}&x={x}&y={y}
IDErioja - Ortofografía aérea|`"iderioja-ortofoto"`|`2`||TS|https://ts0.larioja.org/mb_raster.php?z={z}&x={x}&y={y}
IDErioja - Relieve|`"iderioja-relieve"`|`4`|TS|https://ts0.larioja.org/mb_relieve.php?z={z}&x={x}&y={y}
[IGN Mapa Base](http://www.ign.es/wmts/ign-base?request=GetCapabilities&service=WMTS)|`"ign-base"`|`100`|WMTS|http://www.ign.es/wmts/ign-base (Layer=IGNBaseTodo)
[PNOA (SCNE) - Ortofotografía aérea](http://www.ign.es/wmts/pnoa-ma?request=GetCapabilities&service=WMTS)|`"pnoa-ortofoto"`|`101`|WMTS|http://www.ign.es/wmts/pnoa-ma (layer=OI.Orthoimage)
[OpenStreetMap Standard](http://wiki.openstreetmap.org/wiki/Standard_tile_layer)|`"osm-standard"`|`700`|TS|https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png
[Carto - Light_all](https://carto.com/location-data-services/basemaps/)|`"carto-light_all"`|`800`|TS|https://cartodb-basemaps-{s}.global.ssl.fastly.net/light_all/{z}/{x}/{y}.png
[Carto - Dark_all](https://carto.com/location-data-services/basemaps/)|`"carto-dark_all"`|`801`|TS|https://cartodb-basemaps-{s}.global.ssl.fastly.net/dark_all/{z}/{x}/{y}.png
{Sin fondo}|`"blanco"`|`999`| | 

<br />La opción se puede configurar especificando su etiqueta de texto o su correspondiente valor numérico, siendo ambas opciones equivalentes.

La *API js IDErioja* puede representar fondos cartográficos servidos mediante tecnología *TileServer* con configuraciones (TileMatrix) del tipo [*TS*](https://developers.google.com/maps/documentation/javascript/maptypes) utilizada por Google, y la especificación [*TMS*](http://wiki.osgeo.org/wiki/Tile_Map_Service_Specification) *Tile Map Service* de OSGEO.

También se soportan fondos cartográficos provenientes de servicios [*WMTS*](http://www.opengeospatial.org/standards/wmts) *Web Map Tile Service*.

Si no se especifica nada, el valor que se utilizará por defecto es:  el valor **`0`** que corresponde a `"iderioja-base"`.

Una de las ventajas que ofrece utilizar directamente los fondos cartográficos ofertados, es la relativa a la obligación de expresar el *"reconocimiento"* del proveedor del servicio (attribution), ya que dicha información se refleja de forma automática en el mapa.

<br />*Notas*:

*(1)* Aunque para la configuración de la variable `fondo_base` se tratan de la misma forma los fondos cartográficos TS/TMS y WMTS, los *métodos* que emplea internamente la API para su configuración y que el usuario podría utilizar, son muy diferentes, por lo que este aspecto deberá ser tenido en cuenta en el caso de abordar una configuración personalizada.

*(2)* El uso de los fondos cartográficos que se ofertan, están sujetos a las condiciones de uso que fija cada proveedor, por lo que será obligación y responsabilidad del usuario comprobar que la utilización que hace de los mismos se atiene a las condiciones establecidas por este.

<br />

### Código de ejemplo
<br />

El siguiente ejemplo inicializa el mapa con el fondo cartográfico de la Ortofotografía aérea PNOA del [*Sistema Cartográfico Nacional*](http://www.scne.es/), ofertada por el [*Instituto Geográfico Nacional (España)*](http://www.ign.es/ign/main/index.do) a través de un servicio WMTS.

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración fondo_base</title>
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
      "fondo_base": "pnoa-ortofoto"
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```
<br />
En este caso el valor de la variable `"fondo_base": "pnoa-ortofoto"` se podría sustituir por `"fondo_base": 101`.

<br />

#### Salida gráfica
<br />

Ejemplo de uso de la opción *fondo_base=pnoa-ortofoto*. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_fondo_base)
![Ejemplo de uso de la opción fondo_base](/img/opciones_fondo_base_salida_grafica.jpg "Ejemplo de uso de la opción fondo_base")
