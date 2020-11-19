# :maple_leaf::maple_leaf::maple_leaf: POWER BI

## DATAMART
Un Data Mart es un almacén de datos orientado a un área específica, como por ejemplo,  Ventas, Recursos Humanos u otros sectores en una organización. Por ello, también se le conoce como una base de información departamental. 

### DATAMART DE COMPRAS
> Esquema de base de datos:
<img src="img/cap1.png">

|TABLAS||
|---|---|
|ARTICULO|	MAESTRO :blue_book:|
|SUBLINEA|	MAESTRO :blue_book:|
|LINEA|	MAESTRO :blue_book:|
|UNIDAD|	MAESTRO :blue_book:|
|TIPOVENTA|	MAESTRO :blue_book:|
|COMPRA|	TRANSACCIONAL :chart_with_upwards_trend:|
|PROVEEDOR|	MAESTRO :blue_book:|
|DISTRITO|	MAESTRO :blue_book:|
|DETALLECOMPRA|	TRANSACCIONAL :chart_with_upwards_trend:|

###  MODELO DIMENSIONAL
El modelado dimensional se basa en HECHOS (Facts) y es una alternativa al modelado
relacional. Sus principales ventajas son:
- Enfocado en el negocio y sus actividades
- Permite búsquedas a gran velocidad
#### Dimension articulo
La dimensión artículo nos brinda información acerca de los artículos más comprados por la empresa se agregó los campos de categoría subcategoría y unidad para hacer una mejor clasificación y ver el comportamiento de los datos.
|dimArticulo|	
|---|
|idArticulo **PK IDENTITY** :key:|
|Id_articulo|
|nombreArticulo|
|categoria|
|subcategoria|
|unidad|
#### Dimension proveedor
La dimensión proveedor en el proceso de compras  nos brinda datos de nuestros proveedores agregando el campo distrito para poder clasificarlos, es muy útil esta dimensión para ver el comportamiento de los proveedores .
|dimProveedor|		
|---|
|idProveedor **PK IDENTITY** :key:|	
|Id_Proveedor|
|nomProveedor|
|distritoProveedor|	

