# 7ucu-Man.github.io
Temeria que desaparezcan bld
Listo, ya solo queda copiar & pegar lo del informe o tomar de referencia la página de Github de Vallone

LAMPARA ELECTRONICA ADVANCE



IMAGEN DEL FINAL PROYECTO*
Nuestro proyecto se basa en una lámpara, la cual se puede controlar por medio de una aplicación móvil-página web, siendo posible determinar su encendido, apagado, como también su intensidad entre los colores que se utilizan en la lámpara: verde, rojo, azul y blaco.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
📒 Indice
----------------------------------------------------------------------------------------------------------------------------------------------------------------------

⚙️ Componentes & funcionamiento

🔌 Conexiones esquematicas

📟 Codigos y software

⚡ Ultimos cambios

🛠️ Armado final

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
⚙️ Componentes & funcionamiento

MQTT

El MQTT es un protocolo de mensajería que funciona como “Cliente - Servidor”. El cliente sería la lámpara que tiene que estar conectado al servidor y el servidor sería la app del celular que estaría conectado a wifi.
Es necesario el MQTT en el proyecto porque sirve como conexión para la comunicación con el micro controlador (ESP32)

PWM

El pwm es una técnica que se utiliza para transmitir señales analógicas cuya señal portadora será digital. En esta técnica se modifica el ciclo de trabajo de una señal periódica (una senoidal o una cuadrada, por ejemplo), ya sea para transmitir información a través de un canal de comunicaciones o para controlar la cantidad de energía que se envía a una carga.
Básicamente, consiste en activar una salida digital durante un tiempo y mantenerla apagada durante el resto, generando así pulsos positivos que se repiten de manera constante.

Combinación de colores

Mediante nuestra aplicación se puede cambiar el color de los leds además de los 3 principales (Rojo, Verde, Azul). Para eso, se regulan la intensidad de iluminación de cada led.
Ej: Si queremos Violeta, necesitamos Azul y Rojo además de la intensidad de iluminación.
En la app se puede prender y apagar los tres leds principales a tu gusto así como su fuerza de luminosidad. 

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
u
