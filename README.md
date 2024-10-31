# LAMPARA ELECTRONICA ADVANCE



![Captura de pantalla 2024-10-29 103329](https://github.com/user-attachments/assets/93936b83-1bd0-48de-af7b-4972f1e8836e)

Nuestro proyecto consiste en una lámpara inteligente controlable a través de una aplicación móvil o una página web. La lámpara permite:

-Encendido y apagado remoto.

-Ajuste de la intensidad de luz.

-Cambio entre colores: verde, rojo, azul y blanco.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
# 📒 Indice
---------------------------------------------------------------------------------------------------------------------------------------------------------------------

⚙️ Componentes & funcionamiento

🔌 Conexiones esquematicas

📟 Software

⚡ Hardware

🛠️ Conclusiones finales

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
# ⚙️ Componentes & funcionamiento

MQTT (Cliente-Servidor)

-Cliente: Lámpara conectada al servidor.

-Servidor: Aplicación móvil conectada a WiFi.

-Función: Establecer conexión y comunicación con el microcontrolador (ESP32).


PWM (Modulación por Ancho de Pulso)

-Técnica: Transmite señales analógicas usando una señal portadora digital.

-Funcionamiento: Modifica el ciclo de trabajo de una señal periódica para controlar la energía enviada a una carga.

-Uso: Controla la intensidad de iluminación de los LEDs.


Combinación de Colores

-Aplicación: Permite cambiar el color de los LEDs (Rojo, Verde, Azul).

-Ejemplo: Para obtener Violeta, se combinan Azul y Rojo ajustando su intensidad.

-Control: Enciende/apaga LEDs principales y regula su luminosidad.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
# 🔌 Conexiones esquematicas

*ESQUEMATICO*

![Captura de pantalla 2024-10-31 135246](https://github.com/user-attachments/assets/70c51386-3b68-417f-a82d-b131e0e5ea18)



*PCB*

![WhatsApp Image 2024-10-04 at 08 14 15](https://github.com/user-attachments/assets/0681dd35-5f44-4f11-bd1c-42ff735424d8)


----------------------------------------------------------------------------------------------------------------------------------------------------------------------
# 📟 Software

Características del MQTT

Ligero y eficiente

-Requiere pocos recursos para funcionar.

-Optimiza el ancho de banda de la red.

Seguridad

-Cifra mensajes mediante TLS.

-Autenticación de clientes.

-TLS: Protocolo de seguridad que ofrece privacidad e integridad de datos para comunicaciones en internet.

Entrega de mensajes confiables

-Niveles de calidad de servicio:

-0: Como máximo una vez.

-1: Al menos una vez.

-2: Exactamente una vez.

PWM

Beneficios del Uso de PWM en el Proyecto.

Control de Intensidad Luminosa

-Ajuste preciso y continuo del brillo en cada color de la tira LED RGB y el LED blanco.

Combinación de Colores

-Mezcla de intensidades de rojo, verde y azul para obtener una amplia gama de colores personalizados.

Ahorro Energético

-Reducción del consumo energético, ya que el LED solo consume energía durante los pulsos de encendido.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
# ⚡Hardware

ESP32

-Microcontrolador con conectividad WiFi y Bluetooth.

-Popular en proyectos de IoT por su capacidad de conectarse a redes inalámbricas y su alto rendimiento.

Funciones en el Proyecto

-Control de LEDs: El ESP32 envía señales a través de un transistor MOSFET para encender (1) o apagar (0) los LEDs.

Características del ESP32 en el Proyecto

Conectividad Wi-Fi y Blynk:

-Se conecta a la red Wi-Fi usando SSID y contraseña definidos en el código.

-Utiliza la librería Blynk para control remoto y monitoreo mediante una aplicación móvil.

-La autenticación con Blynk se realiza mediante un token (BLYNK_AUTH_TOKEN).

Control de LEDs RGB:

-Pines GPIO (17, 19, 23) conectados a los canales rojo, verde y azul de los LEDs RGB.

-Control de intensidad de cada color mediante PWM (Modulación por Ancho de Pulso).

Interacción con la App Blynk:

-La app permite encender/apagar los LEDs y ajustar la intensidad de los colores mediante sliders.

-Valores de sliders enviados al ESP32 a través de pines virtuales (V1, V2, V3).

-La función analogWrite() ajusta la intensidad de cada color en los LEDs.


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


Alumnos:

Canelo Lucas

Maiuro Ignacio

Medrano Nicolas

Montial Octavio

Zuñiga Juan José

Links:

Repositorio del proyecto: https://github.com/7ucu-Man/Lampara-LED-Advance

Informe del proyecto *link del docx
