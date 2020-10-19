# 6.3. Monitores

 Los monitores, nos ayudan a resolver las desventajas que encontramos en el uso de semáforos. El problema en el uso de semáforos es que, recae sobre el programador o programadora la tarea implementar el correcto uso de cada semáforo para la protección de cada recurso compartido; y, sigue estando disponible el recurso para utilizarlo sin la protección de un semáforo. Los monitores son como guardaespaldas, encargados de la protección de uno o varios recursos específicos; pero encierran esos recursos de forma que el proceso sólo puede acceder a esos recursos a través de los métodos que el monitor expone.

 Los monitores encierran en su interior los recursos o variables compartidas como componentes privadas y garantizan el acceso a ellas en exclusión mutua.

 La declaración de un **monitor incluye**:

* Declaración de las **constantes, variables, procedimientos** y **funciones** que son **privados del monitor** \(solo el monitor tiene visibilidad sobre ellos\).
* Declaración de los **procedimientos** y **funciones** que el monitor expone \(**públicos**\) y que constituyen la **interfaz a través de las que los procesos acceden al monitor**.
* **Cuerpo del monitor**, constituido por un bloque de código que se ejecuta al ser instanciado o inicializado el monitor. Su finalidad es **inicializar las variables y estructuras internas del monitor**.
* El **monitor garantiza el acceso al código interno en régimen de exclusión mutua.**
* Tiene asociada una **lista** en la que se incluyen los **procesos que al tratar de acceder al monitor son suspendidos**.

 Los paquetes Java, no proporcionan una implementación de clase `Monitor` \(habría que implementar un monitor para cada variable o recurso a sincronizar\). Pero, siempre **podemos implementarnos nuestra propia clase monitor, haciendo uso de semáforos para ello**.

 Pensemos un poco, ¿hemos utilizado objetos que pueden encajar con la declaración de un monitor aunque su tipo de dato no fuera monitor?, ¿no?, ¿seguro? Cuando realizamos una lectura o escritura en fichero, nuestro proceso queda bloqueado hasta que el sistema ha realizado completamente la operación. Nosotros inicializamos el uso del fichero indicando su ruta al crear el objeto, por ejemplo, `FileReader`; y utilizamos los métodos expuestos por ese objeto para realizar las operaciones que deseamos con ese fichero. Sin embargo, el código que realmente realiza esas operaciones es el implementado en la clase `FileReader`. Si bien, esos objetos no proporcionan exclusión mutua en los accesos al recurso; o, por lo menos, no en todos sus métodos. Aún así, podemos decir que **utilicemos objetos de tipo monitor al acceder a los recursos del sistema**, aunque no tengan como nombre Monitor.

 Las **ventajas** que proporciona el uso de monitores son:

* Uniformidad: El monitor provee una única capacidad, la exclusión mutua, no existe la confusión de los semáforos.
* Modularidad: El código que se ejecuta en exclusión mutua está separado, no mezclado con el resto del programa.
* Simplicidad: El programador o programadora no necesita preocuparse de las herramientas para la exclusión mutua .
* Eficiencia de la implementación: La implementación subyacente puede limitarse fácilmente a los semáforos.

 Y, la **desventaja**:

* Interacción de múltiples condiciones de sincronización: Cuando el número de condiciones crece, y se hacen complicadas, la complejidad del código crece de manera extraordinaria.

