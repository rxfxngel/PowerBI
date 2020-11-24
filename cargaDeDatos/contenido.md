# Cargar datos power BI (Transformar datos) :green_book: :green_book: :green_book:

## Renombrar columna

```C#
= Table.RenameColumns(dbo_DimDocumentType,{{"DocumentTypeID", "IdTipoDocumento"}, {"Name", "TipoDeDocumento"}})
```
## Conversion de datos
### Cambiar columna  a date (Fecha)
```C#
= Table.TransformColumnTypes(dbo_DimPeriod,{{"PeriodID", type date}})
```
## Filtrar datos

### Funciones

Date.AddDays (Sumar y Restar fechas)

Sintaxis
```C#
Date.AddDays ( dateTime como cualquiera, numberOfDays como número)
```
Ejemplo: Restar 180 dias(3 meses) a la fecha actual
```C#
= Table.SelectRows(#"Changed Type", each [PeriodID] > Date.AddDays(DateTime.Date(DateTime.LocalNow()),-180))
```
