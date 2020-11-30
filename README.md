## Municipios y Departamentos de Colombia API

Esta es una documentación para el uso de una API para el manejo de datos sobre la divición politica de colombia.

Esta basada en replicas de la [base natural de Datos Abiertos Colombia.](https://www.datos.gov.co/Mapas-Nacionales/DIVIPOLA-C-digos-municipios/gdxc-w37w)

## [PROBLEMAS] 

Debido a la eliminación de la base de datos natural se hizo necesario crear una copia de la misma actualzada hasta el día 17/Ago/2020 disponible aqui https://docs.google.com/spreadsheets/d/e/2PACX-1vTnS7bhQ1WJ-h8JIAaxpcuqe002fHNTgJX5iSnGtQ5Inm0pIu6OTv70OMgqwEO7DZH9pkaQcO_ZFpMf/pub?output=csv.

## New Publish Dataset in  [Datos.gov.co](https://www.datos.gov.co/Mapas-Nacionales/DIVIPOLA-C-digos-municipios/gdxc-w37w)



**Formato:** El formato admitido para entregar estos datos es cvs y json, esta definido en la URL.

## Manejo directo sobre Datos Abiertos Colombia

Usted puede consultar directamente estos datos sobre la plataforma de datos abiertos de la siguiente manera, tenga en cuenta que **necesitara una API Key para poder obtener el conjunto de datos completo**.


Consulta de todos los registros:

```
 https://www.datos.gov.co/resource/gdxc-w37w.csv?$limit=5000&$$app_token=YOURAPIKEY
```

Filtro de Municipios unicamente:

```
https://www.datos.gov.co/resource/gdxc-w37w.json?$select=dpto
```

Obtener departamento de un municipio especificado:

```
https://www.datos.gov.co/resource/xdk5-pm3f.csv?$select=dpto&nom_mpio=Florencia
```


## Replica en Google Sheets

La replica a continuación se usa para importar los datos que sean necesarios en hojas de calculo de Google y se permitira su
uso mientras esta no genera cargos monetarios a su creador

https://docs.google.com/spreadsheets/d/134dUP-ejxdPXaZi1dkYjMdhqdk5gmuQIdSecgdHrXiw/edit?usp=sharing

## Estructura de la replica

| region                          | c_digo_dane_del_departamento | departamento | c_digo_dane_del_municipio | municipio |
|---------------------------------|------------------------------|--------------|---------------------------|-----------|
| Región Eje Cafetero - Antioquia |                            5 | Antioquia    |                      5001 | Medellín  |
| Región Eje Cafetero - Antioquia |                            5 | Antioquia    |                      5002 | Abejorral |


### Uso:
En hojas de calculo de Google Importe los rangos de la siguiente manera :
```
=IMPORTRANGE("https://docs.google.com/spreadsheets/d/134dUP-ejxdPXaZi1dkYjMdhqdk5gmuQIdSecgdHrXiw/edit?usp=sharing";"Data!D1:F1124")
```

## Uso como JSON


https://spreadsheets.google.com/feeds/cells/134dUP-ejxdPXaZi1dkYjMdhqdk5gmuQIdSecgdHrXiw/1/public/full?alt=json




## Por Incluir
- Unir los datos acorde a la [Norma ISO 3166 COUNTRY CODES](https://www.iso.org/iso-3166-country-codes.html) para poder utilizar estos datos en plataformas que utilzan este estandar como guia.
- Se plantea la mejora mediante la inclusión de un Script de Google que facilite el acceso a estos datos por ejemplo con la librería [librería](https://github.com/bradjasper/ImportJSON).

