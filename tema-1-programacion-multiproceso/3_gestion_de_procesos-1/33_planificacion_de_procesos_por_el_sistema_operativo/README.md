# 3.3. Planificación de procesos por el Sistema Operativo

Entonces, ¿un proceso sabe cuando tiene o no la CPU? ¿Cómo se decide qué proceso debe ejecutarse en cada momento?

Hemos visto que un **proceso**, desde su creación hasta su fin \(durante su vida\), pasa por muchos estados. Esa **transición de estados, es transparente** para él, todo **lo realiza el SO. Desde el punto de vista de un proceso, él siempre se está ejecutando en la CPU sin esperas.** Dentro de la gestión de procesos vamos a destacar dos componentes del SO que llevan a cabo toda la tarea: el cargador y el planificador.

El **cargador es el encargado de crear los procesos.** Cuando se inicia un proceso \(para cada proceso\), el cargador, realiza las siguientes tareas:

1.  **Carga el proceso en memoria principal.** Reserva un espacio en la RAM para el proceso. En ese espacio, copia las instrucciones del fichero ejecutable de la aplicación, las constantes y, deja un espacio para los datos \(variables\) y la pila \(llamadas a funciones\). **Un proceso, durante su ejecución, no podrá hacer referencia a direcciones que se encuentren fuera de su espacio de memoria;** si lo intentara, el SO lo detectará y generará una excepción \(produciendo, por ejemplo, los típicos pantallazos azules de Windows\).
2.  **Crea una estructura de información** llamada **PCB** \(Bloque de Control de Proceso\). La información del PCB, es única para cada proceso y permite controlarlo. Esta información, también la utilizará el planificador. Entre otros datos, el PCB estará formado por:
   *  **Identificador del proceso o PID**. Es un número único para cada proceso, como un DNI de proceso.
   *  **Estado actual del proceso:** en ejecución, listo, bloqueado, suspendido, finalizando.
   *  **Espacio de direcciones de memoria** donde comienza la zona de memoria reservada al proceso y su tamaño.
   *  **Información para la planificación:** prioridad, quamtum, estadísticas, ...
   *  **Información para el cambio de contexto:** valor de los registros de la CPU, entre ellos el contador de programa y el puntero a pila. Esta información es necesaria para poder cambiar de la ejecución de un proceso a otro.
   *  **Recursos utilizados.** Ficheros abiertos, conexiones, …

