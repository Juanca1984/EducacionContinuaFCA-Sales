# Implementación de Crystal Clear EducacionContinuaFCA-Sales

Este documento detalla la adopción y adaptación de la metodología ágil **Crystal Clear** para la gestión y desarrollo del proyecto **EducaciónContinuaFCA-Sales**.

---

## 1. Principios y Prioridades de Crystal

Nuestra implementación se guía por los siguientes principios de Crystal:

| Principio de Crystal | Nuestra Aplicación |
| :--- | :--- |
| **Entrega Frecuente** | Entregamos software funcional a los usuarios al final de cada Sprint (cada semana). |
| **Mejora Reflexiva** | Realizamos retrospectivas al final de cada sprint para ajustar procesos y herramientas. |
| **Comunicación Osmótica** | Fomentamos la comunicación directa y continua, ya sea en persona o mediante canales de comunicación activos (Ver Punto 2). |
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

Nuestro "Latido" se basa en Sprints de **1 semana**.

| Evento | Frecuencia | Duración Máxima | Propósito |
| :--- | :--- | :--- | :--- |
| **Stand-up Diario** | Diario (L-V) | 15 minutos | Sincronización rápida y eliminación de impedimentos. |
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
