# Git Conventions

En este documento detallo las convenciones de Git y el flujo de trabajo usual en un equipo de desarrollo de software.

- [Naming Conventions](#naming-conventions)
  * [Branches](#branches)
  * [Commits](#commits)
- [Workflow](#workflow)
  * [Development](#development)

## Naming Conventions

Convenciones en la nomenclatura para ramas y mensajes de commit.

### Branches

Para las ramas, se puede usar la estructura `<token>/<short-descriptive-name>`.

Los tokens que se pueden utilizar son:

- `feature`: nuevas funcionalidades que serán incluidas en el proyecto. (i.e. visualización de cursos).
- `fix`/`hotfix`/`patch`: corrección de un bug esperado o inesperado (i.e. links rotos).
- `refactor`: mejoras/reescritura de features existentes, no agrega un cambio grande a lo que actualmente tiene. 
  (i.e. cambiar estados locales usando stateless components conectados a Redux).
- `test`: agrega tests a un feature existente que no cuenta con los mismos (i.e. unit testing del componente de login).
- `chore`: mejoras en temas de administración/mantenimiento del proyecto (i.e. actualización de dependencias).
- `docs`: creación/actualización de documentación (i.e.: guía de configuración del proyecto).

Para los nombres que siguen al token, se puede utilizar en número de task (En Jira, Trello, etc.) y, si es necesario, palabras cortas que describan en lo que se está trabajando. 

#### Ejemplos (Suponiendo que el número de la task es 180)

- feature/180-project-roadmap
- fix/180-student-routing
- refactor/180-settings-components
- test/180-controllers
- chore/180-deps-upgrade
- docs/180-setup

### Commits

Para los commits, se puede seguir la siguiente estructura:  `<type> <subject>`.

El `type` son tokens cortos similares a los de las ramas, pueden ser: 

- `Add` (Feature)
- `Fix` (Bug fix)
- `Doc` (Documentation)
- `Style` (Rormatting, missing semi colons, …)
- `Refactor`(When the input and output data remain the same )
- `Test` (When adding missing tests).

El `subject`:
  * En inglés, usar modo imperativo, present tense: **change** en vez de _changed_ o _changes_.
  * La primera letra en mayúsculas (para seguir el estándar por defecto que usa Git al hacer un `merge` o `rebase`).
  * Intentar acortar el mensaje a 50 caracteres, no debe pasar de 78. 
  * No poner punto al final
  
> Nota: Los mensajes de commits no describen lo que alguien del equipo ha trabajado, por el contrario debe describir lo que se cambia en el proyecto.
Ejemplo:

- ~~_I_~~ "Added Github field in profile settings" ✗
- ~~_Someone_~~ "Adds Github field in profile settings" ✗
- ~~_This commit will_~~ "Add Github field to profile settings" ✔

## Workflow

Convenciones al trabajar colaborativamente.

### Development

Para la etapa del desarrollo dentro del proyecto, se recomienda trabajar cada feature, task, fix, etc., en una rama específica, siguiendo la convención de [nomenclatura de ramas](#branches).

Se parte desde Develop, creando una nueva rama y se vuelve a develop creando un PR para que sea revisada y una vez esta sea aprobada se procede a mergear con develop.
