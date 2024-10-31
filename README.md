# LAMPARA ELECTRONICA ADVANCE



![Captura de pantalla 2024-10-29 103329](https://github.com/user-attachments/assets/93936b83-1bd0-48de-af7b-4972f1e8836e)

Nuestro proyecto se basa en una lámpara, la cual se puede controlar por medio de una aplicación móvil-página web, siendo posible determinar su encendido, apagado, como también su intensidad entre los colores que se utilizan en la lámpara: verde, rojo, azul y blaco.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
# 📒 Indice
---------------------------------------------------------------------------------------------------------------------------------------------------------------------

- ⚙️ Componentes & funcionamiento

- 🔌 Conexiones esquematicas

- 📟 Software

- ⚡ Hardware

- 🛠️ Conclusiones finales

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
# ⚙️ Componentes & funcionamiento

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
# 🔌 Conexiones esquematicas

*ESQUEMATICO*

![Captura de pantalla 2024-10-31 135246](https://github.com/user-attachments/assets/70c51386-3b68-417f-a82d-b131e0e5ea18)



*PCB*

![WhatsApp Image 2024-10-04 at 08 14 15](https://github.com/user-attachments/assets/0681dd35-5f44-4f11-bd1c-42ff735424d8)


----------------------------------------------------------------------------------------------------------------------------------------------------------------------
📟 Software

MQTT

Características del MQTT

_Ligero y eficiente: Los clientes MQTT requieren pocos recursos para poder funcionar y optimizar el ancho de banda de la red.

_Seguridad: El MQTT facilita el cifrado de mensajes mediante TLS y la autenticación de clientes.

_TLS: es un protocolo de seguridad que ofrece privacidad e integridad de datos para las comunicaciones de internet.

_Entrega de mensajes confiables: El MQTT tiene 3 niveles de calidad de servicio:

0: Como máximo una vez

1: Al menos una vez

2: exactamente una vez

PWM

Beneficios del Uso de PWM en el Proyecto.

_El uso de PWM para el control de los LEDs permite un ajuste preciso de la intensidad luminosa sin necesidad de variar el voltaje de alimentación, lo cual es más eficiente en términos energéticos y simplifica el diseño del circuito. Mediante PWM, el proyecto ofrece:

_Control de Intensidad Luminosa: Ajuste continuo de brillo en cada color de la tira LED RGB y del LED blanco.

_Combinación de Colores: Mediante la mezcla de intensidades de rojo, verde y azul, es posible obtener una amplia gama de colores personalizados.

_Ahorro Energético: La técnica PWM reduce el consumo energético, ya que el LED solo consume energía durante los pulsos de encendido.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
# ⚡Hardware

ESP32
Características del ESP32 en el proyecto:

 1. Conectividad Wi-Fi y Blynk:

_El ESP32 se conecta a tu red Wi-Fi utilizando el SSID y la contraseña que defines en el código.

_Utiliza la librería Blink para interactuar con una aplicación en tu smartphone. Blynk permite controlar y monitorear dispositivos de forma remota.

_La autenticación con Blink se hace mediante un token (BLYNK_AUTH_T0KEN), lo que permite asociar tu ESP32 con la aplicación en la nube de Blynk.

 2. Control de LEDs RGB:

_Los pines GPIO del ESP32 (pines 17, 19 y 23) están conectados a los canales rojo, verde y azul de los LEDs RGB, respectivamente. Estos pines controlan la intensidad de cada color mediante PWM.

_PWM (Modulación por ancho de pulso): El ESP32 ajusta la cantidad de corriente que pasa a cada color de los LEDs. Al variar el ciclo de trabajo del PWM (un valor entre 0 y 255), puedes cambiar la intensidad del rojo, verde y azul, logrando diferentes colores combinados.

 3. Interacción con la App Blynk:

_Desde la app de Blink, tienes un botón que enciende o apaga los LEDs, y sliders (deslizadores) que controlan la intensidad de los colores rojo, verde y azul.

_Los valores de los sliders se envían desde la app Blink al ESP32 mediante los pines virtuales V1 (rojo), V2 (verde) y V3 (azul).

_Cada vez que cambias un slider en la app, el valor se envía al ESP32, y la función “analogWrite( )” ajusta la intensidad de cada color en los LEDs.



Step-Down

_Alta eficiencia: Los convertidores Step Down suelen tener una eficiencia del 85% al 95%, lo que significa que se pierde muy poca energía en forma de calor.

_Regulación de voltaje: Estos dispositivos permiten un control preciso del voltaje de salida.

_Pequeño tamaño: Son compactos y fáciles de integrar en proyectos electrónicos.


Modulo de carga (TP4056)

_Cargador para baterías de litio: Diseñado específicamente para cargar baterías de iones de litio (Li-Ion) o de polímero de litio (Li-Po).

_Voltaje de entrada: 4.5V a 5.5V, comúnmente alimentado por un puerto USB (5V).

_Corriente de carga: Ajustable, con un valor predeterminado de 1A.

_Protección integrada: Protección contra sobrecarga, sobredescarga y cortocircuitos. Esto lo hace muy seguro para baterías de litio, que son más sensibles a la sobrecarga y sobredescarga.

_Indicadores LED: Tiene dos LEDs que indican el estado de la carga:

-Rojo: La batería se está cargando.

-Azul: La batería está completamente cargada. 


Tira led RGB

Características principales:

_LEDs RGB: Cada LED en la tira contiene tres chips LED: uno rojo, uno verde y uno azul. Estos se controlan individualmente para mezclar los colores y obtener el color deseado.

_Control individual o en segmentos: Algunas tiras RGB permiten el control individual de cada LED (tiras direccionables como las WS2812B o WS2811), mientras que en otras la tira se controla en segmentos, lo que significa que todos los LEDs en una sección específica cambiarán al mismo color.

_Voltaje de operación: Las tiras de LEDs RGB generalmente funcionan a 5V, 12V o 24V, dependiendo del tipo y fabricante.

_Controlador: Para manipular los colores y los efectos de la tira, se necesita un controlador. Puedes utilizar controladores comerciales o microcontroladores como el Arduino, ESP32, o plataformas como Blynk para tener control remoto.

_Consumo de corriente: Las tiras RGB consumen una cantidad significativa de corriente, especialmente cuando están encendidas al máximo brillo. Es importante asegurarse de que la fuente de alimentación sea adecuada para soportar el consumo.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
# 🛠️ Conclusiones finales
Los objetivos que queremos conseguir con este proyecto es aplicar todos los conocimientos que hemos adquirido con el paso de los años, además de aprender nuevos. Además de brindarle al usuario una lámpara la cual cumpla su función decorativa y de iluminación.

Desde un punto de vista profesional, hay aspectos a reconocer como bases fuertes, y otros a mejorar.

Con un capital y producción mayores a los que nosotros tenemos se podrían mejorar los siguientes puntos:

_Mejorar la estructura del código, agregando funciones que hagan más sencilla la interacción entre el usuario y la aplicación móvil.

_Mejora de la estructura física con materiales que sean más resistentes, duraderos y más lindos estéticamente.

_Crear una aplicación propia que tenga una conexión con otro broker MQTT y que permita al usuario poder tener varias lámparas conectadas en un solo dispositivo. 


*Ultima seccion, adjuntar PDF del proyecto y repositorio Github*
