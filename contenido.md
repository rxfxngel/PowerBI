# BUSINESS INTELLIGENCE :maple_leaf::maple_leaf::maple_leaf: POWER BI

## DATAMART
Un Data Mart es un almacén de datos orientado a un área específica, como por ejemplo,  Ventas, Recursos Humanos u otros sectores en una organización. Por ello, también se le conoce como una base de información departamental. 

## DATAMART DE COMPRAS
> Esquema de base de datos:
<img src="img/cap1.png" width="50%">

## TIPO DE TABLA

|TABLA|TIPO|
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

##  MODELO DIMENSIONAL
El modelado dimensional se basa en HECHOS (Facts) y es una alternativa al modelado
relacional. Sus principales ventajas son:
- Enfocado en el negocio y sus actividades
- Permite búsquedas a gran velocidad
## Dimension articulo
La dimensión artículo nos brinda información acerca de los artículos más comprados por la empresa se agregó los campos de categoría subcategoría y unidad para hacer una mejor clasificación y ver el comportamiento de los datos.
|dimArticulo|	
|---|
|idArticulo **PK IDENTITY** :key:|
|Id_articulo|
|nombreArticulo|
|categoria|
|subcategoria|
|unidad|
## Dimension proveedor
La dimensión proveedor en el proceso de compras  nos brinda datos de nuestros proveedores agregando el campo distrito para poder clasificarlos, es muy útil esta dimensión para ver el comportamiento de los proveedores .
|dimProveedor|		
|---|
|idProveedor **PK IDENTITY** :key:|	
|Id_Proveedor|
|nomProveedor|
|distritoProveedor|	
## Dimension tipo venta
La dimensión tipo venta nos brinda información  si las compras de la empresa a los proveedores  fueron realizadas al CONTADO, CREDITO, A 15 DIAS, A 30 DIAS, A 21 DIAS o PROFORMA
|dimTipoVenta|
|---|
|idTipoVenta **PK IDENTITY** :key:|
|id_tipoVenta|
|tve_nombre|
## Dimensión tiempo
La dimensión tiempo es muy fundamental pues nos permite saber el comportamiento de los datos por cada periodo de tiempo, y lo podemos clasificar por año, trimestre, mes, quincena.
|dimtiempo|
|---|
|idTiempo **PK IDENTITY** :key:|
|fecha|
|anio|
|nmes|
|nombremes|
|ndia|
|nombredia|
|trimestre|
|quincena|


## Metricas
- Métrica subtotal: La métrica subtotal es el importe esto quiere decir el monto antes de aplicar IGV (impuestos) o descuentos
- Métrica cantidad: La métrica cantidad representa la cantidad de cada compra  por cada transacción. 

|factCompras|
|---|
|idProveedor|
|idArticulo|
|idTipoVenta|
|idTiempo|
|cantidad|
|subtotal|

## Creacion de base de datos multidimencional

```sql
create table  dimArticulo(
idArticulo int identity primary key not null ,
Id_articulo char(10) NOT NULL,
nombreArticulo varchar(60) ,
categoria varchar(50),
subcategoria varchar(50),
unidad varchar(30)
)
```


