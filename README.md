

## Municipios y Departamentos de Colombia API

Se recomienda nombrar el campo de Municipios como: `cbc:CityName`

Nota: Cuando se trate de Departamentos y Municipios en Colombia se realiza una validación
cruzada entre el código del departamento y el código del municipio. Por lo que los valores Código Departamento y Código Municipio guardan la relación expresada en la siguiente tabla  [base natural de Datos Abiertos Colombia.](https://www.datos.gov.co/Mapas-Nacionales/DIVIPOLA-C-digos-municipios/gdxc-w37w).


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
## Validar una cedula de Colombia con REgeX

```
^((\d{8})|(\d{10})|(\d{11})|(\d{6}-\d{5}))?$
```

### Reconocimiento de datos en Cédula
Una cédula cuenta  con una serie de números en la parte inferior del código de barras, estos números y letras revelan información importante de éste documento. Algunos de ellos son:

#### Primer letra Código barras 
- **P** Primera vez que se genero el documento.
- **A** Duplicado del documento ó Renovación del mismo.
- **R** Existe una rectificación en el documento de identidad.

#### Escaneo de los datos de la cedula mediante el código de Barras que esta en formato [PDF417](https://es.wikipedia.org/wiki/PDF417)

Aquí estan los datos como
- Numero de Documento
- Nombres Apellidos
- Fecha de Nacimiento


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

Tratamiento de los datos en la consulta con Google Query 
**Municipiso de Antioquia en Mayusculas**
```
=Query({IMPORTRANGE("134dUP-ejxdPXaZi1dkYjMdhqdk5gmuQIdSecgdHrXiw";"Data!C:E")};"SELECT upper(Col3) WHERE Col1 = 'Antioquia' ";0)
```

## Uso como JSON


https://spreadsheets.google.com/feeds/cells/134dUP-ejxdPXaZi1dkYjMdhqdk5gmuQIdSecgdHrXiw/1/public/full?alt=json




## Entidades prestadoras de Salud 

Respuesta 1278 solicitudes de ciudadanos https://www.datos.gov.co/Participaci-n-ciudadana/Datos-Abiertos-Solicitados-Por-Los-Ciudadanos-En-L/9it7-3gvu/data no tiene end point y solo esta en excel.


## Procuraduria General de la nación
La procuraduria tiene datos muy dispersos y poco accesibles, aquí algunos enlaces que proporcionan en su web:

**Directorio de dependencias**_(El mas completo de todos )_ : https://www.procuraduria.gov.co/portal/index.jsp?option=co.gov.pgn.portal.frontend.component.pagefactory.DependenciaComponentPageFactory

**directorio de Sedes Regionales y Provinciales**

https://www.procuraduria.gov.co/portal/sedes.page

tienen un con marcadores de Google y ademas tienen 2 hojas de google sheets con algunos datos tabulados aquí los enlaces a la hoja de google sheets que esta de manera publica(los datos se pueden consumir desde ahí directo y al parecer son dos hojas de el mismo libro de Google Sheets) 

PGN regionales y pronvinciales : 2. PROVINCIALES

https://docs.google.com/spreadsheets/u/1/d/e/2PACX-1vQsKL-Rcv6p79tuN-JrjXCuws89lAylITAbgYaQkTmvWNFyNzSlwqN6GowrJHqHbsBia2PjeD98t01z/pubhtml/sheet?headers=false&gid=798715752

PGN regionales y pronvinciales : 1. REGIONALES

https://docs.google.com/spreadsheets/u/1/d/e/2PACX-1vQsKL-Rcv6p79tuN-JrjXCuws89lAylITAbgYaQkTmvWNFyNzSlwqN6GowrJHqHbsBia2PjeD98t01z/pubhtml?gid=1160064317&single=true&widget=true&headers=false

**

## Por Incluir
- Unir los datos acorde a la [Norma ISO 3166 COUNTRY CODES](https://www.iso.org/iso-3166-country-codes.html) para poder utilizar estos datos en plataformas que utilzan este estandar como guia.
- Se plantea la mejora mediante la inclusión de un Script de Google que facilite el acceso a estos datos por ejemplo con la librería [librería](https://github.com/bradjasper/ImportJSON).
- Se plantea la publicación de una mezcla entre el dataset recuperado y la nueva publicación del dataSet en Datos Abiertos 
Colombia

- En google forms las listas desplegables para los municipios superarian las 1000 opciones lo que cargaria mucho un formulario de estos con ese tipo de opción, por lo tanto se propone la posibilidad de crear un formato que indique a las personas la forma de escribir un municipio ó departamento y validar cada uno de ellos con una expresión de REGEX de esta manera se descargaria la cantidad de posibilidades pero se valida en cierta medida que el municipio exista (por ejemplo no existen municipios con 'X' ó con tildes en la á etc) así se podria validar esto de una manera un poco limitada pero factible, un escenario posible de creacion y publicación es [https://regex101.com/](https://regex101.com/)
*
- Para las personas jurídicas el NIT será asignado mediante un proceso con la DIAN y la cámara de comercio correspondiente, está compuesto por 9 dígitos y un dígito de verificación adicional.(Se realizara un END-Point para validarlo con Regex y la formula que comprueba el numero de verificación)

