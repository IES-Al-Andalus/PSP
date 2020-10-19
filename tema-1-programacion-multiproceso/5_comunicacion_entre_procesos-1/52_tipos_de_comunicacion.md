# 5.2. Tipos de comunicación

 Ya hemos visto que dos procesos pueden comunicarse. Remarquemos algunos conceptos fundamentales sobre comunicación.

 En cualquier comunicación, vamos a tener los siguientes **elementos**:

* **Mensaje**. Información que es el objeto de la comunicación.
* **Emisor**. Entidad que emite, genera o es origen del mensaje.
* **Receptor**. Entidad que recibe, recoge o es destinataria del mensaje.
* **Canal**. Medio por el que viaja o es enviado y recibido el mensaje.

 Podemos clasificar el **canal de comunicación** según su capacidad, y los sentidos en los que puede viajar la información, como:

* **Símplex**. La comunicación se produce en un sólo sentido. El emisor es origen del mensaje y el receptor escucha el mensaje al final del canal. Ejemplo: reproducción de una película en una sala de cine.
* **Dúplex** \(Full Duplex\). Pueden viajar mensajes en ambos sentidos simultáneamente entre emisor y receptor. El emisor es también receptor y el receptor es también emisor. Ejemplo: telefonía.
* **Semidúplex** \(Half Duplex\). El mensaje puede viajar en ambos sentidos, pero no al mismo tiempo. Ejemplo: comunicación con walkie-talkies.

 Otra clasificación dependiendo de la **sincronía** que mantengan el **emisor y** el **receptor** durante la comunicación, será:

* **Síncrona**. El emisor queda bloqueado hasta que el receptor recibe el mensaje. Ambos se sincronizan en el momento de la recepción del mensaje.
* **Asíncrona**. El emisor continúa con su ejecución inmediatamente después de emitir el mensaje, sin quedar bloqueado.
* **Invocación remota**. El proceso emisor queda suspendido hasta que recibe la confirmación de que el receptor recibido correctamente el mensaje, después emisor y receptor ejecutarán síncronamente un segmento de código común.

 Dependiendo del **comportamiento** que tengan los **interlocutores que intervienen en la comunicación**, tendremos comunicación:

* **Simétrica**. Todos los procesos pueden enviar y recibir información.
* **Asimétrica**. Sólo un proceso actúa de emisor, el resto sólo escucharán el o los mensajes.

 En nuestro anterior ejemplo básico de comunicación con sockets: el proceso `SocketEscritor`, era el emisor; el proceso `SocketLector`, era el receptor. El canal de comunicación: sockets. En el ejemplo, hemos utilizado del socket en una sola dirección y síncrona; pero los sockets permiten comunicación dúplex síncrona \(en cada sentido de la comunicación\) y simétrica \(ambos procesos pueden escribir en y leer del socket\); también existen otros tipos de sockets que nos permitirán establecer comunicaciones asimétricas asíncronas \(`DatagramSocket`\).

 En el caso del ejemplo de las tuberías, la comunicación que se establece es simplex síncrona y asimétrica.

 Nos damos cuenta, que conocer las características de la comunicación que necesitamos establecer entre procesos, nos permitirá seleccionar el canal, herramientas y comportamiento más convenientes.

