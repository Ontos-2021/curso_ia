# Silabus del Curso: Construir Productos con IA

## 1. Datos generales

- Nombre del curso: Construir Productos con IA.
- Modalidad: curso modular.
- Duracion sugerida: 10 sesiones.
- Duracion por sesion: 90 a 120 minutos.
- Nivel: inicial.
- Perfil de ingreso: principiantes totales o personas con poca experiencia tecnica interesadas en IA aplicada.

## 2. Descripcion del curso

Este curso introduce a los participantes en el uso practico de la inteligencia artificial para construir productos utiles con una base tecnica razonable. El enfoque no se limita al prompting o al uso superficial de asistentes, sino que busca desarrollar una comprension clara de como funcionan los modelos, como se integran en aplicaciones reales y como se preparan para uso practico mediante Git, variables de entorno, Docker y despliegue.

El curso combina fundamentos conceptuales, demostraciones guiadas y trabajo practico orientado a un proyecto final. La meta es que cada participante comprenda el flujo completo: desde entender que es un LLM hasta poner en marcha un prototipo funcional.

## 3. Objetivo general

Que el estudiante sea capaz de pasar de una idea a una aplicacion util con IA, comprendiendo los fundamentos de los modelos, el uso estructurado de asistentes y prompts, la integracion con APIs y herramientas, y las bases minimas de desarrollo necesarias para versionar, contenerizar y desplegar un producto sencillo.

## 4. Objetivos especificos

Al finalizar el curso, el estudiante deberia poder:

- Explicar que es un LLM, que es un token y como funciona el contexto.
- Entender a nivel conceptual como se entrenan las redes neuronales modernas.
- Utilizar asistentes y prompting de forma estructurada.
- Distinguir entre modelo, chat, asistente, producto y agente.
- Integrar una API con manejo basico de claves y variables de entorno.
- Entender que problema resuelve MCP y como pensar integraciones.
- Usar herramientas actuales de desarrollo con mejor criterio.
- Trabajar con Git en un flujo basico de colaboracion.
- Empaquetar una aplicacion simple con Docker.
- Desplegar un prototipo funcional.

## 5. Resultados de aprendizaje

Se espera que al finalizar el curso el estudiante pueda:

- Analizar una tarea y decidir como usar un modelo de lenguaje de forma adecuada.
- Diseñar instrucciones y prompts mas claros, utiles y verificables.
- Pensar una aplicacion con IA como sistema, y no solo como una llamada aislada a un chat.
- Configurar un entorno de desarrollo minimo para construir y compartir un proyecto.
- Presentar un producto funcional con una base razonable de reproducibilidad.

## 6. Metodologia

El curso se desarrolla bajo una metodologia practica con tres capas por sesion:

- Concepto: para introducir el marco teorico minimo.
- Demo: para observar una implementacion concreta.
- Practica: para aplicar lo aprendido inmediatamente.

Distribucion sugerida por sesion:

- 20 por ciento concepto.
- 30 por ciento demo.
- 50 por ciento practica.

La practica tiene prioridad. El curso esta pensado para que los estudiantes construyan y experimenten, no solo para escuchar explicaciones.

## 7. Estrategia de evaluacion

La evaluacion del curso debe centrarse en la capacidad de construir algo util y razonablemente consistente. Se recomienda evaluar:

- Comprension de los conceptos fundamentales.
- Calidad del uso de prompts, contexto e instrucciones.
- Capacidad para integrar herramientas y APIs.
- Orden y reproducibilidad del proyecto.
- Uso basico de Git.
- Configuracion correcta de variables de entorno.
- Empaquetado y despliegue funcional.

### Ponderacion sugerida

- Participacion y ejercicios por sesion: 30 por ciento.
- Avances del proyecto final: 30 por ciento.
- Proyecto final y demo: 40 por ciento.

## 8. Requisitos minimos

- Computador con acceso a internet.
- Editor de codigo, idealmente VS Code.
- Cuenta en alguna plataforma de IA con acceso a modelos o APIs.
- Git instalado.
- Docker instalado.

## 9. Unidades y cronograma sugerido

### Sesion 1. Fundamentos de IA y LLMs

**Objetivo de la sesion**

Comprender que es un modelo de lenguaje, que hace y cuales son sus limites basicos.

**Contenidos**

- IA, machine learning, deep learning y LLM.
- Que es un token.
- Prediccion del siguiente token.
- Contexto y ventana de contexto.
- Diferencia entre modelo, chat, asistente y producto.

**Actividad practica**

- Resolver una misma tarea con distinto nivel de contexto.
- Comparar resultados y discutir por que cambian.

**Evidencia de aprendizaje**

- Explicacion breve de como funciona un LLM en terminos practicos.

### Sesion 2. Redes neuronales, transformers y entrenamiento

**Objetivo de la sesion**

Entender de forma conceptual como se construyen y entrenan los modelos modernos.

**Contenidos**

- Redes neuronales.
- Embeddings.
- Atencion y transformers.
- Entrenamiento, loss y ajuste de pesos.
- Pretraining, fine-tuning y RLHF.
- Diferencia entre entrenamiento e inferencia.

**Actividad practica**

- Trazar el recorrido desde datos hasta respuesta.
- Identificar limites y ventajas de distintos modelos.

**Evidencia de aprendizaje**

- Mapa conceptual o explicacion grupal del proceso.

### Sesion 3. Prompting y chat con asistentes

**Objetivo de la sesion**

Aprender a dar instrucciones claras y utiles a un asistente.

**Contenidos**

- Estructura de instrucciones.
- Rol, objetivo, contexto, restricciones y formato.
- Prompting iterativo.
- Zero-shot y few-shot.
- Como reducir alucinaciones.
- Como pedir salidas utiles.

**Actividad practica**

- Reescribir prompts defectuosos.
- Diseñar prompts para planificacion, creatividad y codigo.

**Evidencia de aprendizaje**

- Entrega de una pequena biblioteca de prompts utiles.

### Sesion 4. Productos construidos arriba de modelos

**Objetivo de la sesion**

Entender que una app con IA es un sistema y no solo una llamada a un modelo.

**Contenidos**

- Modelo versus producto.
- Contexto persistente.
- Memoria.
- Archivos e instrucciones.
- Herramientas.
- Ejemplos tipo ChatGPT Projects.
- Que hace que una app sea robusta.

**Actividad practica**

- Diseñar la arquitectura conceptual de un producto simple con IA.

**Evidencia de aprendizaje**

- Esquema de producto con separacion entre modelo, backend e interfaz.

### Sesion 5. APIs, claves, costos y variables de entorno

**Objetivo de la sesion**

Aprender a conectar una aplicacion con servicios externos de forma segura y ordenada.

**Contenidos**

- Que es una API.
- API key versus token de texto.
- Request y response.
- Rate limits y costo.
- Variables de entorno.
- Diferencia entre desarrollo y produccion.

**Actividad practica**

- Hacer una llamada simple a una API.
- Configurar credenciales con variables de entorno.

**Evidencia de aprendizaje**

- Ejemplo funcional de integracion con API usando configuracion separada del codigo.

### Sesion 6. Agentes y MCP

**Objetivo de la sesion**

Comprender que es un agente, cuando tiene sentido usarlo y que problema resuelve MCP.

**Contenidos**

- Que es un agente.
- Herramientas, estado, memoria y toma de decisiones.
- Cuando un agente tiene sentido y cuando no.
- Que es MCP.
- Integraciones con archivos, servicios y herramientas.

**Actividad practica**

- Diseñar un agente simple de research, planificacion o ejecucion.

**Evidencia de aprendizaje**

- Definicion breve del agente, sus herramientas y sus limites.

### Sesion 7. Herramientas modernas para construir

**Objetivo de la sesion**

Aprender a usar el ecosistema actual de asistentes de desarrollo con criterio.

**Contenidos**

- VS Code.
- GitHub Copilot.
- Cursor.
- Claude Code.
- Casos de uso para explorar, escribir, refactorizar, depurar y documentar.
- Riesgos de delegar demasiado.

**Actividad practica**

- Resolver una mini tarea con distintas herramientas.
- Comparar resultados.

**Evidencia de aprendizaje**

- Reflexion breve sobre que herramienta usar segun la tarea.

### Sesion 8. Git para trabajar en equipo

**Objetivo de la sesion**

Adquirir una base funcional de control de versiones y colaboracion.

**Contenidos**

- Control de versiones.
- Repositorio, commit, rama y merge.
- Clone, init, add, commit, push, pull.
- Conflictos simples.
- Gitignore.

**Actividad practica**

- Crear un repositorio, trabajar con ramas y resolver un conflicto simple.

**Evidencia de aprendizaje**

- Repositorio con historial basico de trabajo.

### Sesion 9. Docker, despliegue y servidor

**Objetivo de la sesion**

Entender como preparar y desplegar una app de manera reproducible.

**Contenidos**

- Que problema resuelve Docker.
- Imagen y contenedor.
- Dockerfile.
- Puertos.
- Variables de entorno en despliegue.
- Logs basicos.
- Servidor, hosting y plataforma gestionada.
- Opciones como Vercel, Railway o Render.

**Actividad practica**

- Dockerizar una app simple.
- Levantarla localmente y dejarla lista para deploy.

**Evidencia de aprendizaje**

- Aplicacion corriendo en contenedor.

### Sesion 10. Proyecto final y demo

**Objetivo de la sesion**

Cerrar el curso con un producto funcional que integre los principales contenidos trabajados.

**Opciones de proyecto**

- Asistente de planificacion personal o de equipo.
- Copiloto creativo para ideas, contenido o guiones.
- Mini app de chat con archivos y contexto.
- Agente simple con una o dos herramientas.

**Entregables**

- App funcional.
- Repositorio ordenado.
- Variables de entorno bien configuradas.
- Docker basico.
- Despliegue funcionando.
- Demo final.

**Evidencia de aprendizaje**

- Presentacion del proyecto y demostracion funcional.

## 10. Proyecto final recomendado

La opcion recomendada para este curso es un asistente de planificacion o un copiloto de trabajo. Este proyecto permite integrar de manera equilibrada los fundamentos de modelos, prompting, APIs, variables de entorno, Git, Docker y despliegue.

## 11. Criterios de aprobacion sugeridos

Se sugiere considerar aprobado al estudiante que:

- Participe activamente en las practicas.
- Entregue avances del proyecto.
- Presente un producto funcional al cierre del curso.
- Demuestre comprension basica de los conceptos clave.

## 12. Bibliografia y recursos de referencia sugeridos

- Documentacion oficial de VS Code.
- Documentacion oficial de GitHub Copilot.
- Documentacion basica de Docker.
- Documentacion del proveedor de API de IA que se utilice en clase.
- Recursos introductorios sobre transformers, prompting y agentes.

## 13. Observacion final

Este silabus esta pensado para una formacion inicial orientada a la accion. Su valor no esta en cubrir toda la teoria posible, sino en dar una base suficiente para que los participantes entiendan lo que hacen, construyan algo util y tengan un punto de partida serio para seguir desarrollandose.