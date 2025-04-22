# 🏠Sistema de iluminació publica

## Descripción General

Descripción del Proyecto: Sistema de iluminació publica
Es un sistema domótico inteligente implementado con ESP32, diseñado específicamente para un cuarto destinado para masajes dentro de una vivienda. Este sistema ofrece control y automatización de iluminación, monitoreo ambiental y seguridad, con el objetivo de proporcionar una experiencia cómoda, segura y eficiente tanto para la terapeuta como para sus clientes.

# Aplicación Real
Este proyecto está destinado a una emprendedora que ofrece servicios de masajes en un cuarto adaptado dentro de su hogar. El sistema ayuda a crear un ambiente óptimo de  trabajo, al mismo tiempo que protege el entorno y optimiza el consumo eléctrico.

# Componentes y Funcionalidades
🔌 Automatización de Luz
El sistema enciende o apaga la luz automáticamente basado en la detección de movimiento (PIR), nivel de luz ambiente (LDR) y sonido ambiental (micrófono).

Se puede controlar manualmente a través de comandos enviados por MQTT (on, off, auto), permitiendo flexibilidad al momento de recibir clientes o ajustar condiciones según necesidad.

🔔 Alarma de Seguridad
Si se detecta movimiento en horas no laborales (por ejemplo, de madrugada), se activa una alarma sonora mediante un buzzer, y se envía una alerta vía internet a través de un WebApp (Google Apps Script).

También responde a ruidos inusuales, alertando al sistema cuando se detectan sonidos fuertes.

🌐 Conectividad y Control Remoto
El sistema se conecta automáticamente al WiFi al encenderse.

Utiliza MQTT para recibir comandos y publicar estados a un broker local (por ejemplo, en una Raspberry Pi con Node-RED).

Las alertas importantes se notifican automáticamente a través de una WebApp, permitiendo monitoreo externo desde cualquier lugar.

🕹️ Modo Manual
Se puede forzar el encendido o apagado de la luz por un tiempo limitado (10 segundos) mediante comandos MQTT, muy útil cuando la terapeuta desea controlar el entorno sin depender de sensores.

🧠 Lógica Adaptativa
Durante el día, la luz se apaga si hay suficiente luz natural, ayudando a reducir el consumo eléctrico.
---

## 🎯 Objetivos del Proyecto

✅ Ambiente óptimo para ofrecer servicios profesionales.

✅ Ahorro energético con encendido automático de luz solo cuando se necesita.

✅ Seguridad mejorada mediante alarmas y notificaciones remotas.

✅ Control remoto desde el celular o computadora.

✅ Automatización no invasiva, que trabaja en segundo plano sin requerir interacción constante.



## ⚙️ Tecnologías Utilizadas

| Tecnología       | Uso Principal                                   |
|------------------|--------------------------------------------------|
| ESP32            | Microcontroladores para manejar sensores/actuadores |
| Node-RED         | Plataforma de control e interfaz web             |
| Raspberry Pi     | Máquina virtual que aloja Node-RED y PostgreSQL  |
| PostgreSQL       | Base de datos relacional para almacenamiento de datos |
| MQTT             | Protocolo de mensajería entre nodos ESP32 y Node-RED |
|Google Apps Script WebApp  | Notificaciones cuando detecta movimiento de las 12:00 am a 6:00 am|
| Impresión 3D     | Carcasas para tener buen diseño y presentación en el proyecto real  |


## ⚙️ **Tabla de Actuadores**

| **Nombre**           | **Tipo**                 | **Uso**                                                                | **Imagen** |
|----------------------|--------------------------|------------------------------------------------------------------------|------------|
| **Relevador**        | Actuador Electromecánico | Encender o apagar dispositivos de alto voltaje como lámparas           | <img src="https://github.com/user-attachments/assets/b3fb3f49-902e-4f02-838e-16978927f0e4" width="100"> |
| **Lámparas LED**     | Iluminación              | Iluminar el cuarto según el nivel de luz o manualmente                 | <img src="https://github.com/user-attachments/assets/e47e4534-3f42-4888-97f2-d46cc8ad64ef" width="100"> |
| **Alarma (Buzzer)**  | Actuador Sonoro          | Emitir alarma sonora si se detecta movimiento o sonido sospechoso      | <img src="https://github.com/user-attachments/assets/dfef9d15-3674-43f1-a72b-3b714f6f3f0e" width="100"> |
| **Pantalla LCD/OLED**| Visualización            | Mostrar datos como temperatura, estado de sensores, o alertas          | <img src="https://github.com/user-attachments/assets/9864e7f9-5cd3-45fc-9523-533060cc801c" width="100"> |

---

## 🧪 **Tabla de Sensores**

| **Nombre**            | **Tipo**                | **Uso**                                                                 | **Imagen** |
|-----------------------|-------------------------|--------------------------------------------------------------------------|------------|
| **Sensor de Luz LDR** | Fotoresistencia         | Detectar nivel de luz para activar o apagar lámparas LED                | <img src="https://github.com/user-attachments/assets/b8101240-da5d-4628-b200-595423f2ff32" width="100"> |
| **Sensor PIR**        | Infrarrojo Pasivo       | Detectar movimiento en el cuarto para activar alarma o luz              | <img src="https://github.com/user-attachments/assets/3632bf44-3ee8-4b7f-8dfa-3cb10115dfac" width="100"> |
| **Sensor DHT11**      | Temperatura y Humedad   | Medir condiciones ambientales y mostrarlas en pantalla                  | <img src="https://github.com/user-attachments/assets/da082c7a-60ed-4bc6-a186-5c08440d41c3" width="100"> |
| **Sensor de Sonido**  | Micrófono Digital       | Detectar ruidos anormales para activar una alarma                       | <img src="https://github.com/user-attachments/assets/032bcb99-a63c-4b03-a4cf-9c36933d081d" width="100"> |

--

#### Codigo Documentado .py

[🔗 Código de Thonny](https://github.com/CatalinaDM/AlumbradoIoT/blob/main/C%C3%B3digoFuente/Placa1) 


#### Flujo NodeRed
[🔗 Flujo Json](https://github.com/CatalinaDM/AlumbradoIoT/blob/main/FlujoNodeRed) 

#### Imagen de Nodos

[🔗Ver diagrama](https://github.com/CatalinaDM/AlumbradoIoT/blob/main/Nodos%20y%20Dashboard/Nodos_conexion.png) 


#### Diagrama de Conexión

[🔗Ver diagrama](https://github.com/CatalinaDM/AlumbradoIoT/blob/main/Diagrama%20de%20Conexi%C3%B3n/Captura%20de%20pantalla%202025-04-21%20165735.png) 

[🔗Ver diagrama](https://github.com/user-attachments/assets/7efebf7d-1d9d-4bff-bc62-1809e0dda987) 


<img src="https://github.com/user-attachments/assets/763471df-941a-4e41-8ddb-50eb19de184d">


#### Carcasas 
[🔗 Ver Carcasa 1](https://github.com/CatalinaDM/AlumbradoIoT/blob/main/Carcasas/Carcasas.stl) 

[🔗 Ver Carcasa 2](https://github.com/CatalinaDM/AlumbradoIoT/blob/main/Carcasas/Carcasas2.stl) 

---

## 📸 Instalación Física

<div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center; margin-top: 20px;"> <img src="https://github.com/user-attachments/assets/4df8ea1f-31ee-44a6-a3de-5d4c789c40a6" alt="Imagen 1" style="width: 300px; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.2);"> <img src="https://github.com/user-attachments/assets/ee243578-3fab-410a-8f33-38600f44963d" alt="Imagen 2" style="width: 300px; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.2);"> <img src="https://github.com/user-attachments/assets/42570bd8-5916-4985-ba0b-01f4823fff46" alt="Imagen 3" style="width: 300px; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.2);"> <img src="https://github.com/user-attachments/assets/6ab9da89-50d0-4e04-9206-b45e710d8ad3" alt="Imagen 4" style="width: 300px; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.2);"> <img src="https://github.com/user-attachments/assets/2e3ea1b0-e88f-4271-b188-73311f99a1ea" alt="Imagen 4" style="width: 300px; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.2);"> </div>
---

## 🧪 Base de Datos y Almacenamiento

<img src="">

# Funcionamiento envio correo

<img src="https://github.com/user-attachments/assets/42c5f0bb-b303-40ee-96e9-dbd8df3c49ac">
<img src="https://github.com/user-attachments/assets/904ddbe1-0760-47a6-85f1-ff5ff612aec6">
<img src="https://github.com/user-attachments/assets/a857820a-7eed-47bc-85f1-e4d7069c62b7">

#### Código de AppsScript

[🔗 Ver Code ](https://github.com/CatalinaDM/AlumbradoIoT/blob/main/AppsScript)


---

## Videos explicando el funcionamient

Link a videos

https://drive.google.com/drive/folders/1Mwg-OasbqF_vHa8ZhzucIkqC5u0zefmu?usp=drive_link

## Evidencia (Videos) de los clientes que aprueban el proyecto

Link a videos

https://drive.google.com/drive/folders/1yig3J2GGEPOLDp7m1ZyxWFej3fN-4ZA3?usp=sharing

---

## Ejecicios de Clase

Link a videos

https://drive.google.com/drive/u/2/folders/1FdQDaAN-clIueNZEJagn0WYT43Cx2bHN

## Coevaluación

# Coevaluación

##Coevaluación de Carmen Catalina Delgado Manzano para Monserrat Guadalupe Castañon Sanchez 

Monse es una persona dispuesta a apoyar en las cosas por lo que también siempre ayuda, su cualidad es que es muy detallista entonces las cosas le salen bien  y en lo que creo que deberia de mejorar es que a veces se le olvidan las cosas impoertantes, es decir no ve a futuro que podría haber consecuencia de no presentar atención en cosas que son importanes entregar. 

##Coevaluación de Carmen Catalina Delgado Manzano para Brayan Leonel Hernandez Díaz

Leo es un compañero muy adaptable, auqnue no sepa hacer ciertas cosas se esfuerza y lo intenta, entonces siempre esta disponible para avanzar en ciertas cosas. Pero en las cosas que  puede mejorar  es que se distrae mucho y se deberia de estar haciendo ciertas cosas pero se distrae y no avanza tan rapido por lo que yo creo que debería de esforzarse en mejorar más estar presente  y de una mejor calidad el trabajo. 


##Coevaluación de Monserrat Guadalupe Castañon Sanchez para Carmen Catalina Delgado Manzano
##Coevaluación de Monserrat Guadalupe Castañon Sanchez para Brayan Leonel Hernandez Díaz




##Coevaluación de Brayan Leonel Hernandez Díaz para Carmen Catalina Delgado Manzano
##Coevaluación de Brayan Leonel Hernandez Díaz para Monserrat Guadalupe Castañon Sanchez


---

## ✍️Integrantes de equipo

  - Carmen Catalina Delgado Manzano 
  - Monserrat Guadalupe Castañon Sanchez
  - Brayan Leonel Hernandez Díaz

---
