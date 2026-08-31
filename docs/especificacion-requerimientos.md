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

Durante el desarrollo del taller se utilizaron y se utilizarán las siguientes ramas:

- `main`: rama principal del repositorio, utilizada para mantener la versión estable del trabajo.
- `develop`: rama de integración, donde se van uniendo los requerimientos antes de llevarlos a `main`.
- `feature/rf01/registro-tutoria`: rama utilizada para desarrollar y documentar el RF-01, correspondiente al registro de tutorías.
- `feature/rf02/consultar-tutorias`: rama utilizada para desarrollar y documentar el RF-02, correspondiente a la consulta de tutorías.
- `feature/rf03/...`: rama que deberá utilizarse para desarrollar y documentar el RF-03.
- `feature/rf04/...`: rama que deberá utilizarse para desarrollar y documentar el RF-04.

Cada requerimiento debe trabajarse en una rama `feature` independiente, creada a partir de `develop`, para evitar modificar directamente las ramas principales.

### Proceso de integración

Cada requerimiento se trabaja inicialmente en una rama `feature` independiente creada a partir de `develop`. Los cambios realizados en cada requerimiento se guardaron mediante commits y luego se subieron al repositorio remoto con `git push`.

Para integrar los cambios se utilizaron  Pull Requests desde las ramas `feature` hacia `develop`.

El flujo general esperado es el siguiente:

`feature/rf01/registro-tutoria` → `develop`

`feature/rf02/consultar-tutorias` → `develop`

`feature/rf03/inscripcion-tutoria` → `develop`

`feature/rf04/cancelacion-inscripcion` → `develop`

En el caso del RF-01 y RF-02, los cambios fueron trabajados en sus respectivas ramas y posteriormente integrados a `develop` mediante Pull Requests.

Para RF-03 y RF-04 se siguió el mismo procedimiento: cada integrante creo su rama a partir de la versión más reciente de `develop`, se realizó únicamente los cambios correspondientes a su requerimiento, se hizo los commit, se subio  la rama al repositorio remoto y se creo un Pull Request hacia `develop`.

Durante el proceso se detectó que algunos cambios habían sido integrados de forma anticipada en `main`. Para corregir el flujo de trabajo, esos cambios fueron revertidos en `main`, manteniendo los requerimientos correctamente integrados en `develop`.

Antes de comenzar RF-03 y RF-04, los integrantes encargados actualizaron `develop` para trabajar sobre la versión más reciente y evitar sobrescribir los cambios de RF-01 y RF-02.

Cuando los cuatro requerimientos estuvieron terminados, revisados e integrados correctamente en `develop`, se integraron final mediante un Pull Request desde `develop` hacia `main`.

El flujo general del proyecto quedo de la siguiente manera:

`feature/rf01` → `develop`

`feature/rf02` → `develop`

`feature/rf03` → `develop`

`feature/rf04` → `develop`

`develop` → `main`

### Conflictos encontrados

Se presentó un conflicto al actualizar la rama `feature/rf02/consultar-tutorias` con los cambios que ya se encontraban en `develop`.

El conflicto ocurrió en el archivo de especificación de requerimientos porque tanto RF-01 como RF-02 habían realizado modificaciones sobre el mismo archivo. Git mostró las marcas de conflicto `<<<<<<<`, `=======` y `>>>>>>>`.

Para resolverlo, se revisó manualmente el contenido de ambas versiones y se conservaron los cambios correspondientes a los dos requerimientos. Se mantuvo la información del RF-01 que ya estaba integrada en `develop` y se agregó correctamente la información del RF-02. También se completó información faltante detectada durante la revisión.

Después de eliminar las marcas de conflicto, el archivo se agregó nuevamente con `git add`, se realizó un commit de resolución y se subió la rama actualizada. Finalmente, se creó el Pull Request de `feature/rf02/consultar-tutorias` hacia `develop` y los cambios fueron integrados correctamente.

Para evitar conflictos similares durante el desarrollo de RF-03 y RF-04, cada integrante  actualizo su rama con los últimos cambios de `develop` antes de comenzar o antes de realizar el Pull Request. Si se presentaban nuevos conflictos, estos debian resolverse manualmente conservando la información de todos los requerimientos y evitando sobrescribir el trabajo realizado por otros integrantes.

De esta forma, cada requerimiento puede desarrollarse de manera independiente y posteriormente integrarse de forma controlada en `develop` antes de realizar la integración final hacia `main`.

