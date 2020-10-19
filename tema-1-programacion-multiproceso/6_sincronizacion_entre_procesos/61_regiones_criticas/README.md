# 6.1. Regiones críticas

 La definición común, y que habíamos visto anteriormente, de una región o sección crítica, es, el **conjunto de instrucciones en las que un proceso accede a un recurso compartido**. Para que la definición sea correcta, añadiremos que, las instrucciones que forman esa región crítica, **se ejecutarán de forma indivisible o atómica y de forma exclusiva con respecto a otros procesos que accedan al mismo recurso** compartido al que se está accediendo.

 Al identificar y definir nuestras regiones críticas en el código, tendremos en cuenta:

* **Se protegerán con secciones críticas sólo aquellas instrucciones que acceden a un recurso compartido.**
* Las **instrucciones que forman una sección crítica, serán las mínimas**. Incluirán sólo las instrucciones imprescindibles que deban ser ejecutadas de forma atómica.
* Se pueden **definir tantas secciones críticas como sean necesarias**.
* **Un único proceso entra en su sección crítica.** El **resto de procesos esperan** a que éste salga de su sección crítica. El resto de procesos esperan, porque encontrarán el **recurso bloqueado**. El proceso que está en su sección crítica, es el que ha bloqueado el recurso.
* Al **final de cada sección crítica**, el **recurso** debe ser **liberado** para que puedan utilizarlo otros procesos.

 Algunos lenguajes de programación permiten definir bloques de código como secciones críticas. Estos lenguajes, cuentan con palabras reservadas específicas para la definición de estas regiones. En Java, veremos cómo definir este tipo de regiones a nivel de hilo en posteriores unidades.

 A nivel de procesos, lo primero, haremos, que nuestro ejemplo de accesos múltiples a un fichero, sea correcto para su ejecución en un entorno concurrente. En esta presentación identificaremos la sección o secciones críticas y qué objetos debemos utilizar para conseguir que esas secciones se ejecuten de forma excluyente.

 En nuestro ejemplo, hemos visto cómo definir una sección crítica para proteger las actualizaciones de un fichero. **Cualquier actualización de datos en un recurso compartido, necesitará establecer una región crítica que implicará como mínimo** estas instrucciones:

* **Leer el dato que se quiere actualizar.** Pasar el dato a la zona de memoria local al proceso.
* **Realizar el cálculo de actualización.** Modificar el dato en memoria.
* **Escribir el dato actualizado.** Llevar el dato modificado de memoria al recurso compartido.

 Debemos darnos cuenta de que nos referimos a un recurso compartido de forma genérica, ese recurso compartido podrá ser: memoria principal, fichero, base de datos, etc.

