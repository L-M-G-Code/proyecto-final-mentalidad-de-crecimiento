#Post Mortem-Error en enlaces de navegacion (commit v1.03)

##Contexto

Durante el desarrollo de una página web institucional responsive, el equipo trabajaba en la implementación de la estructura general del sitio, compuesta por múltiples secciones accesibles desde una barra de navegación (navbar).

El proyecto estaba desarrollado con HTML, CSS,siguiendo una estructura modular para facilitar el mantenimiento y escalabilidad del código. El control de versiones se gestionó mediante Git y GitHub, utilizando commits frecuentes para registrar avances y cambios importantes.

En la versión v1.03, se realizó una actualización enfocada en mejorar la navegación entre páginas y optimizar la experiencia del usuario.

-------------------------------------------------------------------------------------

##Problema

Durante las pruebas posteriores al commit v1.03, se detectó un error crítico en la configuración de los enlaces del navbar.

Los enlaces de navegación presentaban los siguientes problemas:

*Algunos redirigían a rutas incorrectas.

*Otros generaban error 404.

*En ciertos casos, varios botones apuntaban al mismo destino de forma accidental.

Esto afectaba directamente la navegación del sitio, generando una mala experiencia de usuario y comprometiendo una funcionalidad central de la aplicación.

-------------------------------------------------------------------------------------

Acciones

Para resolver el incidente, se llevaron a cabo las siguientes acciones:

1. Identificación del error

Se revisó el commit v1.03 para comparar cambios recientes en el navbar y detectar las rutas afectadas.

2. Corrección de enlaces

Se actualizaron manualmente todos los enlaces incorrectos para asegurar que cada botón redirigiera a su página correspondiente.

Ejemplo del error:

<li><a href="./pages/contacto.html">Inicio</a></li>

Corrección aplicada:

<li><a href="./index.html">Inicio</a></li>
3. Testing completo

Se ejecutó una validación manual de todos los enlaces del navbar en:

*Desktop

*Tablet

*Mobile

4. Post-mortem constructivo

Se realizó una revisión interna enfocada no en buscar responsables, sino en identificar fallas del proceso.

Se concluyó que el problema no estuvo únicamente en el error de código, sino también en la falta de validaciones posteriores a cambios estructurales.

Como resultado, se incorporaron mejoras al flujo de trabajo:

*Revisión obligatoria de navegación antes de cada commit importante.

*Checklist de QA básica.

*Mayor granularidad en commits para facilitar debugging.

-------------------------------------------------------------------------------------

Aprendizajes

Este incidente dejó aprendizajes importantes para el equipo:

 *Cambios pequeños en rutas pueden generar fallas críticas en navegación.
 *El testing funcional debe formar parte del flujo normal de desarrollo.
 *Los commits deben ser claros y enfocados en cambios específicos.
 *La revisión de código reduce errores evitables.

A partir de este caso, se implementó una metodología más rigurosa de validación antes de cerrar tareas relacionadas con frontend.

-------------------------------------------------------------------------------------

Documentación de control de versiones

Repositorio del proyecto:
GitHub Repository

Commit con error detectado (v1.03):
Commit v1.03 - Navbar Update

Commit con corrección aplicada:
Fix Navbar Links

Pull Request de validación:
PR #12 - Fix Navigation Routes

-------------------------------------------------------------------------------------

Reflexión sobre feedback radicalmente sincero

Durante este proceso se aplicó feedback radicalmente sincero mediante una comunicación directa, clara y constructiva entre los integrantes del equipo.

En lugar de enfocarnos en quién cometió el error, priorizamos discutir con honestidad qué falló en el proceso y cómo evitar que vuelva a suceder.

El feedback fue específico y orientado a soluciones: se señaló la ausencia de testing y revisión de rutas como puntos críticos, pero siempre desde una perspectiva de mejora continua.

Esta forma de trabajo permitió transformar un error técnico en una oportunidad de aprendizaje, fortaleciendo tanto la calidad del proyecto como la dinámica del equipo.
