# panel_info
<br />

La opción `panel_info` habilita la utilización del panel lateral de información.

Su uso se puede personalizar mediante programación, o utilizarlo activando la opción [`popup`](opciones/popup) = `2` que muestra en el panel lateral todo el conjunto de atributos del elemento seleccionado.

Esta opción puede tomar los siguientes valores:

- **`0`**- Sin panel lateral de información (valor por defecto)
- **`1`**- Sustituye el bocadillo informativo por un panel lateral.

<br />*Notas*:

*(1)* La opción [`popup`](opciones/popup) = `2`, establece automáticamente el valor de la opción [`panel_info`](opciones/panel_info) = `1`, por lo que en este caso no es preciso configurarlo expresamente.

*(2)* Para mejorar la visualización del panel lateral de información en los dispositivos móviles, se aconseja configurar el parámetro `viewport` en el apartado cabecera (head) del fichero html de la siguiente manera:

    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />  

<br />

### Código de ejemplo
<br />

El siguiente ejemplo muestra el código necesario para habilitar la activación del panel lateral de información:

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Ejemplo de configuración panel_info</title>
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
      "panel_info": 1
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```
