# Cargar datos power BI (Transformar datos)

## Renombrar columna

```C#
= Table.RenameColumns(dbo_DimDocumentType,{{"DocumentTypeID", "IdTipoDocumento"}, {"Name", "TipoDeDocumento"}})
```
## Conversion de datos
### Cambiar columna  a date (Fecha)
```C#
= Table.TransformColumnTypes(dbo_DimPeriod,{{"PeriodID", type date}})
```

