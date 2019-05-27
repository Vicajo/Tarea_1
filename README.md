# Tarea1
## Integrantes
* Johanna Gomez 3101443
* Viviana Diaz 3101437
* Camilo Lopez 3101436

## Expectativas
La expectativa que tenemos con este curso es poder entender de forma práctica el proceso y herramientas para publicar cartografía vía web

## Mapas
## Mapa de pendientes
Utilizamos el DEM de la CAR de 10 m. de resolución, con el software ArcGis y la herramienta Slope que se encuentra en el Arctoolbox Spatial Analyst. Se clasificaron las pendientes en porcentaje, de acuerdo a la metodología IGAC.
0-3%
3-7%
7-12%
12-25%
25-50%
50-75%
mayor 75%


[Mapa de Pendientes](https://github.com/Vicajo/Tarea_1/blob/master/DR-07%20MAPA%20DE%20PENDIENTES.pdf)

## Mapa de Elevación

Se clasifican los valores de altura del DEM en una rampa de colores donde se pueden diferenciar los cambios de elevación. La fuente utilizada es un MODELO DE ELEVACIÓN DIGITAL de 10 m. de resolución de la jurisdicción CAR Cundinamarca.

[Mapa de Elevación](https://github.com/Vicajo/Tarea_1/blob/master/DR-08%20MODELO%20DIGITAL%20DE%20ELEVACI%C3%93N.pdf)

# Preguntas
## ¿Cuál es el problema a tratar? 


## ¿Por qué un mapa ayuda a resolverlo?

Partiendo del concepto de mapa como una representación gráfica del territorio, en este caso es una herramienta que registra una de sus características físicas como lo es la pendiente del territorio correspondiente al municipio de Chocontá, siendo esta una variable de tipo continuo que tiene un componente espacial la representación gráfica es óptima para su registro y posterior uso, de manera que permita una caracterización del territorio con mejor precisión y una cobertura completa del espacio objetivo. 

## Descripción del mapa temático (Variable seleccionada, utilidad) 
Teniendo en cuenta que el mapa temático realizado corresponde a un mapa de pendientes, el cual tiene como objetivo principal mostrar el grado de inclinación del terreno de manera que a mayor valor, mayor es el grado de inclinación y puede ser expresada en términos de porcentaje.
La pendiente es una de las características base del territorio para su análisis y toma de decisiones, 

## Descripción de los métodos de clasificación seleccionados. ¿Cuál es mejor para la variable seleccionada? ¿Por qué? 

Inicialmente la clasificación se realizó por porcentajes teniendo en cuenta que es la más utilizada para expresar la variable de pendientes puesto que esta establecida su caracterización de acuerdo con los rangos utilizados de la siguiente manera: 


![Pendientes](https://user-images.githubusercontent.com/50974099/58396084-bd94fa00-8010-11e9-8831-c1debe59c231.png)
Fuente: Jairo Alonso Figueredo Rodriguez - CLASIFICACION DE PENDIENTES Y SU CARACTERISTICAS
## Listado de fuentes de datos seleccionadas (proveedor, enlace para descarga, descripción, procesamiento realizado) 

## Descripción breve del procedimiento utilizado (pluggins, extensiones, procesos, transformaciones de datos, etc) 

Para la generación del mapa de pendientes se siguieron los siguientes pasos:

* Desde ArcMap se carga el Modelo Digital de Elevación - DEM.
* Se valida el sistema de referencia en el que se encuentra la información.
* Se comprueba que los valores del DEM correspondan  a la altitud (Cota).
* Para crear la capa de pendientes se hace desde ArcToolbox > Spatial Analyst > Slope.
* Se reclasifica la capa resultante en ArcToolbox > Spatial Analyst Tools > Reclass > Reclassify en la clasificación se seleccionan 7 rangos en porcentaje: 0-3, 3-7, 7-12, 12-25, 25-50, 50-75 y más de 75.
* Se trasforma a polígono en ArcToolbox > Conversion Tools > From Raster > Raster to Polygon.
* Se remueven las capas sin uso que en este caso corresponde al DEM original y se adicionan las capas de cartografía base correspondientes al municipio de Chocontá: Drenaje sencillo, Drenaje doble, vías límite veredal, límite municipal, perímetro urbano y predial rural.
* En la tabla de atributos y se agrega un campo Add Field (tipo double), se calcula el área con clic derecho sobre el nombre del nuevo campo > Calculate Geometry.
* Para sumar las superficies conforme a los rangos de pendientes establecidos, en el campo se accede a Gridcode > Summarize > area_ha (campo de superficie) > Sum.
* Al abrir la tabla generada con Sum se muestran los valores totales por rangos.
* Se genera el formato de salida gráfica con todos sus elementos: Leyenda, Convenciones, perímetro cartográfico, fuente básica cartográfica, localización general, título, escala y grilla.

## Ventajas / desventajas / dificultades / diferencias encontradas al utilizar QGIS y ArcGis para el desarrollo del ejercicio
