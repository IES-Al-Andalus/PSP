# 3.6. Creación de procesos

Las clases que vamos a necesitar para la creación de procesos, son:

* Clase `java.lang.Process.` Proporciona los objetos Proceso, por los que podremos controlar los procesos creados desde nuestro código.
* Clase `java.lang.Runtime.` Clase que permite lanzar la ejecución de un programa en el sistema. Sobre todos son interesantes los métodos exec\(\) de esta clase, por ejemplo:
  * `Runtime.exec(String comando)`; devuelve un objeto Process que representa al proceso en ejecución que está realizando la tarea comando.

La ejecución del método `exec`\(\) puede lanzar las excepciones: `SecurityException`, si hay administración de seguridad y no tenemos permitido crear subprocesos. `IOException`, si ocurre un error de E/S. `NullPointerException` y `IllegalArgumentException`, si commando es una cadena nula o vacía.

Veamos un ejemplo sencillo. Si queremos editar varios ficheros de texto a la vez, necesitamos que sean creados tantos procesos del editor de texto, como documentos queramos editar. Vamos a utilizar la aplicación de ejemplo del IDE NetBeans 'Editor de texto \(Document Editor\)', para que nos permita editar varios documentos al mismo tiempo en distintas instancias del editor.

