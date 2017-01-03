# tag_mapa
</br>

La opción `tag_mapa` establece el nombre del `<div>` de la página *html* en el que se incrustará el mapa.

Por defecto el *id* utilizado es `"map"`.

</br>
###Código de ejemplo
</br>

El siguiente ejemplo dirige la salida a un `<div>` denominado `"mi_mapa"`.

```html
<!DOCTYPE html>
<html>
  <head lang="es">
    <meta charset="UTF-8">
    <title>Ejemplo de configuración tag_mapa</title>
    <style>
      body, html{
        height: 100%;
        border: 0;
        padding: 0;
        margin: 0;
      }
      #mi_mapa{
        width: 100%;
        height: 100%;
      }
    </style>
  </head>
  <body>
    <div id="mi_mapa"></div>
  </body>
  <script>
    var iderioja_config = {
      "consulta": "5872436f7150784e763446756d79744a756c6e4c4a513d3d",
      "tag_mapa": "mi_mapa"
    }
  </script>
  <script src="https://apigeo.larioja.org/v1/iderioja.js"></script>
</html>
```

</br>
####Salida gráfica
</br>

Ejemplo de uso de la opción *tag_mapa=mi_mapa*.  [(visualizar ejemplo)](https://iderioja.github.io/doc_api_iderioja/ejemplo_opcion_tag_mapa)

![Ejemplo de uso de la opción tag_mapa](/img/opciones_tag_mapa_salida_grafica.jpg "Ejemplo de uso de la opción tag_mapa")
