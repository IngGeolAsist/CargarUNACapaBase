# Cargar UNA Capa Base
## Ya hemos visto, cómo crear un lienzo para nuestros mapas, pero en el solamente aparece un recuadro gris. 
### En este tutorial te mostraré como cargar UNA capa base a tu mapa, para de una vez por todas comiences el diseño de tu primer mapa en la web
Para empezar, ingresamos a la página: https://leaflet-extras.github.io/leaflet-providers/preview/  y visualizaremos la siguiente pantalla

En el costado derecho, podremos observar una columna en la que podemos navegar para encontrar todas las previsualizaciones al dar click. 

### Si te das cuenta, cada vez que cambiamos de capa base, se actualiza la información que está en el recuadro de la esquina superior izquierda.


Este recuadro nos brinda los siguientes datos
  1.	Fuente: Nos indica a quién pertenecen los datos del mapa base que elegimos 
  2.	Fragmento de Código: Son las líneas de código que hay que incluir para visualizar el mapa base en cuestión.

### A continuación, copiamos las línea de código correspondiente y pegamos dentro de la etiqueta scripten el archivo html de nuestro proyecto, justo despues de la ultima variable declarada en el tutorial anterior.

``` html
	var topo = L.tileLayer('https://{s}.tile.opentopomap.org/{z}/{x}/{y}.png', {
	maxZoom: 17,
	attribution: 'Map data: &copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors, <a href="http://viewfinderpanoramas.org">SRTM</a> | Map style: &copy; <a href="https://opentopomap.org">OpenTopoMap</a> (<a href="https://creativecommons.org/licenses/by-sa/3.0/">CC-BY-SA</a>)'
	}); 
	topo.addTo(map);
```
### Analicemos los elementos de estas líneas de código:
Se declara una nueva variable y se le asigna un nombre que podamos identificar, en este caso es por defecto.
  - **L.titleLayer** es un comando de leaflet para incluir capas base al mapa. 
  - **Attribution** En él, se incluyen datos acerca del propietario de los datos, aparece en la esquina inferior derecha del mapa y aunque se puede prescindir de esta información, es importante mostrar al usuario del mapa la fuente de nuestros datos
- **Osm.addRoMap** Como ya vimos es el comando que nos permite agregar la variable previamente declarada al mapa.

### Puedes agregar cuantas capas desees, al finalizar tu codigo debería parecerse a lo siguiente.

``` html
<html>
<head>
	<meta charset="utf-8">
	<title>Mapa E14C17_2</title>
	<link rel="stylesheet" href="https://unpkg.com/leaflet@1.6.0/dist/leaflet.css"
  integrity="sha512-xwE/Az9zrjBIphAcBb3F6JVqxf46+CDLwfLMHloNu6KEQCAWi6HcDUbeOfBIptF7tcCzusKFjFw2yuvEpDL9wQ=="
  crossorigin=""/>
	<script src="https://unpkg.com/leaflet@1.6.0/dist/leaflet.js"
  integrity="sha512-gZwIG9x3wUXg2hdXF6+rVkLF/0Vi9U8D2Ntg4Ga5I5BZpVkVxlJWbSQtXPSiUTtC0TjtGOmxa1AJPuV0CPthew=="
  crossorigin=""></script>
	<style>
	#mapDIV {
	height: 100%;
	width: 100%;
	border: solid 2px black;
	}
	</style>
</head>
<body>
<div id="mapDIV"></div>

 <script>	
 var map = L.map('mapDIV', {
		center:[20.83748 , -99.71396],
		zoom:12
	});
	
	var scale = L.control.scale({
		'imperial':false
	});
	scale.addTo(map);
	
	var topo = L.tileLayer('https://{s}.tile.opentopomap.org/{z}/{x}/{y}.png', {
	maxZoom: 17,
	attribution: 'Map data: &copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors, <a href="http://viewfinderpanoramas.org">SRTM</a> | Map style: &copy; <a href="https://opentopomap.org">OpenTopoMap</a> (<a href="https://creativecommons.org/licenses/by-sa/3.0/">CC-BY-SA</a>)'
	}); 
	topo.addTo(map);
		
 </script>
</body>
</html>
```

### Ejecutamos en el navegador de nuestra preferencia, y por fin podremos ver un mapa en el lienzo que estábamos trabajando.

