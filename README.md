Proyecto-1-Interfaces
=====================

Proyecto1 Interfaces
Contents
Introducción  3
Descripción del contenido al desplegar	3
Forma de compilación, ejecución y utilización de la aplicación	4
Ejemplos de datos a utilizar como pruebas	4
Limitaciones observadas y posibles mejoras	7



Introducción
El primer proyecto del curso diseño de interfaces para usuario consta en visualizar una librería javascript y 
una pantalla html en el ambiente gráfico Mozilla XUL. El proyecto consta de tres etapas diferentes. En esta primera 
etapa del proyecto se debe desarrollar una aplicación interactiva tipo editor/diseñado de contenido. 
En esta primera etapa del proyecto se debe de investigar sobre la librería escogida, además de realizar pruebas de 
diferentes librerías javascript que permitan el despliegue del contenido deseado, así como la implementación de la 
funcionalidad de carga y despliegue de la aplicación. 
Los temas a investigar en esta primera parte del proyecto son los siguientes: sus elementos principales, propiedades,
forma de visualización y características especiales. Para lograr realizar esta primera parte del proyecto se debió 
consultar páginas en la Web relacionadas con el tema del contenido o otra manera es la de descargar aplicaciones 
que procesen ese tipo de contenido y revisar su ayuda o tutoriales.

Posteriormente, se deben buscar diferentes implementaciones de librerías javascript que permitan presentar el contenido 
en forma correcta bajo el ambiente XUL. Para establecer cuál librería es la más adecuada es necesario realizar una 
investigación sobre diferentes implementaciones de uso gratuito. Los aspectos importantes a investigar son: si 
funciona dentro de XUL, si acepta contenido mediante parámetros, y sus diferentes opciones de configuración. 

En el momento que se haya podido cargar la librería adecuadamente en XUL se prosigue con la siguiente parte del
proyecto. Se debe de crear una aplicación XUL que permita cargar y desplegar contenido desde archivos en disco. 
El formato de estos archivos debe ser el definido por el tipo de contenido a presentar. Se debe de crear algún 
formato XML o JSON que permita almacenar dichos datos. En el caso de nuestra aplicación utilizará archivo XML 
para la carga de los archivos. 

La aplicación XUL debe de ser implementada utilizando el lenguaje CoffeeScipt junto con D3.js. Se debe crear un 
menú con un botón para poder cargar el archivo, en nuestro caso XML. 

Descripción del contenido al desplegar
El contenido que se debía de desplegar era el de un organigrama. Según wikipedia un organigrama se define como 
“la representación gráfica de la estructura de una empresa u organización. Representa las estructuras departamentales
y, en algunos casos, las personas que las dirigen, hacen un esquema sobre las relaciones jerárquicas y competenciales
de vigor en la organización”. Se desplegaran cuadros con el nombre y posición del miembro de la organización. 
Esos cuadros serán unidos por líneas. La jerarquica será representada por niveles, entre más alto este el nivel
más importante es la posición de la persona en la organización.  


Forma de compilación, ejecución y utilización de la aplicación
Manera de compilar el programa:
coffee -c nombreDelArchivoJavaScript.coffee

Manera de ejecución para el programa:
“C:\Program Files (x86)\Mozilla XULRunner\XULRunner” progra\applicacion.ini
 
En caso de no contar con XULRunner se puede ejecutar de la siguiente manera:
"C:\Program Files\Mozilla Firefox\firefox.exe" –app "C:\tutorial3\application.ini"

Ejemplos de datos a utilizar como pruebas
var org = Joint.dia.org;
	Joint.paper("world", 800, 650);
//////// Se crea los miembros del organigrama
	var bart = org.Member.create({
	  rect: { x: 305, y: 70, width: 140, height: 60 },
	  name: "Bart Simpson",
	  position: "CEO",
	  attrs: { fill: '#e4d8a4', stroke: 'gray' }
	});

	var homer = org.Member.create({
	  rect: { x: 90, y: 200, width: 150, height: 60 },
	  name: "Homer Simpson",
	  position: "VP Marketing"
	});

	var marge = org.Member.create({
	  rect: { x: 300, y: 200, width: 150, height: 60 },
	  name: "Marge Simpson",
	  position: "VP Sales"
	});

	var lisa = org.Member.create({
	  rect: { x: 500, y: 200, width: 150, height: 60 },
	  name: "Lisa Simpson",
	  position: "VP Production"
	});

	var maggie = org.Member.create({
	  rect: { x: 400, y: 350, width: 150, height: 60 },
	  name: "Maggie Simpson",
	  position: "Manager",
	  attrs: { fill: '#4192d3', stroke: 'black' }
	});

	var lenny = org.Member.create({
	  rect: { x: 190, y: 350, width: 150, height: 60 },
	  name: "Lenny Leonard",
	  position: "Manager",
	  attrs: { fill: '#4192d3', stroke: 'black' }
	});

	var carl = org.Member.create({
	  rect: { x: 190, y: 500, width: 150, height: 60 },
	  name: "Carl Carlson",
	  position: "Manager",
	  attrs: { fill: '#4192d3', stroke: 'black' }
	});

////////////// Se crean las líneas para relacionar a las personas creadas y así tener el organigrama.
	bart.joint(marge, org.arrow);
	homer.joint(marge, org.arrow);
	marge.joint(lisa, org.arrow);

	marge.joint(maggie, org.arrow).setVertices(['375 380']);
	homer.joint(lenny, org.arrow).setVertices(['165 380']);
	homer.joint(carl, org.arrow).setVertices(['165 530']);


Limitaciones observadas y posibles mejoras
La principal limitación encontrada a la realización del proyecto fue que las librerías encontradas que 
dibujaran el organigrama no funcionaban en XUL. A pesar de que se utilizo diferentes librerías del organigrama
y se intento con otro tema diferente no fue posible implementar esas librerías en XUL. Por lo cual continuar con 
el proyecto fue imposible dado que era necesario la utilización de XUL.


