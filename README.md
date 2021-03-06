# Tarea1
## Integrantes
* Johanna Gomez 3101443
* Viviana Diaz 3101437
* Camilo Lopez 3101436

## Expectativas
La expectativa que tenemos con este curso es poder entender de forma práctica el proceso y herramientas para publicar cartografía vía web

## Mapas
### Mapa de pendientes
Utilizamos el DEM de la CAR de 10 m. de resolución, con el software ArcGis y la herramienta Slope que se encuentra en el Arctoolbox Spatial Analyst. Se clasificaron las pendientes en porcentaje, de acuerdo a la metodología IGAC.
0-3%
3-7%
7-12%
12-25%
25-50%
50-75%
mayor 75%


[Mapa de Pendientes](https://github.com/Vicajo/Tarea_1/blob/master/DR-07%20MAPA%20DE%20PENDIENTES.pdf)

### Mapa de Elevación

Se clasifican los valores de altura del DEM en una rampa de colores donde se pueden diferenciar los cambios de elevación. La fuente utilizada es un MODELO DE ELEVACIÓN DIGITAL de 10 m. de resolución de la jurisdicción CAR Cundinamarca.

[Mapa de Elevación](https://github.com/Vicajo/Tarea_1/blob/master/DR-08%20MODELO%20DIGITAL%20DE%20ELEVACI%C3%93N.pdf)

# Preguntas
## ¿Cuál es el problema a tratar? 

Identificar la pendiente del terreno de la zona de estudio, teniendo en cuenta el cambio de la elevación en función de los ejes X, Y. A partir de la clasificación de pendientes dada por el IGAC, con el fin de usar este como insumo para la modelacion de la amenaza por remocion en masa dode las pendientes son un factor a analizar.

![maxresdefault](https://user-images.githubusercontent.com/50974099/58396594-f7670000-8012-11e9-9bbb-72bd5dc42b47.jpg)
Fuente: MAGNUM T&C S.A.C. - Obtención de Pendientes y Calculo de Cotas

## ¿Por qué un mapa ayuda a resolverlo?

Partiendo del concepto de mapa como una representación gráfica del territorio, en este caso es una herramienta que registra una de sus características físicas como lo es la pendiente del territorio correspondiente al municipio de Chocontá, siendo esta una variable de tipo continuo que tiene un componente espacial la representación gráfica es óptima para su registro y posterior uso, de manera que permita una caracterización del territorio con mejor precisión y una cobertura completa del espacio objetivo. Tambien nos permite utilizarlo en la elavoracion de estudios de amenaza ya que las pendientes son un factor clave a la hora de modelar las amenazas.

## Descripción del mapa temático (Variable seleccionada, utilidad) 

Teniendo en cuenta que el mapa temático realizado corresponde a un mapa de pendientes, el cual tiene como objetivo principal mostrar el grado de inclinación del terreno de manera que a mayor valor, mayor es el grado de inclinación y puede ser expresada en términos de porcentaje.

La pendiente es una de las características base del territorio para su análisis y toma de decisiones, pues  su repercusión en la planeación y el manejo del territorio es muy alta, teniendo influencia en factores como  con la infiltración, la escorrentía superficial, la humedad del suelo, la contribución del agua subterránea a la escorrentía, la estabilidad, áreas de amenaza, entre muchos otros.


## Descripción de los métodos de clasificación seleccionados. ¿Cuál es mejor para la variable seleccionada? ¿Por qué? 

Inicialmente la clasificación se realizó por porcentajes teniendo en cuenta que es la más utilizada para expresar la variable de pendientes puesto que esta establecida su caracterización de acuerdo con los rangos utilizados de la siguiente manera: 


![Pendientes](https://user-images.githubusercontent.com/50974099/58396084-bd94fa00-8010-11e9-8831-c1debe59c231.png)

Fuente: Jairo Alonso Figueredo Rodriguez - CLASIFICACION DE PENDIENTES Y SU CARACTERISTICAS

## Listado de fuentes de datos seleccionadas (proveedor, enlace para descarga, descripción, procesamiento realizado) 

* DEM (Modelo de elevación digital del terreno) resolución espacial 10 metros, entregado por la CAR Cundinamarca
* Limite del municipio de Chocontá

## Descripción breve del procedimiento utilizado (pluggins, extensiones, procesos, transformaciones de datos, etc) 

Para la generación del mapa de pendientes se siguieron los siguientes pasos:

* Desde ArcMap se carga el Modelo Digital de Elevación - DEM.

* Se valida el sistema de referencia en el que se encuentra la información.

* Se comprueba que los valores del DEM correspondan  a la altitud (Cota).

* Para crear la capa de pendientes se hace desde ArcToolbox > Spatial Analyst > Surface > Slope, se define el extent con el polígono del municipio de Chocontá y se establece en porcentaje con el elemento de entrada el DEM anteriormente cargado en ArcMap.

* Se reclasifica la capa resultante en ArcToolbox > Spatial Analyst Tools > Reclass > Reclassify en la clasificación se seleccionan 7 rangos en porcentaje: 0-3, 3-7, 7-12, 12-25, 25-50, 50-75 y más de 75.

* Se trasforma a polígono en ArcToolbox > Conversion Tools > From Raster > Raster to Polygon.

* Se remueven las capas sin uso que en este caso corresponde al DEM original y se adicionan las capas de cartografía base correspondientes al municipio de Chocontá: Drenaje sencillo, Drenaje doble, vías límite veredal, límite municipal, perímetro urbano y predial rural.

* En la tabla de atributos y se agrega un campo Add Field (tipo double), se calcula el área con clic derecho sobre el nombre del nuevo campo > Calculate Geometry.

* Para sumar las superficies conforme a los rangos de pendientes establecidos, en el campo se accede a Gridcode > Summarize > area_ha (campo de superficie) > Sum.

* Al abrir la tabla generada con Sum se muestran los valores totales por rangos.

* Se genera el formato de salida gráfica con todos sus elementos: Leyenda, Convenciones, perímetro cartográfico, fuente básica cartográfica, localización general, título, escala y grilla.

## Ventajas / desventajas / dificultades / diferencias encontradas al utilizar QGIS y ArcGis para el desarrollo del ejercicio

Se realizó la salida cartográfica mediante los software ArcGis y QGis, y se obtuvieron los siguientes resultados:

* La simbología para representar el Norte, en ArcGis es muy amplia, mientras que en QGis esta limitada 
* El manejo de la símbología es muy parecido entre los dos software, teniendo en cuenta que el flujo de trabajo es el mismo, así los menús sean algo diferentes.
* La rampa de colores en QGis es más limitada con respecto a ArcGis, sin embargo, el primero presenta la opción de crear y editar la rampa de colores a gusto personal.
* La visualización de las capas es más rápida en QGis.
* Gracias al trabajo comunitario en QGis se puede mejorar la funcionalidad del mismo, como sucede con el uso de imágenes de referencia, que tiene muchas más opciones, con respecto a ArcGis, gracias al plugging Quick map services.
* En general, se puede afirmar que las dos opciones de software (ArcGis, QGis), para generar salidas cartográficas son bastante buenas y el uso depende exclusivamente del gusto personal del Profesional encargado.

[Mapa de Pendientes QGIS](https://github.com/Vicajo/Tarea_1/blob/master/Mapa%20de%20Pendientes_QGIS.pdf)



