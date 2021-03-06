# Configuración
<br />

Para configurar un mapa dentro de una página web, es necesario editar su código *html* de la siguiente manera:

 - Declaración de la aplicación como *HTML5* utilizando `<!DOCTYPE html>`.
 - Creación de un `<div>` denominado `"map"`, en el que se visualizará el mapa.
 - Definición de las opciones del mapa, dentro de la variable `iderioja_config`.
 - Inclusión del `<script>` de la API js IDErioja.

Para la representación de la información almacenada en la *Base de Datos Geográfica del Gobierno de La Rioja*, IDErioja dispone de unos ficheros de configuración predeterminados denominados *"Consultas"*, en los que se almacenan las referencias de los datos que se quieren representar, su simbología y atributos, así como su orden de presentación (opción: [consulta](opciones/consulta)).

Si se prefiere utilizar la API para la representación de datos geográficos propios o de terceros en lugar de los almacenados en IDErioja, la API dispone de funciones que permiten añadir al mapa datos de otras procedencias.

<br />

### Código de ejemplo
<br />

Se presenta a continuación el código del fichero html para la representación de la consulta de IDErioja  *"4d4b792f6469754163366644435862454d7a314e47773d3d"*, correspondiente a las *Estaciones de Medición de La Rioja*.

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración API IDErioja</title>
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
      "consulta": "4d4b792f6469754163366644435862454d7a314e47773d3d"
      // Estaciones de medición
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```
<br />

#### Salida gráfica
<br />

[Resultado visual](https://iderioja.github.io/doc_api_iderioja/ejemplo_configuracion_api_iderioja).

![Ejemplo de configuración](/img/configuracion_salida_grafica.jpg "Ejemplo de configuración")
<br />

### Opciones
<br />

Opción | Tipo | Valor def. | Descripción
:--- | :--- | :---: | :---
[ajuste_elementos](opciones/ajuste_elementos)|[0,1]|1|Permite ajustar la extensión del mapa en base a los elementos del GeoJSON
[capa_geojson](opciones/capa_geojson)|array|(no)|Array de archivos *GeoJSON* con capas geográficas a visualizar.
[capa_gpx](opciones/capa_gpx)|array|(no)|Array de archivos *GPX* (GPS) con puntos, recorridos y rutas a visualizar.
[capa_kml](opciones/capa_kml)|array|(no)|Array de archivos *KML* con capas geográficas a visualizar.
[cluster_markers](opciones/cluster_markers)|[0,1]|0|Simbolización agrupada y dinámica de elementos puntuales y símbolos
[colabora](/opciones/colabora)|[0,1]|0|Añade un control que permite capturar la coordenada del mapa
[consulta](/opciones/consulta)|texto|(no)|Especifica la *consulta de IDErioja* que se quiere utilizar
[control_zoom](opciones/control_zoom)|[0,1]|1|Establece la visualización o no del control de zoom.
[escala](/opciones/escala)|[0,1]|0|Muestra una barra con la *escala gráfica* del mapa
[estilo_hover](/opciones/estilo_hover)|parámetros|()|Define la simbolización que se emplea para resaltar un elemento
[fondo_base](/opciones/fondo_base)|texto|"iderioja-base"|Especifica el *fondo cartográfico* o mapa base que se utilizará en el visor
[ids](/opciones/ids)|array|(no)|Elementos a representar entre los incluidos en una consulta IDErioja
[init_lat](/opciones/init_lat-init_lng)|coordenada|40.4169473|*Latitud* del centrado inicial del mapa en coordenadas geográficas
[init_lng](/opciones/init_lat-init_lng)|coordenada|-3.7035285|*Longitud* del centrado inicial del mapa en coordenadas geográficas
[leyenda](/opciones/leyenda)|[0,1]|0|Muestra un *botón leyenda* de las capas utilizadas en una *consulta* IDErioja
[localizacion](opciones/localizacion)|[0,1]|0|Ofrece un botón que muestra la localización geográfica del dispositivo
[minimapa](opciones/minimapa)|[0,1]|0|Muestra un *mapa guía* en la parte inferior derecha del mapa principal
[panel_info](opciones/panel_info)|[0,1]|0|Habilita la utilización del panel lateral de información
[popup](opciones/popup)|[0,1,2]|1|Define cómo se visualizan los atributos de un elemento seleccionado
[selector_capas](/opciones/selector_capas)|[0,1,2,3]|0|Configura la oferta y apariencia del *selector de capas*
[tag_mapa](/opciones/consulta)|div|"map"|Establece el nombre del <*div*> en el que incrustará el mapa
[zoom_inicial](/opciones/zoom_inicial)|[0-19]|10|Nivel de *zoom* inicial con el que se representará el mapa
<br />

### Métodos
<br />

Método|Descripción
:---|:---
[abreModal](/metodos/metodos/#abremodal)|Abre un *iFrame* centrado en la patalla, por encima del mapa.
[captura_zoom](/metodos/metodos/#captura_zoom)|Inserta el valor del zoom actual en el ID del elemento de DOM que se indique.
[carga_capa_geojson](/metodos/metodos/#carga_capa_geojson)|Carga una capa en formato GeoJSON.
[carga_capa_gpx](/metodos/metodos/#carga_capa_gpx)|Carga una capa en formato GPX.
[carga_capa_kml](/metodos/metodos/#carga_capa_kml)|Carga una capa en formato KML.
[carga_capa_notiled_wms](/metodos/metodos/#carga_capa_notiled_wms)|Carga una capa WMTS sin tilear.
[carga_fondo](/metodos/metodos/#carga_fondo)|Carga un fondo en formato tile server.
[carga_fondo_wmts](/metodos/metodos/#carga_fondo_wmts)|Carga un fondo en formato WMTS.
[crea_boton](/metodos/metodos/#crea_boton)|Añade un botón dentro del mapa que al pulsarlo ejecuta la función que se le pasa como parámetro.
[eliminaCapasBaseMapa](/metodos/metodos/#eliminacapasbasemapa)|Suprime las capas del tipo *BaseLayer*.
[eliminaCapasMapa](/metodos/metodos/#eliminacapasmapa)|Suprime todas las capas del mapa.
[ir_a_coordenada](/metodos/metodos/#ir_a_coordenada)|Sitúa el mapa en la coordenada y el nivel de zoom especificados.
[ir_a_elemento](/metodos/metodos/#ir_a_elemento)|Sitúa el mapa en el ID del elemento indicado con el nivel de zoom seleccionado.<br />Se abren las propiedades del elemento.
[ir_a_todo](/metodos/metodos/#ir_a_todo)|Centra el mapa para que todos los elementos aparezcan, ajustando también el nivel de zoom.
[setFiltroBD](/metodos/metodos/#setfiltrobd)|Muestra en el mapa solamente los elementos que coincidan con los campos que queremos filtrar.
[setFiltroIDS](/metodos/metodos/#setfiltroids)|Muestra en el mapa solamente los elementos que coincidan con los identificadores (IDs) seleccionados.
[setFiltroProp](/metodos/metodos/#setfiltroprop)|Muestra en el mapa solamente los elementos que coincidan con el valor del atributo seleccionado.
[unsetFiltroBD](/metodos/metodos/#unsetfiltrobd)|Elimina los filtros creados con `setfiltroBD`.
[unsetFiltroIDs](/metodos/metodos/#unsetfiltroids)|Elimina los filtros creados con `setfiltroIDs`.
[unsetFiltroProp](/metodos/metodos/#unsetfiltroprop)|Elimina los filtros creados con `setfiltroProp`.
[zoom_mas](/metodos/metodos/#zoom_mas)|Acerca el mapa.
[zoom_menos](/metodos/metodos/#zoom_menos)|Aleja el mapa.
<br />

### Componentes
<br />

La API js IDErioja incorpora funcionalidades de las siguientes librerías y plugins de software abierto:

 - [Leafletjs v 0.7.7](http://leafletjs.com/): Librería JavaScript *open-source* para la visualización de mapas interactivos.
 - [leaflet-control-geocoder](https://github.com/perliedman/leaflet-control-geocoder): Geocodificación directa e inversa de direcciones.
 - [Leaflet.EasyButton](https://github.com/CliffCloud/Leaflet.EasyButton): Ofrece la posiblidad de añadir botones en Leaflet de una forma sencilla.
 - [Leaflet.fullscreen](https://github.com/Leaflet/Leaflet.fullscreen): Plugin para mostrar la visualización a pantalla completa (HTML5).
 - [Leaflet.geojsonCSS](https://github.com/albburtsev/Leaflet.geojsonCSS): Permite aprovechar para la simbolización las posibilidades del formato [Geojson CSS](http://wiki.openstreetmap.org/wiki/Geojson_CSS).
 - [leaflet-locatecontrol](https://github.com/domoritz/leaflet-locatecontrol): Añade controles para la geolocalización del dispositivo.
 - [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster): Permite añadir a Leafletjs funcionalidades para el clustering dinámico de símbolos.
 - [Leaflet-MiniMap](https://github.com/Norkart/Leaflet-MiniMap): Control que permite añadir en una esquina un minimapa con funciones *pan* y *zoom*.
 - [Leaflet.NonTiledLayer](https://github.com/ptv-logistics/Leaflet.NonTiledLayer): Soporta peticiones a servicios WMS no tileados.
 - [leaflet-omnivore](https://github.com/mapbox/leaflet-omnivore): Soporte de formatos CSV, GPX, KML, WKT, TopoJSON y Encoded Polylines. Incluye [*corslite*](https://github.com/mapbox/corslite).
 - [leaflet-sidebar](https://github.com/Turbo87/leaflet-sidebar): Añade la posibilidad de configurar persianas laterales adaptativas (*responsives*).
 - [leaflet.TileLayer.WMTS](https://github.com/mylen/leaflet.TileLayer.WMTS): Incorpora la posibilidad de añadir capas a partir de servicios WMTS.


Otras librerías JavaScript integradas:

 - [pace](https://github.com/HubSpot/pace): Línea de carga automática.
 - [reqwest](https://github.com/ded/reqwest): Ajax.
 - [ondomready](https://github.com/tubalmartin/ondomready): Inicialización del código cuando el DOM está preparado.
 