# Especificación de Requerimientos

## 1. Descripción del sistema

## 2. Integrantes

- Nombre: Saray Jimenez
- Nombre: Isabella Gordillo
- Nombre: Natalia Giraldo
- Nombre: Leyder 

## 3. Requerimientos Funcionales

### RF-01 - [Registrar tutoría]

#### El sistema debe permitir que un profesor registre una nueva tutoría académica, proporcionando la información necesaria para que posteriormente pueda ser consultada por los estudiantes.


#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|--------------|---|
| codigoProfesor | String       | Código que identifica al profesor responsable de la tutoría. |
| tema | String       | Tema o contenido académico que será tratado durante la tutoría. |
| fecha | LocalDate    | Fecha en la que se realizará la tutoría. |
| horaInicio | String       | Hora de inicio programada para la tutoría. |
| cantidadMaximaEstudiantes | Int          | Número máximo de estudiantes que podrán participar en la tutoría. |

#### Reglas o condiciones
- La fecha de la tutoría no puede ser anterior a la fecha actual.
- La cantidad máxima de estudiantes debe ser mínimo 1 y máximo 10.
- El profesor debe proporcionar la información necesaria para registrar la tutoría.
- El sistema debe asignar un identificador único a cada tutoría creada.
#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|
| idTutoria | String | Identificador único asignado por el sistema a la tutoría registrada. |
| mensajeConfirmacion | String | Mensaje que informa al profesor que la tutoría fue creada correctamente. |

#### Resultado esperado
La tutoría quedo registrada correctamente. 
### RF-02 - [Nombre del requerimiento]

#### Resumen

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|

#### Reglas o condiciones

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|

#### Resultado esperado


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
