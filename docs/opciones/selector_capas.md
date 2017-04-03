# selector_capas
<br />

La opción `selector_capas` configura la oferta y apariencia del *selector de capas*, admitiendo las siguientes posibilidades:

- **`0`**- No muestra ningún selector de capas (opción por defecto).
- **`1`**- Activa el tipo de selector de capas que ofrece de forma estándar la librería javascript *[Leaflet](http://leafletjs.com/)*.  
Presenta los fondos cartográficos que se ofertan por defecto y las capas incluidas en la *consulta IDErioja*.
- **`2`**- Muestra un *"miniselector"* con dos opciones: **Mapa** (Mapa Base IDErioja) y **Satélite** (Ortofoto IDErioja).  *(1)
- **`3`**- El selector de capas muestra la capa definida en la opción `fondo_base`

<br />Notas:

(1) El valor `2` (miniselector), invalida cualquier otro fondo cartográfico elegido mediante la opción [fondo_base](opciones/fondo_base). Aunque el fondo elegido mediante esta opción pueda aparecer en una primera instancia, desaparecerá al pulsar cualquiera de los botones del miniselector, para no volver a mostrarse.

<br />

### Código de ejemplo
<br />

El ejemplo que se muestra configura el selector de capas con la opción "*miniselector*" (selector_capas=2).

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración selector_capas</title>
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
      "selector_capas": 2
	}
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

<br />

#### Salida gráfica
<br />

Ejemplo de uso de la opción *selector_capas=1* (selector estándar Leaflet) [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_selector_capas_1)

![Ejemplo de uso de la opción selector_capas=1](/img/opciones_selector_capas_salida_grafica_1.jpg "Ejemplo de uso de la opción selector_capas = 1")
<br />

Ejemplo de uso de la opción *selector_capas=2* (miniselector IDErioja) [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_selector_capas_2)

![Ejemplo de uso de la opción selector_capas=2](/img/opciones_selector_capas_salida_grafica_2.jpg "Ejemplo de uso de la opción selector_capas = 2")
<br />

Ejemplo de uso de la opción *selector_capas=3* (miniselector IDErioja) [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_selector_capas_3)

![Ejemplo de uso de la opción selector_capas=3](/img/opciones_selector_capas_salida_grafica_3.jpg "Ejemplo de uso de la opción selector_capas = 3")
