# Especificación de Requerimientos

## 1. Descripción del sistema

## 2. Integrantes

- Nombre: Saray Jimenez
- Nombre: Isabella Gordillo
- Nombre: Natalia Giraldo
- Nombre: Leyder 

## 3. Requerimientos Funcionales

### RF-01 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


### RF-02 - [Consultar tutorías]

#### Resumen

Los estudiantes podran hacer consulta de la tutorias disponibles ingresando la fecha deseada y opcionalmente la materia, mostrando los detalles de cada tutoria correspondientes a los datos ingresados o un mensaje si no hay coincidencias.

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|
| Fecha| LocalDate | formato deseado: [ DD/MM/AAAA ] corresponde al dia en que el estudiante quiere ver la tutoria  |
|Asignatura | String | Materia que se quiere estudiar|

#### Reglas o condiciones
- Que la fecha ingresada sea valida
- Que haya cupos disponibles en las tutorias

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|
| id | String | identificador de la tutoria|
| tema | String | tema de la tutoria|
| nombreDelProfesor | String | profesor que va dar la tutoria |
| fecha | LocalDate | fecha de la tutoria |
|hora | String | hora de la tutoria |
cantidadDeCupos| int | Capacidad max. de estudiantes en la tutoria |

#### Resultado esperado
-	Si existen tutorías que correspondan con la búsqueda, el sistema deberá desplegar la información, si no es el caso el estudiante recibiría un mensaje informándolo.

### RF-03 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


### RF-04 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


## 4. Gestión de Versiones

### Ramas utilizadas

### Proceso de integración

### Conflictos encontrados
