# Métodos
<br />

La llamada a los *métodos* o *funciones* se debe realizar después de que el mapa esté cargado en el DOM, por lo que se utilizará la función *"iderioja_ready"* o funciones similares de jQuery (DOMReady).

También pueden ser invocadas desde un evento *'click'* de un botón.

<br />

### abreModal
<br />

`abreModal(<url>,<ancho>,<alto>)`

<br />Abre un *iFrame* centrado en la patalla, por encima del mapa.

<br />

### captura_zoom
<br />

`captura_zoom (<id del DOM>)`

<br />Inserta el valor del zoom actual en el ID del elemento de DOM que se indique.

```
iderioja_ready(function () {
  mapa_iderioja.captura_zoom("nivel_zoom");
});
```

<br />

### carga_capa_geojson
<br />

`carga_capa_geojson`

<br />Carga una capa en formato GeoJSON.

```
mapa_iderioja.carga_capa_geojson(
  'Departamentos de Francia',
  'https://raw.githubusercontent.com/gregoiredavid/france-geojson/master/departements.geojson'
);
```

<br />

### carga_capa_gpx
<br />

`carga_capa_gpx`

<br />Carga una capa en formato GPX.

```
mapa_iderioja.carga_capa_kml(
  'Punto GPS',
  'https://raw.githubusercontent.com/doronkatz/GFXLocations/78c430a92124bd9b52f4fc5a60f0185849aea1fd/darwin.gpx',
  null,
  {iconUrl: 'http://www.thenationalgroup.net/App_Themes/ELPISCMS/images/map-marker_icon.png',
   iconSize: [24, 24], // tamaño del icono
   iconAnchor: [12, 24], // punto geográfico respecto al xy del icono
   popupAnchor: [0, -24] // punto de anclaje de la burbuja de datos
  }
);
```

<br />

### carga_capa_kml
<br />

`carga_capa_kml`

<br />Carga una capa en formato KML.

```
mapa_iderioja.carga_capa_kml(
  'Trip to Spain and Morocco',
  'https://raw.githubusercontent.com/CafeGIS/gvSIG2_0/81376f304645d040ee34e98d57b4f745e0293d05/libGPE-KML/testdata/SpainMorocco.kml'
);
```

<br />

### carga_capa_notiled_wms
<br />

`carga_capa_notiled_wms`

<br />Carga una capa WMTS sin tilear.

```
mapa_iderioja.carga_capa_notiled_wms(
  'D.G. Catastro',
  'http://ovc.catastro.meh.es/Cartografia/WMS/ServidorWMS.aspx',
  {minZoom: 0,
   maxZoom: 19,
   opacity: 1.0,
   layers: 'Catastro',
   styles: 'default',
   version: '1.1.1.',
   format: 'image/png',
   transparente: true,
   attribution: 'Dirección General del Catastro'
  },
  false
);
```

<br />

### carga_fondo
<br />

`carga_fondo`

<br />Carga un fondo en formato tile server.

```
mapa_iderioja.carga_fondo(
  'MapQuest',
  'http://otile{s}.mqcdn.com/tiles/1.0.0/map/{z}/{x}/{y}.jpg',
  {maxZoom: 19,
   subdomains: '1234',
   tms: false,
   attribution: 'Map data © <a href="http://www.mapquest.com">MapQuest</a>'
  }
);
```

<br />

### carga_fondo_wmts
<br />

`carga_fondo_wmts`

<br />Carga un fondo en formato WMTS.

<br />

### crea_boton
<br />

`crea_boton (<contenido>, <función>, <parámetros>)`

<br />Añade un botón dentro del mapa que al pulsarlo ejecuta la función que se le pasa como parámetro.

Tiene 3 parámetros:

* Contenido del botón (string):
    * Código HTML
    * Icono de *FontAwesome*
* Función Javascript (string)
* Parámetros de la funcion (array)

```
iderioja_ready(function () {
  mapa_iderioja.crea_boton('<span id="nivel_zoom"></span>', "alert", ["hola!!!"]);
});
```

<br />

### eliminaCapasBaseMapa
<br />

`eliminaCapasBaseMapa`

<br />Suprime las capas del tipo *BaseLayer*.

<br />

### eliminaCapasMapa
<br />

`eliminaCapasMapa`

<br />Suprime todas las capas del mapa.

<br />

### ir_a_coordenada
<br />

`ir_a_coordenada (<lon>, <lat>, <zoom>)`

<br />Sitúa el mapa en la coordenada y el nivel de zoom especificados.

<br />

### ir_a_elemento
<br />

`ir_a_elemento (<id del elemento>, <zoom>)`

<br />Sitúa el mapa en el ID del elemento indicado con el nivel de zoom seleccionado.

Se abren las propiedades del elemento.

<br />

### ir_a_todo
<br />

`ir_a_todo ()`

<br />Centra el mapa para que todos los elementos aparezcan, ajustando también el nivel de zoom.

<br />

### setFiltroBD
<br />

```
setFiltroBD([{
  "campo": "<nombre de campo encriptado>",
  "valor": "<valor>"
}])
```

<br />Muestra en el mapa solamente los elementos que coincidan con los campos que queremos filtrar.

Los datos no tienen por qué existir en el GeoJSON, deben existir en la Base de Datos IDErioja.

<br />

### setFiltroIDS
<br />

`setFiltroIDS([<id1>,<id2>,<id3>,...])`

<br />Muestra en el mapa solamente los elementos que coincidan con los identificadores (IDs) seleccionados.

Los datos tienen que existir en el GeoJSON cargado en el mapa.

<br />

### setFiltroProp
<br />

```
setFiltroProp({
  "<atributo>": "<valor>",
  "<atributo>": "<valor>"
})
```


<br />Muestra en el mapa solamente los elementos que coincidan con el valor del atributo seleccionado.

Los datos tienen que existir en el GeoJSON cargado en el mapa.

<br />

### unsetFiltroBD
<br />

`unsetFiltroBD()`

<br />Elimina los filtros creados con `setfiltroBD`.

<br />

### unsetFiltroIDs
<br />

`unsetFiltroIDs()`

<br />Elimina los filtros creados con `setfiltroIDs`.

<br />

### unsetFiltroProp
<br />

`unsetFiltroProp()`

<br />Elimina los filtros creados con `setfiltroProp`.

<br />

### zoom_mas
<br />

`zoom_mas()`

<br />Acerca el mapa.

<br />

### zoom_menos
<br />

`zoom_menos()`

<br />Aleja el mapa.

<br />

## Ejemplo
<br />

```html
<!DOCTYPE html>
<html>
<head lang="es">
  <meta charset="UTF-8">
  <title>Test API IDErioja</title>
  <style>
    body, html{
      height: 100%;
      border: 0;
      padding: 0;
      margin: 0;
      background-color: #e7e7e7;
      overflow: hidden;
    }
    #map{
      top: 10px;
      width: 100%;
      height: 500px;
      border: 1px solid cornflowerblue;
    }
    #botones{
      margin-top: 10px;
      width: 750px;
      display: block;
      margin-left: auto;
      margin-right: auto;
      border: 0px solid red;
    }
  </style>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css">
  </head>
  <body>
    <div id="botones">
      <button type="button" id="ir_log">Ir a Logroño</button>
      <button type="button" id="z_mas">Zoom +</button>
      <button type="button" id="z_menos">Zoom -</button>
      <button type="button" id="ir_a_id">Ir al ID 4057</button>
      <button type="button" id="filtrar_municipio">Filtrar los de Logroño</button>
      <button type="button" id="quitar_filtros">Eliminar filtros</button>
      <button type="button" id="z_todo">Zoom elementos</button>
    </div>
    <div id="map">
    </div>
    </body>
    <script src="https://apigeo.larioja.org/iderioja.js"></script>
    <script src="https://code.jquery.com/jquery-1.11.3.min.js"></script>
    <script>
      var iderioja_config = {
        "consulta": "5872436f7150784e763446756d79744a756c6e4c4a513d3d" // Arboles
      };
      $( document ).ready(function() {
        /* BOTONES EXTERNOS */
        $("#ir_log").click(function() {
          mapa_iderioja.ir_a_coordenada(42.46121, -2.44205, 13);
        });
        $("#z_mas").click(function() {
          mapa_iderioja.zoom_mas();
        });
        $("#z_menos").click(function() {
          mapa_iderioja.zoom_menos();
        });
        $("#ir_a_id").click(function() {
          mapa_iderioja.ir_a_elemento(4057, 15);
        });
        $("#filtrar_municipio").click(function() {
          mapa_iderioja.filtro_propiedad("Municipio", "Logroño");
        });
        $("#quitar_filtros").click(function() {
          mapa_iderioja.filtro_eliminar();
        }); // Ajustar a los elementos del mapa
        $("#z_todo").click(function() {
        mapa_iderioja.ir_a_todo();
        });
        mapa_iderioja.crea_boton('<span id="nivel_zoom"></span>', "alert", ["test!"]);
        mapa_iderioja.captura_zoom("nivel_zoom");
        mapa_iderioja.crea_boton('fa fa-check-circle', "filtro_propiedad", ["Municipio", "Logroño"]);
        mapa_iderioja.crea_boton('fa fa-eraser', "filtro_eliminar", []);
        mapa_iderioja.crea_boton('fa fa-crosshairs', "ir_a_todo", []);
        mapa_iderioja.crea_boton('fa fa-bell-o', "abreModal", ["http://www.larioja.org", 800, 700]); });
        $("#filtrar_municipio").prop('disabled', true);
          var interValRef = setInterval("checkState();",100);
          function checkState(){
            if(document.readyState == 'complete'){
              clearInterval(interValRef);
              $("#filtrar_municipio").prop('disabled', false);
            }
	      }
    </script>
</html>
```
