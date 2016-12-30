# init_lat, init_lng
</br>

Las opciones `init_lat` e `init_lng` definen la posición del centrado inicial del mapa en coordenadas geográficas (*latitud*,*longitud*), en ese orden.

Si no se especifican, el mapa se centrará por defecto en las coordenadas (*42.33012*,*-2.38403*) correspondientes a La Rioja.

Las coordenadas se deberán expresar en *grados* y *decimales de grado*, indicando su cuadrante geográfico mediante el uso de los signos: Norte (**+**), Sur (**-**), Este (**+**) y Oeste (**-**).

</br>
###Código de ejemplo
</br>

El siguiente ejemplo centra la presentación inicial del mapa en la ciudad de Madrid (40.4169473, -3.7035285).

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <title>Ejemplo de configuración init_lat,init_lng</title>
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
      "init_lat": 40.4169473, "init_lng": -3.7035285
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

</br>
####Salida gráfica
</br>

Ejemplo de uso de la opción  *init_lat = 40.4169473*,  *init_lng = -3.7035285*. [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_init_lat-init_lng)

![Ejemplo de uso de la opción init,lat-init_lng](/img/opciones_init_lat_init_lng_salida_grafica.jpg "Ejemplo de uso de la opción init_lat,init_lng")
