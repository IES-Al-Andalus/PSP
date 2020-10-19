# 6.5. Cola de mensajes

 El paso de mensajes es una **técnica** empleada en programación concurrente para aportar **sincronización entre procesos y permitir la exclusión mutua**, de manera similar a como se hace con los semáforos, monitores, etc. Su principal característica es que **no precisa de memoria compartida**.

 Los **elementos principales** que intervienen en el paso de mensajes son el **proceso** que **envía**, el que **recibe** y el **mensaje**.

 Dependiendo de si el proceso que envía el mensaje espera a que el mensaje sea recibido, se puede hablar de paso de mensajes síncrono o asíncrono:

* En el **paso de mensajes asíncrono**, el proceso que envía, **no espera a que el mensaje sea recibido**, y continúa su ejecución, siendo posible que vuelva a generar un nuevo mensaje y a enviarlo antes de que se haya recibido el anterior. Por este motivo se suelen emplear **buzones o colas**, en los que se **almacenan los mensajes a espera de que un proceso los reciba**. Generalmente empleando este sistema, el proceso que envía mensajes sólo se bloquea o para, cuando finaliza su ejecución, o si el buzón está lleno. Para conseguir esto, estableceremos una serie de **reglas de comunicación** \(o protocolo\) entre emisor y receptor, de forma que el **receptor** pueda **indicar al emisor qué capacidad restante** queda en su cola de mensajes y si está lleno o no.
* En el **paso de mensajes síncrono**, el proceso que envía el mensaje **espera a que un proceso lo reciba** para continuar su ejecución. Por esto se suele llamar a esta técnica encuentro, o rendezvous. Dentro del paso de mensajes síncrono se engloba a la **llamada a procedimiento remoto** \(RPC\), muy popular en las arquitecturas cliente/servidor.

 Veremos cómo implementar sincronización de procesos con paso de mensajes en las unidades 3, 4 y 5.

