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

*MQTT*

_Características del MQTT_

-Ligero y eficiente

-Requiere pocos recursos para funcionar.

-Optimiza el ancho de banda de la red.

_Seguridad_

-Cifra mensajes mediante TLS.

-Autenticación de clientes.

-TLS: Protocolo de seguridad que ofrece privacidad e integridad de datos para comunicaciones en internet.

_Entrega de mensajes confiables_

-Niveles de calidad de servicio:

-0: Como máximo una vez; 1: Al menos una vez; 2: Exactamente una vez.

*PWM*

_Beneficios del Uso de PWM en el Proyecto:_

_Control de Intensidad Luminosa_

-Ajuste preciso y continuo del brillo en cada color de la tira LED RGB y el LED blanco.

_Combinación de Colores_

-Mezcla de intensidades de rojo, verde y azul para obtener una amplia gama de colores personalizados.

_Ahorro Energético_

-Reducción del consumo energético, ya que el LED solo consume energía durante los pulsos de encendido.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------
# ⚡Hardware

*ESP32*

-Microcontrolador con conectividad WiFi y Bluetooth.

-Popular en proyectos de IoT por su capacidad de conectarse a redes inalámbricas y su alto rendimiento.

_Funciones en el Proyecto_

-Control de LEDs: El ESP32 envía señales a través de un transistor MOSFET para encender (1) o apagar (0) los LEDs.

_Características del ESP32 en el Proyecto_

_Conectividad Wi-Fi y Blynk:_

-Se conecta a la red Wi-Fi usando SSID y contraseña definidos en el código.

-Utiliza la librería Blynk para control remoto y monitoreo mediante una aplicación móvil.

-La autenticación con Blynk se realiza mediante un token (BLYNK_AUTH_TOKEN).

_Control de LEDs RGB:_

-Pines GPIO (17, 19, 23) conectados a los canales rojo, verde y azul de los LEDs RGB.

-Control de intensidad de cada color mediante PWM (Modulación por Ancho de Pulso).

_Interacción con la App Blynk:_

-La app permite encender/apagar los LEDs y ajustar la intensidad de los colores mediante sliders.

-Valores de sliders enviados al ESP32 a través de pines virtuales (V1, V2, V3).

-La función analogWrite() ajusta la intensidad de cada color en los LEDs.


*Step-Down*

_Principales Componentes:_

-Transistor de Conmutación: Actúa como un interruptor, controlando el flujo de corriente.

-Inductor: Almacena y libera energía, suavizando la salida de corriente.

-Diodo: Permite el flujo de corriente cuando el transistor está apagado.

-Capacitor: Suaviza el voltaje de salida, eliminando fluctuaciones y "ruido".

-Controlador PWM: Ajusta el ciclo de trabajo del transistor para regular el voltaje de salida.

_Características Importantes_

-Alta eficiencia: 85%-95%, con mínima pérdida de energía.

-Regulación de voltaje: Control preciso del voltaje de salida.

-Pequeño tamaño: Compactos y fáciles de integrar en proyectos electrónicos.


*Modulo de carga (TP4056)*

-Descripción: Dispositivo para cargar baterías de iones de litio (Li-Ion) o polímero de litio (Li-Po).

-Aplicación: Ideal para recargar baterías de forma segura y eficiente, ofreciendo protección contra sobrecarga, sobredescarga y cortocircuitos.

_Características_

-Cargador para baterías de litio: Diseñado específicamente para Li-Ion y Li-Po.

-Voltaje de entrada: 4.5V a 5.5V (generalmente alimentado por un puerto USB de 5V).

-Corriente de carga: Ajustable, predeterminada en 1A.

_Protección integrada:_

-Sobrecarga, sobredescarga y cortocircuitos

_Indicadores LED:_

-Rojo: La batería se está cargando.

-Azul: La batería está completamente cargada.


*Transistor TK14G65W*

-Descripción: Transistor de alta velocidad y alta capacidad de corriente.

_Características Principales:_

-Voltaje de colector-emisor (VCE): 650 V

-Corriente de colector (IC): 14 A

-Temperatura de operación máxima (Tj): 150°C

-Tensión de saturación de encendido (VCE(sat)): Aproximadamente 1.7 V a 25°C

-Frecuencia de conmutación: Alta, ideal para aplicaciones de alta velocidad

-Resistencia térmica: Mejora la disipación de calor, aumentando la fiabilidad en aplicaciones industriales


*Tira LED RGB*

_Características principales:_

_LEDs RGB:_

-Cada LED contiene tres chips: rojo, verde y azul.

-Control individual para mezclar y obtener el color deseado.

_Control:_

-Control individual o por segmentos (como en tiras WS2812B o WS2811).

_Voltaje de Operación:_

-Generalmente funcionan a 5V, 12V o 24V.

_Controlador:_

-Necesario para manipular colores y efectos.

-Uso de controladores comerciales o microcontroladores (Arduino, ESP32, Blynk).

_Consumo de Corriente:_

-Alto consumo, especialmente a máximo brillo.

-Fuente de alimentación adecuada es crucial.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
# 🛠️ Conclusiones finales
Los objetivos que queremos conseguir con este proyecto es aplicar todos los conocimientos que hemos adquirido con el paso de los años, además de aprender nuevos. Además de brindarle al usuario una lámpara la cual cumpla su función decorativa y de iluminación.

Desde un punto de vista profesional, hay aspectos a reconocer como bases fuertes, y otros a mejorar.
Como tener bases sólidas en conocimientos y diseño actual.

Áreas de mejora: Código: Mejorar estructura y agregar funciones para una interacción más sencilla; estructura física: Usar materiales más resistentes y estéticamente agradables; aplicación propia: Desarrollar una app con conexión a otro broker MQTT, permitiendo controlar varias lámparas desde un solo dispositivo.


_*Alumnos:*_

Canelo Lucas

Maiuro Ignacio

Medrano Nicolas

Montial Octavio

Zuñiga Juan José

_*Links:*_

Repositorio del proyecto: https://github.com/7ucu-Man/Lampara-LED-Advance

Informe del proyecto: https://docs.google.com/document/d/1hIIw9WClmCf4YHHB72maDt7cbXanECphe6KCiFOogqk/edit?tab=t.0
