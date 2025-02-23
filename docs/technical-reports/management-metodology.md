---
id: management-metodology
title: Management Metodology
---

# Coding Standards

## Convenciones de Nomenclatura

- **Nombrado de las clases:** Se usa la convención **PascalCase** (mayúscula inicial y cada palabra separada con mayúscula).
- **Nombrado de las variables y los métodos:** Se usa la convención **CamelCase**.
- **Nombrado de las funciones:** Deben escribirse en mayúsculas y minúsculas comenzando con letras minúsculas.

## Formato del Código

- Una línea debe tener menos de **120 caracteres** de longitud.
- Evitar la **duplicación de código**.
- Evitar líneas en blanca innecesarias, solo deben usarse para **mejorar la legibilidad**.
- Evitar utilizar un **identificador para múltiples propósitos**.
- Evitar utilizar un estilo de codificación **difícil de entender**.
- La longitud de las funciones **no debe ser muy grande**.
- El código debe estar **comentado correctamente** para que sea fácil de entender.
- Evitar utilizar la declaración **GOTO**.

### Para la duplicación del código:

- Extraer **métodos y funciones reutilizables**.
- Aplicar en el backend los principios **SOLID** y en el frontend la **modularidad**.

## Rutas de la API

- **Sustantivos en plural** para representar los recursos.
- Se usa ``/{id}`` para un recurso concreto.
- Evitar el uso de **verbos en la URL**.
- Evitar el uso de **caracteres especiales**.
- Separar palabras con **guiones**.
- Uso de **nombres claros e intuitivos**.
- Evitar el uso de **extensiones de archivos**.

# Commit Message Policies

Se han establecido políticas claras para los mensajes de commit con el objetivo de garantizar un historial de cambios consistente, legible y alineado con la estructura del trabajo colaborativo.

## Estructura del Mensaje

Los mensajes de commit se estructuran de manera estándar, reflejando el tipo de cambio realizado, su relación con el issue correspondiente y una descripción breve pero informativa. Esta metodología fomenta un flujo de trabajo ordenado, minimiza posibles conflictos y optimiza la colaboración entre los participantes.

### La estructura será la siguiente:

```
[Tipo]: Título de issue
```

### El tipo define el propósito del commit:

- **feat:** nuevas funcionalidades
- **fix:** correcciones
- **docs:** cambios en la documentación
- **style:** cambios en el formato o estilo
- **refactor:** cambios de código para mejorar la optimización o legibilidad
- **test:** adición o modificación de pruebas

## Relación con Issues y Ramas

- Cada commit debe estar relacionado con una **issue previamente creada**.

## Frecuencia de Commits

- Se fomenta la realización de **commits pequeños y frecuentes**, asegurándose de que cada commit represente un cambio coherente y enfocado.
- Esto permite que las revisiones sean más ágiles y reduce el riesgo de conflictos al integrar los cambios de diferentes colaboradores.
- Los cambios que **no están relacionados** entre sí deben realizarse en **commits separados**.

## Cierre de Issues

- Se deben usar palabras clave como **"Closes"**, **"Fixes"** o **"Resolves"** al final del mensaje del commit para indicar cuando un cambio cierra un issue específico.
- Esto asegura que la resolución de cada issue quede **automáticamente reflejada** en el sistema de seguimiento, facilitando la gestión del proyecto.

## Revisión de Commits Antes del Merge

- Antes de integrar cambios en la rama principal, los commits deben **revisarse** para verificar que cumplan con las políticas establecidas.

# Structure of Repositories and Default Branches

## Estructura de Carpetas y Archivos

1. A continuación, se detallan las principales carpetas y archivos:

- **.mvn/wrapper/**: Carpeta generada por el Maven wrapper, contiene sus scripts y binarios necesarios para ejecutar Maven sin necesitar una instalación global.
- **frontend/**: Carpeta destinada a la parte de la aplicación que corresponde con la interfaz de usuario.
- **src/**: Contiene el código fuente de la aplicación backend.

### Archivos de configuración y utilitarios (en la raíz del proyecto):

- **.editorconfig**: Define reglas de codificación para editores.
- **.gcloudignore**: Archivos y carpetas que Google Cloud debe ignorar.
- **.gitignore**: Archivos y carpetas que Git debe ignorar.
- **docker-compose.yml**: Define y coordina los contenedores.
- **info.yml**: Archivo que contiene metadatos.
- **mvnw, mvnw.cmd**: Scripts para ejecutar el Maven Wrapper en distintos sistemas operativos.
- **pom.xml**: Archivo principal de configuración de Maven.

### Otros archivos:

- **README.md**: Explica de forma general el proyecto, cómo configurarlo e iniciarlo.

2. La **rama predeterminada** es **main**. Esta rama siempre refleja el estado listo para su producción.

# Branching Strategy (Based on Git Flow and Including Peer Reviews)

## Cómo Desarrollar Feature Branches

- Por cada issue se creará una **nueva rama**.
- En dicha rama se subirán los commits realionados con dicha issue.
- Una vez la issue haya sido completada, se procederá a realizar un _compare & pull request_, a la rama main (la cual se utilizará como rama de desarrollo) asociando a esta dicho issue. Esta pull request deberá de ser revisada por un número mínimo de tres personas. Finalmente, una vez haya sido aprobada se llevará a cabo un _merge_ de los cambios hacia la rama main.

## Cómo Preparar Releases

- Para preparar los diferentes **releases** se creará una **rama específica** en la que todos los miembros del equipo trabajarán para resolver los posibles errores que no hayan sido identificados con anterioridad.
- También se establecerán y actualizarán los **metadatos**, por ejemplo, se actualizará la versión del proyecto.

## Cómo Corregir Bugs en Producción

- Los **bugs en tiempo de producción** requieren un enfoque meticuloso para minimizar el impacto para los usuarios y la estabilidad del sistema.

### Metodologías Aplicadas:

1. **Clasificación de la severidad:**
   - Errores de **nivel bajo**: errores visuales o de poca importancia.
   - Errores de **mayor gravedad**: aquellos que afectan a los usuarios o comprometen la seguridad de la aplicación.

2. **Respuesta inmediata del equipo:**
   - Tras la detección, el equipo valorará el error y decidirá si requiere una solución inmediata o **hotfix**.

3. **Implementación:**
   - Replicar el error en el entorno de **staging**.
   - Tras su reparación, otro desarrollador revisará los cambios, ejecutando al menos las **pruebas básicas**.

4. **Seguimiento:**
   - Tras el **relanzamiento** de la aplicación en el entorno de producción, se llevará a cabo un **análisis del comportamiento del sistema**.

# Versioning Policies

Las numeraciones de las versiones seguirán la siguiente estructura, comenzando en la versión **0.0.1**:

- **Versión mayor:** Después de cada **release** satisfactoria se incrementará en uno la versión mayor del proyecto (ej. después de la primera entrega, versión 1.0.0).
- **Versión menor:** Por cada historia de usuario completada y cumpliendo la definición de **"hecho"**, se incrementará en uno la versión menor del proyecto (ej. tras añadir la primera nueva funcionalidad, versión 1.1.0).
- **Versión de parche:** Estas versiones se lanzarán cuando se corrija algún fallo o error de una funcionalidad implementada en el proyecto (ej. al hacer una corrección en la funcionalidad lanzada con la versión 1.1.0, la versión pasará a ser la 1.1.1)

### Reglas del versionado:
- Cuando se aumente la versión mayor, la menor y la de parche se resetearán volviendo a 0.
- Cuando se aumente la versión menor, la versión de parche se reseteará volviendo a 0.
- Si hay que hacer una corrección en una funcionalidad lanzada en una versión mayor o menor anterior se incrementará en uno la versión de parche indicando claramente a que funcionalidad (incluyendo su correspondiente versión) se le ha aplicado el parche.

# Definition of "Done"

Para nuestro grupo, previamente la tarea deberá cumplir con los siguientes criterios:

- Cumplir con los **criterios de aceptación** de la historia de usuario.
- Pasar con éxito las **pruebas unitarias**.
- La **documentación** debe haberse actualizado.
- Revisar y resolver las **observaciones** que puedan surgir.

Una vez se cumplan estos criterios, se podrá nombrar una tarea como realizada (**"done"**) cuando se haya hecho el **merge** de dichos cambios a la rama principal **main** después de que su **pull request** haya sido revisada y aprobada por varios miembros del equipo.

# Management of Project Documents

## Gestión de Documentos Generados Durante el Proyecto

En cada lanzamiento del proyecto se plantea la entrega de cierta documentación, así como la actualización, si resulta necesario, de la ya existente:

- **Technical Report:**
  - Decisiones de diseño y uso de la **CMDB (iTop)** para la gestión de activos y configuración en el proyecto.
  - Objetivos y alcance del **CMDB**, junto a su estructura.

- **Configuration Management:**
  - Política de **buenas prácticas** construida por el equipo de desarrollo, que se deberá seguir durante el proyecto.

- **Group Work Report:**
  - **Minutos de reunión** y trabajo llevados a cabo por los diferentes integrantes del equipo.
  - **Sprint planning**, actas de la **sprint review**, decisiones tomadas y actas de las **retrospectivas** llevadas a cabo al final de cada sprint.











