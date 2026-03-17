Laboratorio 1 

Integrantes:

Maria Elena Martiez

Genesis Maribel Cruz 

Problematica
En la universidad, los estudiantes suelen olvidar sus tareas y compromisos académicos porque no cuentan con una herramienta sencilla para organizarlas.
Problema: Falta de organización en la gestión de tareas.
Sector: Educación, estudiantes universitarios.
Solución: Una aplicación web que permita agregar tareas, listarlas, validarlas y marcarlas como completadas.

Funcionalidades principales
Agregar tareas mediante un formulario.
Validar que no se ingresen tareas vacías.
Mostrar lista de tareas con opción de eliminar o marcar como completadas.
Uso de variables reactivas y directivas de Vue.js.
Interfaz sencilla y dinámica.

📌 Preguntas
1. ¿Qué es Vue.js y cuál es su función dentro de la página web desarrollada?
Vue.js es un framework progresivo de JavaScript que permite construir interfaces de usuario dinámicas y reactivas. En este proyecto se utilizo para manejar el estado de las tareas y actualizar la interfaz automáticamente sin necesidad de recargar la página.
2. ¿Qué variables reactivas utilizó en su aplicación y cuál es la función de cada una?
nuevaTarea: almacena el texto ingresado en el input.
tareas: lista de todas las tareas registradas.
error: mensaje de validación cuando se intenta ingresar una tarea vacía.
texto (dentro de cada tarea): contenido de la tarea.
completada (dentro de cada tarea): indica si la tarea ya fue realizada.

3. Explique la diferencia entre las directivas v-bind y v-model
v-bind: enlaza atributos HTML con datos de Vue. Ejemplo: :class="{completada: tarea.completada}".

v-model: crea un enlace bidireccional entre inputs y variables, permitiendo que el valor del input se actualice automáticamente en la variable.

4. Mencione al menos un ejemplo de evento utilizado dentro de su aplicación
El evento @click en el botón Agregar, que ejecuta el método agregarTarea().

5. Explique para qué utilizó la directiva v-for dentro de su aplicación
Se utilizó para recorrer la lista de tareas y mostrarlas dinámicamente en la interfaz. Ejemplo:
vue
<li v-for="(tarea, index) in tareas" :key="index">

6. Describa en qué situación utilizó v-if y qué problema resuelve dentro de su interfaz
Se utilizó para mostrar un mensaje de error cuando el usuario intenta ingresar una tarea vacía.
Esto evita que se agreguen datos incorrectos y mejora la experiencia del usuario.

7. Explique cómo se realiza la validación de datos en su aplicación y por qué es importante validar la información ingresada por el usuario
La validación se realiza verificando que el campo nuevaTarea no esté vacío antes de agregarlo a la lista.
Es importante porque garantiza que la información ingresada sea útil y evita errores en el sistema.
