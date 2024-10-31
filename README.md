# LAMPARA ELECTRONICA ADVANCE



![Captura de pantalla 2024-10-29 103329](https://github.com/user-attachments/assets/93936b83-1bd0-48de-af7b-4972f1e8836e)

Nuestro proyecto consiste en una lámpara inteligente controlable a través de una aplicación móvil o una página web. La lámpara permite:

-Encendido y apagado remoto.

-Ajuste de la intensidad de luz.

-Cambio entre colores: verde, rojo, azul y blanco.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
# 📒 Indice
---------------------------------------------------------------------------------------------------------------------------------------------------------------------

⚙️ Componentes utilizados

🔌 Esquemático y PCB

📟 Software

⚡ Hardware

🛠️ Conclusiones finales

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
# ⚙️ Componentes utilizados

Los componentes principales utilizados para el desarrollo del proyecto:

-MQTT (Clienete-servidor)

-PWM (Modulación por ancho de pulso)

-ESP32

-Step-down

-Modulo de carga (TP4056)

-Transistor TK14G65W

-Tira LED RGB

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
# 🔌 Esquemático y PCB

*ESQUEMATICO*

![Captura de pantalla 2024-10-31 135246](https://github.com/user-attachments/assets/70c51386-3b68-417f-a82d-b131e0e5ea18)



*PCB*

![WhatsApp Image 2024-10-04 at 08 14 15](https://github.com/user-attachments/assets/0681dd35-5f44-4f11-bd1c-42ff735424d8)


----------------------------------------------------------------------------------------------------------------------------------------------------------------------
# 📟 Software

*MQTT*

-Cliente: Lámpara conectada al servidor.

-Servidor: Aplicación móvil conectada a WiFi.

-Función: Establecer conexión y comunicación con el microcontrolador (ESP32).


*Conectividad Wi-Fi y Blynk (ESP32)*

_Conexión a Wi-Fi:_

-El ESP32 se conecta usando el SSID y la contraseña definidos en el código.

_Interacción con la App:_

-Utiliza la librería Blynk para controlar y monitorear dispositivos remotamente.

-Autenticación mediante token (BLYNK_AUTH_TOKEN) para asociar el ESP32 con la aplicación en la nube.

_Interacción con la App Blynk_

_Control de LEDs:_

-Botón en la app para encender/apagar los LEDs.

-Sliders para controlar la intensidad de los colores rojo, verde y azul.

_Envío de Valores:_

-Valores de sliders enviados al ESP32 a través de pines virtuales (V1: rojo, V2: verde, V3: azul).

-Función analogWrite() ajusta la intensidad de cada color en los LEDs.


*PWM*

_Beneficios del Uso de PWM en el Proyecto:_

-Control de Intensidad Luminosa: ajuste preciso y continuo del brillo en cada color de la tira LED RGB y el LED blanco.

-Combinación de Colores: mezcla de intensidades de rojo, verde y azul para obtener una amplia gama de colores personalizados.

-Ahorro Energético: reducción del consumo energético, ya que el LED solo consume energía durante los pulsos de encendido.



*Combinación de Colores*

-Aplicación: Permite cambiar el color de los LEDs (Rojo, Verde, Azul).

-Ejemplo: Para obtener Violeta, se combinan Azul y Rojo ajustando su intensidad.

-Control: Enciende/apaga LEDs principales y regula su luminosidad.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
# ⚡Hardware

*ESP32*

-Microcontrolador con conectividad WiFi y Bluetooth.

-Popular en proyectos de IoT por su capacidad de conectarse a redes inalámbricas y su alto rendimiento.

_Funciones en el Proyecto_

-Control de LEDs: El ESP32 envía señales a través de un transistor MOSFET para encender (1) o apagar (0) los LEDs.


*Step-Down*

_Principales Componentes:_

-Transistor de Conmutación: Actúa como un interruptor, controlando el flujo de corriente.

-Inductor: Almacena y libera energía, suavizando la salida de corriente.

-Diodo: Permite el flujo de corriente cuando el transistor está apagado.

-Capacitor: Suaviza el voltaje de salida, eliminando fluctuaciones y "ruido".

-Controlador PWM: Ajusta el ciclo de trabajo del transistor para regular el voltaje de salida.


*Modulo de carga (TP4056)*

-Descripción: Dispositivo para cargar baterías de iones de litio (Li-Ion) o polímero de litio (Li-Po).

-Aplicación: Ideal para recargar baterías de forma segura y eficiente, ofreciendo protección contra sobrecarga, sobredescarga y cortocircuitos.


*Transistor TK14G65W*

-Descripción: Transistor de alta velocidad y alta capacidad de corriente.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
# 🛠️ Conclusiones finales
Los objetivos que queremos conseguir con este proyecto es aplicar todos los conocimientos que hemos adquirido con el paso de los años, además de aprender nuevos. Además de brindarle al usuario una lámpara la cual cumpla su función decorativa y de iluminación.

Desde un punto de vista profesional, hay aspectos a reconocer como bases fuertes, y otros a mejorar.
Como tener bases sólidas en conocimientos y diseño actual.

Áreas de mejora: el código: mejorar estructura y agregar funciones para una interacción más sencilla; estructura física: usar materiales más resistentes y estéticamente agradables; aplicación propia: desarrollar una app con conexión a otro broker MQTT, permitiendo controlar varias lámparas desde un solo dispositivo.


*Alumnos:*

Canelo Lucas

Maiuro Ignacio

Medrano Nicolas

Montial Octavio

Zuñiga Juan José

*Links:*

Repositorio del proyecto: https://github.com/7ucu-Man/Lampara-LED-Advance

Informe del proyecto: https://docs.google.com/document/d/1hIIw9WClmCf4YHHB72maDt7cbXanECphe6KCiFOogqk/edit?tab=t.0
