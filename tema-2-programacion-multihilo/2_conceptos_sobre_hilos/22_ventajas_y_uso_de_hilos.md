# 2.2. Ventajas y uso de hilos

Como consecuencia de compartir el espacio de memoria, los hilos aportan las siguientes **ventajas sobre los procesos**:

* Se consumen menos recursos en el lanzamiento, y la ejecución de un hilo que en el lanzamiento y ejecución de un proceso.
* Se tarda menos tiempo en crear y terminar un hilo que un proceso.
* La conmutación entre hilos del mismo proceso o [cambio de contexto_Cambio de contexto_Es la acción que efectúa el scheduler \(componente del núcleo del procesador que planifica la ejecución de procesos\) cuando transfiere el procesador de un proceso a otro. Para realizar el cambio de contexto debe realizar diversas labores que conlleva consumir tiempo de procesador.]() es bastante más rápida que entre procesos.

Es por esas razones, por lo que a los hilos se les denomina también **procesos ligeros**.

Y ¿**cuándo se aconseja utilizar hilos**? Se aconseja utilizar hilos en una aplicación cuando:

* La aplicación maneja entradas de varios dispositivos de comunicación.
* La aplicación debe poder realizar diferentes tareas a la vez.
* Interesa diferenciar tareas con una prioridad variada. Por ejemplo, una prioridad alta para manejar tareas de tiempo crítico y una prioridad baja para otras tareas.
* La aplicación se va a ejecutar en un entorno multiprocesador.

Por ejemplo, imagina la siguiente situación:

* Debes crear una aplicación que se ejecutará en un servidor para atender peticiones de clientes. Esta aplicación podría ser un servidor de bases de datos, o un servidor web.
* Cuando se ejecuta el programa éste abre su puerto y queda a la escucha, esperando recibir peticiones.
* Si cuando recibe una petición de un cliente se pone a procesarla para obtener una respuesta y devolverla, cualquier petición que reciba mientras tanto no podrá atenderla, puesto que está ocupado.
* La solución será construir la aplicación con múltiples hilos de ejecución.
* En este caso, al ejecutar la aplicación se pone en marcha el hilo principal, que queda a la escucha.
* Cuando el hilo principal recibe una petición, creará un nuevo hilo que se encarga de procesarla y generar la consulta, mientras tanto el hilo principal sigue a la escucha recibiendo peticiones y creando hilos.
* De esta manera un gestor de bases de datos puede atender consultas de varios clientes, o un servidor web puede atender a miles de clientes.
* Si el número de peticiones simultáneas es elevado, la creación de un hilo para cada una de ellas puede comprometer los recursos del sistema. En este caso, como veremos al final de la unidad lo resolveremos mejor con un pool de hilos.

Resumiendo, los hilos son idóneos para programar aplicaciones de entornos interactivos y en red, así como simuladores y animaciones.

