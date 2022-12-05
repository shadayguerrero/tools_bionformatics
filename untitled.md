## Screen 
Con este programa podemos crear varias instancias de la `terminal` dentro de una sola sesión. Generalmente esta herramienta es bastante util cuando estamos conectados a un servidor por `ssh` y debemos correr programas que son bastante tardados como por ejemplo `metaspades`, `kraken`, `blast`, entre otros. 
### Crear una screen
Con el comando `screen -R temporal` nos permite crear una terminal con el nombre seleccionado (temporal), esto nos permitirar conectarte nuevamente a esta screen y ver lo que dejaste en proceso.

~~~
$ screen -R temporal
~~~

En este momento estamos dentro de la terminal que se llama "temporal" y podemos poner a correr los programas que queremos. Por ejemplo, activamos un ambiente de conda *TDA* y entramos a la carpeta `GIT` como muestra a continuación
~~~
(base) shaday@betterlabub:~$ conda activate TDA
(TDA) shaday@betterlabub:~$ cd GIT/
(TDA) shaday@betterlabub:~/GIT$ pwd
/home/shaday/GIT
~~~


### Conectar y desconectar de una screen

Para desconectarme de una screen presionamos la sigueinte combinacion de teclas **Ctrl + a** y luego presionamos **d**, en nuestra pantalla aparecera la terminal donde estabamos antes de ejecutar el screen.  

~~~
(base) shaday@betterlabub:~$ screen -R temporal
[detached from 563908.temporal]
(base) shaday@betterlabub:~$ ^C
(base) shaday@betterlabub:~$ 

~~~
Podemos notar que ya no estamos en el ambiente conda de **TDA**, esto porque ya no estamos en la terminal donde lo activamos.

Para regresar a la screen debemos utilizar el comando `screen -r temporal` y retomamos lo que estaba activo en nuestra screen antes de descoenctarnos.

~~~
(base) shaday@betterlabub:~$ conda activate TDA
(TDA) shaday@betterlabub:~$ cd GIT/
(TDA) shaday@betterlabub:~/GIT$ pwd
/home/shaday/GIT
~~~

Nos desconectamos nuevamente de la screen con **Ctrl + a** y luego **d**.

### Listar las screen activas

Un comando `screen -ls` nos permite saber las screen que tenmos activas y si estan conectas o desconectadas.

~~~
(base) shaday@betterlabub:~$ screen -ls
There are screens on:
	563908.temporal	(12/05/2022 11:07:23 AM)	(Detached)
	36490.jupyter	(11/18/2022 08:36:54 AM)	(Detached)
2 Sockets in /run/screen/S-shaday.
(base) shaday@betterlabub:~$ 
~~~
 En este caso tenemos 2 screen creadas y no estamos conectadas en ninguna de ellas *(Detached)*.
 
 
 ### Finalizar una screen
 
Las screen permaneran activas hasta que las terminemos, o que se reinicie el servidor.  Para terminar una screen debemos primero conectarnos a esta screen con `screen -r temporal` y luego utiliar el comando `exit`.

~~~
(base) shaday@betterlabub:~$ screen -r temporal
There are screens on:
	563908.temporal	(12/05/2022 11:07:23 AM)	(Detached)
	36490.jupyter	(11/18/2022 08:36:54 AM)	(Detached)
2 Sockets in /run/screen/S-shaday.
(base) shaday@betterlabub:~$ 
~~~