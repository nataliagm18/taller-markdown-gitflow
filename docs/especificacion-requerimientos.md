# Especificación de Requerimientos

## 1. Descripción del sistema

El sistema permite a los profesores crear y gestionar tutorías académicas, registrando información como el tema, fecha, hora, código del profesor y cantidad máxima de estudiantes. Los estudiantes podrán consultar las tutorías disponibles utilizando una fecha y, opcionalmente, un tema o asignatura de interés. También podrán inscribirse en las tutorías siempre que estén activos en la Universidad, existan cupos disponibles y no estén inscritos previamente. Finalmente, los estudiantes podrán cancelar su inscripción cuando exista una inscripción previa y la tutoría todavía no haya comenzado. El sistema realizará las validaciones correspondientes y mostrará mensajes informando el resultado de cada operación.

## 2. Integrantes

- Nombre: Saray Jimenez
- Nombre: Isabella Gordillo
- Nombre: Natalia Giraldo
- Nombre:Leider Rodriguez Caicedo

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

### RF-03 - [Inscribir estudiante a tutoría]

#### Resumen

El sistema debe permitir que un estudiante se inscriba a una tutoría disponible, proporcionando su código estudiantil y el identificador de la tutoría a la que desea inscribirse.

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|
| codigoEstudiante | String | Código que identifica al estudiante que solicita la inscripción. |
| idTutoria | String | Identificador único de la tutoría a la que el estudiante desea inscribirse. |

#### Reglas o condiciones

- El estudiante debe encontrarse activo en la Universidad.
- La tutoría debe existir.
- La tutoría debe tener al menos un cupo disponible.
- El estudiante no puede encontrarse previamente inscrito en la misma tutoría.

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|
| mensajeConfirmacion | String | Mensaje que informa al estudiante que la inscripción fue realizada correctamente. |
| mensajeError | String | Mensaje que informa al estudiante el motivo por el cual la inscripción no pudo realizarse. |

#### Resultado esperado

La inscripción del estudiante queda registrada y la cantidad de cupos disponibles de la tutoría se actualiza (disminuye en 1).


### RF-04 - Cancelar inscripción a tutoría

#### Resumen

Permitir que un estudiante que ya se encuentre inscrito pueda cancelar su participación en una tutoría utilizando su código estudiantil y el identificador de la tutoría.

#### Entradas

| Entrada | Tipo de dato | Descripción |
|---|---|---|
| codigoEstudiantil | String | Código único que identifica al estudiante. |
| identificadorTutoria | String | Identificador único de la tutoría a cancelar. |

#### Reglas o condiciones
- La inscripción previa del estudiante en la tutoría debe existir.
- La tutoría seleccionada aún no ha comenzado.

#### Salidas

| Salida | Tipo de dato | Descripción |
|---|---|---|
| mensaje | String | Mensaje de confirmación de éxito o indicando el motivo por el cual no fue posible realizar la operación. |

#### Resultado esperado
El sistema elimina la inscripción existente, libera nuevamente el cupo correspondiente de la tutoría e informa al estudiante que la operación fue exitosa. Si alguna condición no se cumple, el sistema muestra el mensaje de error correspondiente sin modificar las inscripciones.

## 4. Gestión de Versiones

### Ramas utilizadas

### Proceso de integración

### Conflictos encontrados

