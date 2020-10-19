# 1. Introducción

Cuando desarrollamos aplicaciones con comunicaciones, por ejemplo a través de Internet, debemos proporcionar seguridad tanto a la aplicación como a los datos transmitidos, ya que las operaciones que se realizan a través de la red podrían ser interceptadas, y por tanto manipuladas por personas desautorizadas.

La **seguridad de una aplicación y de los datos transmitidos** dependerá de su diseño, la selección de protocolos de comunicación y el método de autentificar al usuario.

Los **objetivos de seguridad** que debe proporcionar una aplicación con comunicaciones seguras son los siguientes:

* **Confidencialidad**. Consiste en garantizar que los datos transmitidos por la aplicación sólo van a estar disponibles para las entidades \(personas o [procesos_Proceso \(DAM\_PSP07\)_Ejemplar de un programa o aplicación en ejecución.]()\) autorizadas a acceder a dicha información. Si esos datos son interceptados por entidades desautorizadas, éstas no podrán acceder a la interpretación de esa información.
* **Integridad**. Consiste en garantizar que los datos originales no han sido modificados o alterados por alguna entidad no autorizada durante su transmisión.
* **Autenticación**. Consiste en asegurar que la entidad emisora es quien dice ser.
* **No repudio**. Consiste en asegurar que las acciones de un usuario han sido realizadas exactamente por dicho usuario. El no repudio garantiza la participación de las partes en una comunicación. En toda comunicación existe un emisor y un receptor, por lo que se pueden distinguir dos tipos de repudio:
  * **No repudio en origen**: garantiza que la persona que envía el mensaje no puede negar que es el emisor del mismo, ya que el receptor tendrá pruebas del envío.
  * **No repudio en destino**: el receptor no puede negar que recibió el mensaje, porque el emisor tiene pruebas de la recepción del mismo.
* **Autorización**. Trata de asegurar que una entidad puede realizar una acción en concreto, esto es, la autorización valida las acciones del usuario para verificar si tiene privilegios para realizar dicha acción.

Veamos los 4 primeros objetivos con un **ejemplo sencillo**:

* Cuando Antonio le envía información a Isabel, debe asegurarse de que esa información no es alterada o manipulada por el camino \(Integridad de la información transmitida\).
* La información es para Isabel, por tanto nadie más debe entender el mensaje \(Confidencialidad\).
* Debe haber alguna indicación de que el mensaje proviene de Antonio, esto es, debe haber alguna prueba de ello \(Autenticación\). La autenticación de que el mensaje proviene de Antonio es proporcionado por lo que se denomina firma digital.
* ¿Quién garantiza la identidad y la firma de Antonio? Esto se logra mediante un certificado digital, que autentica la firma de Antonio.
* Además, es igualmente importante garantizar que Antonio no pueda negar la autoría del envío del mensaje, indicando que alguien lo envío en su nombre. \(No repudio\). Este objetivo también se logra con la firma digital.

En esta unidad veremos la forma de conseguir estos objetivos de seguridad utilizando **criptografía**, uno de los pilares básicos sobre los que descansan la mayoría de las soluciones de seguridad.

Y, ¿qué es o en qué consiste la criptografía? Esto es lo que vamos a comenzar a ver en el siguiente apartado.

