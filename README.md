# 7ucu-Man.github.io
Temeria que desaparezcan bld
Listo, ya solo queda copiar & pegar lo del informe o tomar de referencia la página de Github de Vallone

LAMPARA ELECTRONICA ADVANCE



![Captura de pantalla 2024-10-29 103329](https://github.com/user-attachments/assets/93936b83-1bd0-48de-af7b-4972f1e8836e)

Nuestro proyecto se basa en una lámpara, la cual se puede controlar por medio de una aplicación móvil-página web, siendo posible determinar su encendido, apagado, como también su intensidad entre los colores que se utilizan en la lámpara: verde, rojo, azul y blaco.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
📒 Indice
----------------------------------------------------------------------------------------------------------------------------------------------------------------------

⚙️ Componentes & funcionamiento

🔌 Conexiones esquematicas

📟 Codigos y software

⚡ Hardware

🛠️ Conclusiones finales

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
🔌 Conexiones esquematicas

ESQUEMATICO
*IMAGEN

PCB
*IMAGEN
----------------------------------------------------------------------------------------------------------------------------------------------------------------------
📟 Codigos y software

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
⚡Hardware

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
🛠️ Conclusiones finales
Los objetivos que queremos conseguir con este proyecto es aplicar todos los conocimientos que hemos adquirido con el paso de los años, además de aprender nuevos. Además de brindarle al usuario una lámpara la cual cumpla su función decorativa y de iluminación.

Desde un punto de vista profesional, hay aspectos a reconocer como bases fuertes, y otros a mejorar.

Con un capital y producción mayores a los que nosotros tenemos se podrían mejorar los siguientes puntos:

_Mejorar la estructura del código, agregando funciones que hagan más sencilla la interacción entre el usuario y la aplicación móvil.
_Mejora de la estructura física con materiales que sean más resistentes, duraderos y más lindos estéticamente.
_Crear una aplicación propia que tenga una conexión con otro broker MQTT y que permita al usuario poder tener varias lámparas conectadas en un solo dispositivo. 


Ultima seccion, adjuntar PDF del proyecto y repositorio Github
