# Ejercicio Integrador Final - Capacitación Data Process - Quales Group

#

## Capacitación data process de Quales Group 

![image](https://user-images.githubusercontent.com/103937102/235311000-95134c7f-36af-4a1e-87d4-1bea05819799.png)

Como parte de la capacitación que realicé, de manera gratuita, en la reconocida y excelente empresa Quales Group, para la entrega de la certificación, se debía realizar un ejercicio integrador final para la aprobación del mismo. Este trabajo fué muy motivante y un lindo desafío para mi labor profesional en el mundo de los datos.
Comencemos por conocer un concepto importante.

##

## ¿QUE ES ETL? ![image](https://user-images.githubusercontent.com/103937102/235486856-be162000-79d3-4a22-91a8-397db0ad47c8.png)

Extracción, Transformación y Carga (ETL), por sus siglas en inglés Extract, Transform and Load, es el proceso consistente en combinar datos de diferentes orígenes un gran repositorio central llamado almacenamiento de datos. ETL utiliza un conjunto de reglas comerciales para limpiar y organizar datos en bruto y prepararlos para el almacenamiento, el análisis de datos y el machine learning (ML). Puede abordar necesidades de inteligencia empresarial específicas mediante análisis de datos (como la predicción del resultado de decisiones empresariales, la generación de informes y paneles, la reducción de la ineficacia operativa y más).

La extracción, transformación y carga (ETL) funciona moviendo datos del sistema de origen al sistema de destino a intervalos periódicos, automatizando el procedimiento. El proceso ETL funciona en tres pasos:

1- Extracción de los datos relevantes de la base de datos de origen.

2- Transformación de los datos para que sean más adecuados para el análisis.

3- Carga de los datos en la base de datos de destino.

##

## OBJETIVOS 

![image](https://user-images.githubusercontent.com/103937102/235486988-3feefd19-210e-4946-a1c8-39dfc6992bbc.png)

El objetivo del trabajo será el de realizar una implementación de una Solución de Datos.
Desde la detección y recolección de datos, relevamiento de requerimientos y construcción del Datawarehouse (DW), desarrollo de ETLs (Stored Procedure)y validaciones de datos.

##

## ORIGENES DE DATOS

La fuente de información es un único conjunto de datos, que simula ser una base de datos con distintas tablas donde se encuentra la información de un sistema de gestión de ventas.
Contiene las siguientes tablas:

***Productos**

***Categorías**

***Clientes**

***Pais**

***Sucursal**

***Vendedor**

***Ventas**

##

## REGLAS DE NEGOCIO

Se identificaron las siguientes reglas de negocio:

Ventas:

➔ Un producto puede estar en más de una venta.

➔ En una venta un producto puede tener más de una cantidad vendida.

➔ Una Sucursal puede contener más de una venta.

➔ Un Producto corresponde a una Categoría.

➔ Un vendedor puede estar en más de una venta.

➔ El nivel de detalle de ventas es diario.

Deberán crear el modelo de datos que justifique estas reglas de negocio.

Para comprender mejor lo solicitado por la empresa, se recomienda leer la totalidad del PDF siguiente https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/Data%20Process%20I%20-%20Ejercicio%20Integrador%20-%20Definiciones%20y%20especificaciones.docx.pdf


##
## ENTREGABLES

Para sintetizar, se debía cargar desde el excel a una base de datos llamada DW_COMERCIAL toda la información en un DataWarehouse, pasando cada tabla (dimensión y hecho) por una serie de transformaciones para llegar a lo solicitado, de esta manera cada una debía contenerse en primer lugar en tablas staging para luego a través de Stored Procedure ir pasando la información a otra Intermedia y luego a las finales, especificando las transofrmaciones requeridas en cada caso.
De esta manera, en las tablas finales llega la información limpia, sin duplicados ni errores y cuando haya cargas incrementales para realizar el ETL, se hará de manera automática, teniendo en cuenta las mismas consideraciones de las cargas iniciales y otras para que no se vuelvan a cargar registros que ya han sido cargados anteriormente.

Los entregables del proyecto son:

**1. Diagrama de Modelo de Datos lógico:** 

  a. Imagen en PDF o PPT o Link si utilizan alguna herramienta de diagramas. El entregable deberá tener el siguiente nombre: NOMBRE_APELLIDO_DW_COMERCIAL_MODELO
  
**2. Script con el modelo físico de datos:**

  a. Script de Creación de Tablas con nombre NOMBRE_APELLIDO_DW_COMERCIAL_CREATE_TABLES.sql
  
  b. Script con el Alter de las tablas con nombre NOMBRE_APELLIDO_DW_COMERCIAL_ALTER_TABLES.sql
  
  c. Script de Inserts Iniciales de las tablas de Dimensiones con el nombre NOMBRE_APELLIDO_DW_COMERCIAL_INSERTS.sql
  
  d. Script con los Stored Procedures de las cargas de Tablas Intermedias y Dimensiones con el nombre 
 NOMBRE_APELLIDO_DW_COMERCIAL_STORED_PROCEDURES.sql
  
**3. Documento con Validaciones (Word donde se describa las validaciones que realizaron. Sepuede agregar imágenes de consultas, queries, imágenes del tablero e imágenes de las validaciones sobre el excel). El word/ doc debera tener el siguiente nombre:**

NOMBRE_APELLIDO_DW_COMERCIAL_VALIDACIONES.docx y el script con las validaciones con el nombre: NOMBRE_APELLIDO_DW_COMERCIAL_SCRIPT_VALIDACIONES.sql

**4. Documento con Supuestos (Word que explique los supuestos que tomaron en cuenta a la hora de cargar el DW y/o el desarrollo del tablero) en caso de que aplique. El word/ doc debera tener el siguiente nombre:**
NOMBRE_APELLIDO_DW_COMERCIAL_SUPUESTOS.docx

**Nota: Como la carga inicial del excel al DW fue realizada mediante la herramienta de task de SQL SERVER y para que quien quisiera pueda correr absolutamente todo el proyecto desde los archivos .sql, realicé un archivo llamado INSERTS_INICIALES (https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/INSERTS_INICIALES.sql) , donde a través de la función concatenar de Excel pude realizar un scripts usando "INSERT INTO" para poder cargar manualmente cada tabla.**

Cabe destacar, que de esta manera hay un límite de 1.000 registros y como la tabla de ventas tiene 11.992 registros, se debió realizar 12 veces el script, pero ejecutando todo este archivo mencionado, se deberían cargar todas las tablas sin ningún problema.

Para ello, se recomienda primero ejecutar el archivo CREATE_TABLES (https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/CREATE_TABLES.sql), luego https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/INSERTS_INICIALES.sql, para tener toda la carga de las tablas staging listas del DW.

##

## ESPECIFICACIONES FINALES

Los archivos incluidos en este repositorio y lo que contiene cada uno, son:

* Un archivo (https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/CREATE_TABLES.sql) con los scripts de todas las tablas creadas.
* Archivo https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/INSERTS_INICIALES.sql con los scripts para las cargas iniciales a las tablas staging (todas realizadas manualmente con la sentencia INSERT INTO) para que no se dificulte la carga ni se deba realizarla a través de los tasks.
* Archivo (https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/INSERTS.sql) que lo realicé como para que pueda tener información (xq se solicitó), ya que los sp los consideraba. Pero puse todos los execute de los procedimientos de cada tabla y entendí que la consigna era insertar en estos, los datos a las tablas dimensión y fact. Por lo tanto, comprendí que era eso lo esperado. De esta manera los datos a las tablas finales fueron llevados a través de los Insert y los sp son para crear nuevos o actualizarlos.
* Archivo https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/STORED_PROCEDURES.sql que contiene cada uno de los sp (para carga y actualización de tablas).
* Otro https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/ALTER_TABLES.sql que yo no había utilizado, pero al igual que con los inserts, para cumplir con la consigna, lo que hice fue crear la tabla Fact Ventas sin las FOREIGN KEY (FK) y agregar las relaciones en un Alter para cada una de las tablas de dimensión.
* Un script con todas las validaciones realizadas llamado https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/SCRIPT_VALIDACIONES.sql.
* Dos archivos WORD, como solicitaban las consignas. Uno de supuestos y otro de validaciones, donde se aclara ciertos caminos tomados o interpretaciones realizadas sobre el proyecto y su ejecución.
https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/SUPUESTOS.docx y https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/VALIDACIONES.docx
* Por último, el modelo de negocio, en formato imagen, creado con draw.io https://github.com/AxelM1989/EjercicioIntegradorFinalQualesGroup/blob/main/MODELO.drawio.png.

##
## TAREAS COMPLEMENTARIAS.

Si bien el trabajo era hasta aquí, realicé tareas extras de visualización. 
En primer lugar, un dashboard bastante simple y sencillo, con las métricas solicitadas por el trabajo final y los filtros por cada una de las tablas para poder mostrar la información de manera más visual y concreta.
Dejaré a continuación una imagen de muestra del tablero sin filtros y luego con filtro. A su vez podrán ver el archivo original en formato pbi en este mismo repositorio --- > https://github.com/AxelM1989/QG_DataProcess/blob/main/DW_COMERCIAL_DASHBOARD.pbix

POWER BI SIN FILTROS

![image](https://github.com/AxelM1989/QG_DataProcess/assets/103937102/c4122518-0d3c-400f-b897-f0ddfac39321)

POWER BI CON FILTROS

![image](https://github.com/AxelM1989/QG_DataProcess/assets/103937102/14af7334-8af6-42b2-8608-4fb35e80cc1e)

Por último, a través de la librería de Power Bi Client en python, logré visualizar el reporte en un archivo notebook y es una biblioteca que no conocía y que puede ser útil para trabajar desde python. Se pueden visualizar reportes publicados de Power Bi o incluso generar nuevos directamente desde aquí.
A continuación, un ejemplo del mismo dashboard con y sin filtro para observar como se visualizan. También se puede acceder al archivo notebook (.ipynb) desde aquí ---> https://github.com/AxelM1989/QG_DataProcess/blob/main/PowerBI_DW_COMERCIAL.ipynb

NOTEBOOK SIN FILTROS

![image](https://github.com/AxelM1989/QG_DataProcess/assets/103937102/04f8ea0b-40b7-46a5-a018-67c826ab0129)

NOTEBOOK CON FILTROS

![image](https://github.com/AxelM1989/QG_DataProcess/assets/103937102/81b736fb-1fd6-4fa7-b95e-80c9237cb09a)


Considerando que probablemente al archivo notebook no puedan visualizarlo sin permisos, mostraré una imagen del archivo de notebook completo en tamaño pequeño.

![image](https://github.com/AxelM1989/QG_DataProcess/assets/103937102/21431023-fe8e-45a2-8b00-edf5c5b6bc5f)

##

## STACK TECNOLOGICO

![image](https://user-images.githubusercontent.com/103937102/235487225-735ddfae-23c9-44f8-8a9b-620554e5b4a6.png)

![image](https://user-images.githubusercontent.com/103937102/235487191-c16daedc-f141-42ba-9e9f-f071da0771ad.png)

![image](https://user-images.githubusercontent.com/103937102/235487342-2c396a0d-b01d-409e-ba47-7b7dfa76cf55.png)

![image](https://user-images.githubusercontent.com/103937102/235487284-6f29ae72-b0b6-4ef8-8b63-9479bb262486.png)

![image](https://user-images.githubusercontent.com/103937102/235487387-2d716c3a-5c3a-4531-8340-15afb6a8cf86.png)



