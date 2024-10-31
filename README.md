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

*MQTT (Cliente-Servidor)*

-Cliente: Lámpara conectada al servidor.

-Servidor: Aplicación móvil conectada a WiFi.

-Función: Establecer conexión y comunicación con el microcontrolador (ESP32).


*PWM (Modulación por Ancho de Pulso)*

-Técnica: Transmite señales analógicas usando una señal portadora digital.

-Funcionamiento: Modifica el ciclo de trabajo de una señal periódica para controlar la energía enviada a una carga.

-Uso: Controla la intensidad de iluminación de los LEDs.


*Combinación de Colores*

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

*Características del MQTT*

-Ligero y eficiente-

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

Principales Componentes:

-Transistor de Conmutación: Actúa como un interruptor, controlando el flujo de corriente.

-Inductor: Almacena y libera energía, suavizando la salida de corriente.

-Diodo: Permite el flujo de corriente cuando el transistor está apagado.

-Capacitor: Suaviza el voltaje de salida, eliminando fluctuaciones y "ruido".

-Controlador PWM: Ajusta el ciclo de trabajo del transistor para regular el voltaje de salida.

Características Importantes

-Alta eficiencia: 85%-95%, con mínima pérdida de energía.

-Regulación de voltaje: Control preciso del voltaje de salida.

-Pequeño tamaño: Compactos y fáciles de integrar en proyectos electrónicos.


Modulo de carga (TP4056)

-Descripción: Dispositivo para cargar baterías de iones de litio (Li-Ion) o polímero de litio (Li-Po).

-Aplicación: Ideal para recargar baterías de forma segura y eficiente, ofreciendo protección contra sobrecarga, sobredescarga y cortocircuitos.

Características del Módulo TP4056

-Cargador para baterías de litio: Diseñado específicamente para Li-Ion y Li-Po.

-Voltaje de entrada: 4.5V a 5.5V (generalmente alimentado por un puerto USB de 5V).

-Corriente de carga: Ajustable, predeterminada en 1A.

Protección integrada:

-Sobrecarga, sobredescarga y cortocircuitos

Indicadores LED:

-Rojo: La batería se está cargando.

-Azul: La batería está completamente cargada.


Transistor TK14G65W 

-Descripción: Transistor IGBT de alta velocidad y alta capacidad de corriente.

Características Principales:

-Voltaje de colector-emisor (VCE): 650 V

-Corriente de colector (IC): 14 A

-Temperatura de operación máxima (Tj): 150°C

-Tensión de saturación de encendido (VCE(sat)): Aproximadamente 1.7 V a 25°C

-Frecuencia de conmutación: Alta, ideal para aplicaciones de alta velocidad

-Resistencia térmica: Mejora la disipación de calor, aumentando la fiabilidad en aplicaciones industriales


Tira LED RGB

Características principales:

LEDs RGB:

-Cada LED contiene tres chips: rojo, verde y azul.

-Control individual para mezclar y obtener el color deseado.

Control:

-Control individual o por segmentos (como en tiras WS2812B o WS2811).

Voltaje de Operación:

-Generalmente funcionan a 5V, 12V o 24V.

Controlador:

-Necesario para manipular colores y efectos.

-Uso de controladores comerciales o microcontroladores (Arduino, ESP32, Blynk).

Consumo de Corriente:

-Alto consumo, especialmente a máximo brillo.

-Fuente de alimentación adecuada es crucial.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
# 🛠️ Conclusiones finales
Los objetivos que queremos conseguir con este proyecto es aplicar todos los conocimientos que hemos adquirido con el paso de los años, además de aprender nuevos. Además de brindarle al usuario una lámpara la cual cumpla su función decorativa y de iluminación.

Desde un punto de vista profesional, hay aspectos a reconocer como bases fuertes, y otros a mejorar.

Con un capital y producción mayores a los que nosotros tenemos se podrían mejorar los siguientes puntos:

_Mejorar la estructura del código, agregando funciones que hagan más sencilla la interacción entre el usuario y la aplicación móvil.

_Mejora de la estructura física con materiales que sean más resistentes, duraderos y más lindos estéticamente.

_Crear una aplicación propia que tenga una conexión con otro broker MQTT y que permita al usuario poder tener varias lámparas conectadas en un solo dispositivo. 


_*Alumnos:*_

Canelo Lucas

Maiuro Ignacio

Medrano Nicolas

Montial Octavio

Zuñiga Juan José

_*Links:*_

Repositorio del proyecto: https://github.com/7ucu-Man/Lampara-LED-Advance

Informe del proyecto: https://docs.google.com/document/d/1hIIw9WClmCf4YHHB72maDt7cbXanECphe6KCiFOogqk/edit?tab=t.0
