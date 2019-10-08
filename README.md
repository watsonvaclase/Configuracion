
## CONFIGURACIÓN DEL TJBOT

<br>
<br> 
<b> 1.3.	SERVICIOS DE WATSON </b> <br> <br> <br> 
<div id="texto8"> Para realizar el proyecto final del TJBot, vamos a utilizar tres servicios de Watson: Text to Speech,<br>
 Speech to Text y Watson Assistant.</div> <br> <br>
<b> 1.3.1.	TEXT TO SPEECH </b> <br> <br>
<div id="texto9"> El servicio Text to Speech proporciona una interfaz de programación de aplicaciones que utiliza  <br>
las capacidades de síntesis de voz de IBM para convertir texto escrito en voz de sonido natural. <br> <br> <br>
Para crear un servicio Text to Speech de Watson, debemos buscarlo en el catálogo de IBM Cloud. <br> <br> <br>
</div>
<img src="imagenes/Imagen13.png" id="img13"> <br> <br>
<div id="texto10"> Una vez seleccionado el servicio deseado, le damos al botón de "Crear" para poder empezar a trabajar.</div> <br> <br>
<img src="imagenes/Imagen14.png" id="img14"> <br> <br>
<div id="texto11"> Cuando ya tenemos nuestro servicio creado, podemos acceder a él desde nuestro Dashboard.</div> <br> <br>
<img src="imagenes/Imagen15.png" id="img14"> <br> <br>
<div id="texto12"> En el apartado Service credentials (credenciales del servicio) podemos ver nuestro usuario y <br>
contraseña, que necesitaremos incluir más adelantes cuando configuremos el servicio Text to <br>
Speech en nuestra Raspberry Pi3.</div> <br> <br> 
<div id="texto13"> ¡Hemos creado nuestro servicio Text to Speech! </div> <br> <br>
<b> 1.3.2.	SPEECH TO TEXT </b> <br> <br>
<div id="texto14"> Para crear un servicio Speech to Text de Watson, debemos buscarlo en el catálogo de IBM Cloud.</div> <br>
<br>
<img src="imagenes/Imagen16.png" id="img16"> <br> <br>
<div id="texto15"> Una vez seleccionado el servicio deseado, le damos al botón de "Crear" para poder empezar a trabajar.</div> <br> <br>
<img src="imagenes/Imagen17.png" id="img17"> <br> <br>
<div id="texto16"> Cuando ya tenemos nuestro servicio creado, podemos acceder a él desde nuestro Dashboard.</div> <br> <br>
<img src="imagenes/Imagen18.png" id="img18"> <br> <br>
<div id="texto17"> En el apartado Service credentials (credenciales del servicio) podemos ver nuestro usuario y <br>
contraseña, que necesitaremos incluir más adelantes cuando configuremos el servicio Speech to <br>
Text en nuestra Raspberry Pi3. </div> <br>  <br> 
<div id="texto18">¡Hemos creado nuestro servicio Speech to Text!</div> <br> <br>
<b> 1.3.3.	ASSISTANT </b> <br> <br> <br> 
<div id="texto19"> Para crear un servicio de Watson Assistant, debemos buscar el servicio deseado en el catálogo de IBM Cloud.</div> <br> <br>
<img src="imagenes/Imagen19.png" id="img19"> <br> <br>
<div id="texto20"> Una vez seleccionado el servicio Assistant, le damos al botón de "Crear" para poder empezar a trabajar.</div> <br> <br>
<img src="imagenes/Imagen20.png" id="img20"> <br> <br> <br>
<a href="https://watsonvaclase.github.io/Conversation/" > Pulsa aquí para acceder al manual de cómo crear una conversación con el servicio de Watson Assistant</a> <br> <br>
<div> Cuando ya tenemos nuestro servicio creado, podemos acceder a él desde nuestro Dashboard.<br> <br> 
Una vez la página principal de nuestro servicio, debemos buscar el botón "Launch tool" que nos llevará a la herramienta <br>
en la que configuraremos y desarrollaremos nuestra conversación. <br> <br> 
En el apartado Service credentials (credenciales del servicio) podemos ver nuestro usuario y contraseña, que <br>
 necesitaremos incluir más adelantes cuando configuremos el servicio Assistant en nuestra Raspberry Pi3. <br> <br> <br>
</div>
<b> 1.4.	CONFIGURAR A TJBOT  </b> <br> <br> <br> 
<b> 1.4.1.	CONFIGURAR LA RASPBERRY PI 3  </b> <br> <br>
Como ya hemos mencionado, Raspberry Pi es similar a un computador completo, lo que significa que se necesita un monitor, ratón y teclado para utilizarla. [1] <br> <br>
Se puede conectar a un televisor a través de un cable HDMI.
<br><br>
También será necesario conectar la Raspberry a la Wifi. <br><br>

En la mayoría de los kits Pi, la tarjeta SD ya está precargada con una imagen del sistema operativo Raspberry Pi.  <br>
Se debe colocar la tarjeta SD en la Pi, encender la Pi y seguir las instrucciones en la pantalla para completar la <br>
instalación del sistema operativo. <br><br>

Una vez tenemos todo preparado, hay que configurar los paquetes para empezar a trabajar. <br>
<br>
<br>
Abrimos un terminal en el Pi y ejecutamos los siguientes comandos para instalar la última versión de Node.js y <br>
npm (Node Package Manager). Necesitará estos paquetes más tarde para ejecutar su código. <br>

Para ello utilizamos el siguiente comando: <br> <br>

> curl -sL http://ibm.biz/tjbot-bootstrap | sudo sh - <br>

A continuación, será necesario configurar la salida de audio; el audio puede tener 2 opciones: 
 HDMI o Jack. <br>

Abrimos un terminal, y escribimos el siguiente comando, para abrir la configuración de las Raspberry: <br> <br>
> sudo raspi-config <br>

<img src="imagenes/Imagen21.png"> <br> <br>
<div> Seleccionamos "Opciones avanzadas" y luego seleccionamos "Audio". Elegimos el canal correcto <br>
para el audio de salida. Si hemos conectado un altavoz externo a la toma de audio, debemos seleccionar la toma de 3,5 mm.
</div> <br> <br> 
<img src="imagenes/Imagen22.png"> <br> <br> <br>
<b> 1.4.2.	OBTENER EL CÓDIGO PARA TJBOT </b> <br> <br>
<div> Una vez tenemos todo configurado, necesitamos descargar el código base para el TJBot. <br>
Podemos hacerlo mediante los siguientes comandos: <br>
 
> git clone https://github.com/ibmtjbot/tjbot.git <br>
> cd tjbot/recipes/conversation <br>
> npm install <br>

Una vez tenemos el código instalado, tenemos que empezar a configurar los servicios de Watson. <br>
Como ya hemos dicho, los servicios que vamos a utilizar son 3: Text to Speech, Assistant y Speech to Text. <br> <br>
</div>
<img src="imagenes/Imagen23.png"> <br> <br>
<div> Recordemos que los tres servicios estaban ya creados; ahora lo único que necesitaremos serán <br>
las credenciales para poder añadirlas al código de configuración del TJBot. <br>
Necesitamos abrir el archivo config.js para actualizar dicha información. Para ello, primero <br>
hacemos una copia del archivo original (config.default.js) mediante el siguiente comando: <br>
cp config.default.js config.js <br> <br>
Una vez hecho, abrimos el archive config.js y actualizamos las credenciales de los servicios. <br> 
Será necesaria la apikey y URL del servicio, en el caso de Watson Assistant, el WorkspaceID. <br> <br>
</div>
<img src="imagenes/Imagen25.png"> <br> <br>
<b> 1.4.3.	PROBANDO A TJBOT </b> <br>  <br> 
<div> Una vez tenemos todo configurado y la conversación creada, podemos probar a TJBot. <br>
Abrimos el terminal y ejecutamos el siguiente comando: <br>
sudo node conversation.js <br>
</div> <br>
<b> ¡Ya puedes hablar con TJBot! </b>
