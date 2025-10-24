# Implementación de Crystal Clear para EducaciónContinuaFCA-Sales

Este documento detalla la adopción y adaptación de la metodología ágil **Crystal Clear** para la gestión y desarrollo del proyecto **EducaciónContinuaFCA-Sales**.

---

## 1. Principios y Prioridades de Crystal

Nuestra implementación se guía por los siguientes principios de Crystal:

| Principio de Crystal | Nuestra Aplicación |
| :--- | :--- |
| **Entrega Frecuente** | Entregamos software funcional a los usuarios al final de cada Sprint (cada semana). |
| **Mejora Reflexiva** | Realizamos retrospectivas al final de cada sprint para ajustar procesos y herramientas. |
| **Comunicación Osmótica** | Fomentamos la comunicación directa y continua, ya sea en persona o mediante canales de comunicación activos (Ver Punto 6). |
| **Seguridad Personal** | Es seguro que cualquier miembro del equipo exprese ideas o preocupaciones sin temor a represalias. |
| **Foco** | Los desarrolladores trabajan en 1 tarea a la vez, minimizando el cambio de contexto. |

---

## 2. Estructura del Equipo y Comunicación

### 2.1 Roles del Equipo

En línea con Crystal Clear, hemos asignado los siguientes roles (una persona puede tener múltiples roles):

| Rol de Crystal | Miembro del Equipo / Área | Responsabilidades Clave |
| :--- | :--- | :--- |
| **Sponsor Ejecutivo** | **Edgar Cambranes, Freddy Collí** | Proporciona la visión y el presupuesto; toma decisiones de alto nivel. |
| **Enlace del Usuario** | **Edgar Cambranes** | Representa al usuario, define los Casos de Uso (Issues) y valida los entregables. |
| **Diseñador/Programador** | **Juan Ceballos, Alexander Canto, Yahdiel Gutierrez, María Fernanda Gonzáles, Alexander Pinzon, Buntarou Emiliano Orduño** | Responsable del diseño, codificación, pruebas unitarias y calidad del código. |
| **Coach** | **Juan Ceballos** | Guía al equipo en la metodología y ayuda a resolver impedimentos. |

### 2.2 Ritmo de las Reuniones

Nuestro "Latido" se basa en Sprints de **2 semanas**.

| Evento | Frecuencia | Duración Máxima | Propósito |
| :--- | :--- | :--- | :--- |
| **Daily Update** | Diario (L-V) | 5 minutos | Todos mandan sus avances y bloqueos por WhatsApp (Ver Punto 6). |
| **Planificación del Sprint** | Inicio del Sprint | 1 hora | Seleccionar Issues del `Backlog` y asignar la carga de trabajo. |
| **Revisión del Sprint** | Fin del Sprint | 1 hora | Demostrar el software funcional al Enlace del Usuario y al Sponsor. |
| **Retrospectiva** | Fin del Sprint | 45 minutos | Reflexionar sobre el Sprint pasado e identificar 1-2 mejoras para aplicar. |

---

## 3. Flujo de Trabajo y Herramientas

Nuestro tablero tiene el siguiente flujo de columnas:

| Columna de Kanban | Propósito / Criterio de Ingreso |
| :--- | :--- |
| **Backlog (o Coming Up)** | Repositorio de todos los Issues pendientes, aún no planificados en un Sprint. |
| **To Do / Ready** | Issues que han sido seleccionados, estimados y asignados a la Iteración actual, listos para ser desarrollados. |
| **In Progress** | Tarea que está siendo desarrollada activamente por un Diseñador/Programador |
| **Ready for Review** | El código ha sido completado, las pruebas unitarias han pasado, y está esperando una **Revisión de Par (Code Review)**. |
| **Done** | La tarea cumple con el **100%** de lis **Criterios de Aceptación** y ha sido aceptada por el Enlace del Usuario. |

---

### 3.2 Definición de Listo (Definition of Done - DoD)

Una tarea (Issue) solo puede ser movida a la columna **"Done"** cuando **TODOS** los siguientes puntos se han cumplido:

1.  El código está escrito y documentado.
2.  Las **pruebas unitarias** cubren el 90% o más del nuevo código.
3.  Todos los **Criterios de Aceptación** definidos en el Issue han sido verificados.
4.  El *Pull Request* (PR) ha sido **aprobado** por al menos un compañero.
5.  El cambio ha sido **desplegado** en el ambiente de **[NOMBRE DEL AMBIENTE - Ej: Staging Sandbox]**.
6.  El **Enlace del Usuario** ha **validado y aceptado** la funcionalidad.

---

## 4. Gestión de Issues

Cada Caso de Uso (`CU-VE-XXX`) se gestiona como un **Issue** en GitHub y utiliza la siguiente convención:

* **Título:** `[CU-VE-XXX] Descripción concisa`
* **Puntuación (Story Points):** Indica la complejidad y el esfuerzo (Ver documentación de `CONTRIBUTING.md`).
* **Iteración:** Asigna el Issue al Sprint correspondiente para el seguimiento.

---

## 5. Reglas de Documentación y Flujo de Trabajo (Git Workflow) 🚀

Para mantener un historial de cambios limpio, trazable y fácil de revisar, utilizaremos un flujo de trabajo basado en *Feature Branching*.

### 5.1 Convenciones para la Creación de *Branches*

Todas las *branches* de desarrollo deben crearse a partir de la *branch* principal (`main`) o de la *branch* de desarrollo (`develop`, si existe y se usa como *staging*).

| Tipo de Branch | Prefijo | Propósito | Ejemplo |
| :--- | :--- | :--- | :--- |
| **Feature** | `feat/` | Desarrollo de nuevas características según un Issue. | `feat/CU-VE-001-login-social` |
| **Fix** | `fix/` | Solución de un *bug* o un Issue de tipo *Bug*. | `fix/CU-VE-005-calculo-impuesto-incorrecto` |
| **Hotfix** | `hotfix/` | Solución de un error crítico directamente en la *branch* `main`. | `hotfix/001-error-pago-pasarela` |
| **Chore** | `chore/` | Tareas de mantenimiento, *refactorizaciones*, o mejoras de documentación. | `chore/actualizar-dependencias-npm` |

***

### 5.2 Conventional Commits (Compromisos Convencionales)

Adoptamos la especificación **Conventional Commits** para asegurar que los mensajes de *commit* sean legibles, estandarizados y que permitan la generación automática de *changelogs*.

#### 5.2.1 Formato Estándar

Cada mensaje de *commit* **DEBE** seguir esta estructura:

$$
\text{<tipo>}(\text{<ámbito>})!: \text{<descripción concisa>} \\ \text{<cuerpo opcional>} \\ \text{<pie de página opcional>}
$$

1.  **Tipo (`<tipo>`):** Obligatorio, define la naturaleza del cambio (ej: `feat`, `fix`, `docs`).
2.  **Ámbito (`<ámbito>`):** Opcional, indica la parte del sistema afectada. **Recomendado usar el ID del Issue** (ej: `CU-VE-001`).
3.  **Descripción (`<descripción concisa>`):** Obligatorio, un resumen breve y en **imperativo** (ej: *Añadir*, *Corregir*) de lo que hizo el *commit*.
4.  **Símbolo `!`:** Opcional, se añade después del ámbito para indicar un **cambio disruptivo** (*Breaking Change*).
5.  **Cuerpo Opcional:** **Debe ir después de una línea en blanco.** Se usa para dar información adicional y detallada (**el qué y el por qué**), especialmente si el cambio es complejo.
6.  **Pie de Página Opcional:** Se usa para referenciar Issues o indicar *Breaking Changes*.

#### 5.2.2 Tipos de Commit Permitidos

| Tipo | Propósito | Uso Común |
| :--- | :--- | :--- |
| **`feat`** | Una **nueva característica**. | `feat(CU-VE-010): añadir endpoint para consulta de cursos` |
| **`fix`** | Una **corrección de *bug***. | `fix(CU-VE-005): corregir cálculo de IVA en carrito` |
| **`docs`** | Cambios puramente de **documentación**. | `docs: actualizar CONTRIBUTING.md con reglas de commit` |
| **`refactor`**| Un **cambio de código** que no soluciona un bug ni añade una funcionalidad. | `refactor(auth): extraer lógica de token a un servicio` |
| **`test`** | Añadir o corregir **pruebas unitarias/integración**. | `test(CU-VE-011): añadir pruebas para validación de datos` |
| **`chore`** | Tareas de **mantenimiento** (configs, dependencias). | `chore: actualizar versión de Node a 18.x` |

#### 5.2.3 Referencia al Issue

En el **pie de página** del *commit* que **finaliza** un Issue, es **obligatorio** incluir la referencia para que GitHub lo cierre automáticamente:

> **Ejemplo de Commit Final con Cuerpo:**
>
> ```
> feat(CU-VE-001): Implementar flujo completo de inicio de sesión con Google
>
> El flujo se ha implementado utilizando el SDK de Google de forma asíncrona
> para evitar bloqueos del hilo principal, creando un usuario local si no existe
> o actualizando su sesión si ya estaba registrado.
>
> Resolves: #CU-VE-001
> ```

### 5.3 Gestión de Pull Requests (PR)

1.  **Título del PR:** Debe ser descriptivo y seguir la convención de *Commit* para el cambio principal.
2.  **Vinculación:** El PR **DEBE** vincularse al Issue correspondiente.
3.  **Revisión de Par:** Todo PR requiere al menos **una aprobación** de un compañero (*Code Review*) antes de ser *mergeado*, cumpliendo con el **Punto 4 del DoD**.
4.  **Integración:** Solo los **Coaches** o **Diseñadores/Programadores Senior** pueden *mergear* un PR tras la aprobación y el cumplimiento de los **6 puntos del DoD**.

---

## 6. Reglas de Comunicación Diaria 💬

Para fomentar la **Comunicación Osmótica** y el **Foco** (Principios de Crystal), formalizamos el canal de **WhatsApp** para el `Daily Update` (5 min).

### 6.1 Reporte Diario (Daily Update)

El `Daily Update` se enviará en el grupo de WhatsApp a primera hora (ej: 9:00 AM) de Lunes a Viernes, siguiendo estrictamente el siguiente formato, respondiendo a **3 preguntas clave**:

1.  **¿Qué hiciste ayer?** (Enfocarse en el **Issue** en el que se trabajó).
2.  **¿Qué haré hoy?** (Indicar la **tarea específica** que se va a abordar, ligada a un Issue en *To Do*).
3.  **¿Qué bloqueos tengo?** (Mencionar **cualquier impedimento** que detenga el progreso).

> **Ejemplo de Mensaje:**
>
> ```
> 📅 **Daily Update - [Tu Nombre]**
>
> 1. ✅ **Ayer:** Finalicé la implementación del formulario de pago (CU-VE-008), moviéndolo a 'Ready for Review'.
> 2. 🚧 **Hoy:** Trabajaré en la conexión del formulario (CU-VE-008) con el *backend* de Stripe.
> 3. 🛑 **Bloqueos:** Necesito la clave pública de prueba de Stripe. ¿@EdgarCambranes me la podrías proporcionar?
> ```

### 6.2 Comunicación General

# Métodos para la Estimación del Esfuerzo en Proyectos de Software

El siguiente documento resume métodos para la estimación del esfuerzo en proyectos de software, principalmente basados en **Puntos de Casos de Uso (UCP)** y la relación con la **complejidad y las transacciones**, así como un método basado en la **cantidad de objetos y su complejidad**.

---

## 1. Puntos de Casos de Uso (UCP)

El método de **Puntos de Casos de Uso (UCP)** clasifica los casos de uso en tres niveles de complejidad, basándose en el número de transacciones que contienen:

| Clasificación | Número de Transacciones | Factor de Peso |
|----------------|--------------------------|----------------|
| Simple         | 1 a 3                    | 5              |
| Promedio       | 4 a 7                    | 10             |
| Complejo       | 8 o más                  | 15             |

Una **transacción** se define como un evento que ocurre entre un actor y el sistema a ser modelado.

Una vez especificados los casos de uso, se obtiene un mejor nivel de detalle para estimar de manera más exacta los puntos de función.

---

## 2. Estimación del Esfuerzo a partir de los Casos de Uso

El esfuerzo estimado se mide en **horas-hombre** y se calcula con la siguiente fórmula:

E = UCP \times CF

