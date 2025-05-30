# 🏠Sistema de iluminación pública

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
| **Relevador**        | Actuador Electromecánico | Encender o apagar dispositivos de alto voltaje en este caso foco LED           | <img src="https://github.com/user-attachments/assets/b3fb3f49-902e-4f02-838e-16978927f0e4" width="100"> |
| **Lámparas LED**     | Iluminación              | Iluminar el espacio de trabajo según el nivel de luz o manualmente                 | <img src="https://github.com/user-attachments/assets/e47e4534-3f42-4888-97f2-d46cc8ad64ef" width="100"> |
| **Alarma (Buzzer)**  | Actuador Sonoro          | Emitir alarma sonora si se detecta movimiento en horas sospechoso (en la madrugada)    | <img src="https://github.com/user-attachments/assets/dfef9d15-3674-43f1-a72b-3b714f6f3f0e" width="100"> |
| **Pantalla OLED**| Visualización            | Mostrar datos de temperatura     | <img src="https://github.com/user-attachments/assets/9864e7f9-5cd3-45fc-9523-533060cc801c" width="100"> |

---

## 🧪 **Tabla de Sensores**

| **Nombre**            | **Tipo**                | **Uso**                                                                 | **Imagen** |
|-----------------------|-------------------------|--------------------------------------------------------------------------|------------|
| **Sensor de Luz LDR** | Fotoresistencia         | Detectar nivel de luz para activar o apagar lámparas LED                | <img src="https://github.com/user-attachments/assets/b8101240-da5d-4628-b200-595423f2ff32" width="100"> |
| **Sensor PIR**        | Infrarrojo Pasivo       | Detectar movimiento en el espacio de trabajao  para activar alarma o luz              | <img src="https://github.com/user-attachments/assets/3632bf44-3ee8-4b7f-8dfa-3cb10115dfac" width="100"> |
| **Sensor DHT11**      | Temperatura y Humedad   | Medir condiciones ambientales y mostrarlas en pantalla                  | <img src="https://github.com/user-attachments/assets/da082c7a-60ed-4bc6-a186-5c08440d41c3" width="100"> |
| **Sensor de Sonido**  | Micrófono Digital       | Detectar ruidos fuertes para encender igualemnte la luz                     | <img src="https://github.com/user-attachments/assets/032bcb99-a63c-4b03-a4cf-9c36933d081d" width="100"> |

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

<div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center; margin-top: 20px;"> <img src="https://github.com/user-attachments/assets/d1e376f0-93d6-47e3-8b03-32ad7c39853d" alt="Imagen 1" style="width: 300px; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.2);"> <img src="https://github.com/user-attachments/assets/93414351-2323-4aaf-98e9-98f9f5aee280" alt="Imagen 2" style="width: 300px; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.2);"> <img src="https://github.com/user-attachments/assets/cecc8d70-a1be-48da-98e1-4e2ab87d5f31" alt="Imagen 3" style="width: 300px; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.2);"> </div>
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

## Videos explicando el funcionamiento


[🔗 Ver video ](https://drive.google.com/file/d/1p3uILw5T7sTr1pT9M0vrEURw72yX7NPy/view?usp=drive_link)

---

## Ejecicios de Clase

Link a videos

[🔗 Ver video ](https://drive.google.com/drive/u/2/folders/1FdQDaAN-clIueNZEJagn0WYT43Cx2bHN)


# Coevaluación

## Coevaluación de Carmen Catalina Delgado Manzano para Monserrat Guadalupe Castañon Sanchez 

(Qué hizo bien) Monse es una persona dispuesta a apoyar en las cosas por lo que también siempre ayuda, su cualidad es que es muy detallista entonces las cosas le salen bien, (Qué hizo mal) creo que en esta ocasión no haber hecho respaldo de algunos trabajos y tuvimos que volver a trabajar, (Qué puede mejorar) y en lo que creo que deberia de mejorar es que a veces se le olvidan las cosas impoertantes, es decir no ve a futuro que podría haber consecuencia de no presentar atención en cosas que son importanes entregar, además creo que deberia de expresar más su punto de vista y confiar en que sus ideas son buenas. 


## Coevaluación de Carmen Catalina Delgado Manzano para Brayan Leonel Hernandez Díaz

(Qué hizo bien) Leo es un compañero muy adaptable, auqnue no sepa hacer ciertas cosas se esfuerza y lo intenta, entonces siempre esta disponible para avanzar en ciertas cosas. (Qué puede mejorar) Pero en las cosas que  puede mejorar  es que se distrae mucho y se deberia de estar haciendo ciertas cosas pero se distrae y no avanza tan rapido por lo que yo creo que debería de esforzarse en mejorar más estar presente  y de una mejor calidad el trabajo, (Qué hizo mal)  creo que esta vez Leo se conformaba con que las cosas funconaran a medias. 


## Coevaluación de Monserrat Guadalupe Castañon Sanchez para Carmen Catalina Delgado Manzano
Qué hizo bien) Ella siempre estuvo al pendiente de todo lo que faltaba y fue muy atenta al momento de trabajar en equipo, estuvo muy dispuesta a terminar el trabajo y colaboró con nosotros en todo momento :3 (Qué hizo mal) Tal vez la puntualidad pero no era mucho, solo una que otra vez sí es la puntualidad :"v (Qué puede mejorar) Y puede mejorar en la comunicación firme de sus ideas porque siento que las decía pero con poca confianza o como no tan viable a menos de que se aprobara por los integrantes, pero sus ideas siempre son buenas y le falta firmeza al momento de decirlas uwu



## Coevaluación de Monserrat Guadalupe Castañon Sanchez para Brayan Leonel Hernandez Díaz

(Qué hizo bien) El estuvo dispuesto a prestar su casa para realizar el trabajo y estuvo a disposición de trabajar en equipo y se adaptó a realizar el proyecto a pesar de tener todo en contra :3. (Qué hizo mal) Tal vez porque sea su casa y estuvo muy cómodo pero a veces se relajaba demás o no realizaba lo principal que era el trabajo :"v. (Qué puede mejorar) Y puede mejorar en avisando qué actividades está realizando para que ninguno de los demás integrantes lo realice y sea tiempo perdido :c


## Coevaluación completa de Brayan Leonel Hernandez Díaz:
En general, nos llevamos bien como equipo. Nos supimos organizar y cada uno hizo su parte. Cati fue muy responsable con su parte, apoyando todo a tiempo y le gustaba que todo quedara bien hecho. Monse también aportó muchas ideas buenas, sobre todo en cómo dar poco de diseño al proyecto y mejorar algunos detalles. Yo (Leonel) traté de apoyar en lo que podía en algunas tareas, estar al tanto de que todo avanzara, y también apoyé en lo técnico cuando se complicaban algunas cosas.
A veces nos faltó un poco más de comunicación al repartir tareas. Hubo momentos en los que no sabíamos bien quién estaba haciendo qué, y eso nos hizo perder algo de tiempo. También dejamos algunas cosas para el final, y eso nos metió presión innecesaria.
Por otro lado Yo (Leonel) podría respetar mas las ideas y escuchas activamente para no afectar a mis compañeros 

## Coevaluación de Brayan Leonel Hernandez Díaz para Carmen Catalina Delgado Manzano
Cati puede mejorar ser un poco mas tolerante y no ser tan exigente

## Coevaluación de Brayan Leonel Hernandez Díaz para Monserrat Guadalupe Castañon Sanchez
Monse puede ser mas expresiva y opinar un poco mas y ser mas objetiva.


# AutoEvaluación

## Carmen Catalina Delgado Manzano 

Qué hizo bien : Estar al pendiente del proyecto y aportar ideas para mejorar y solucionar probemas a la hora de instalar el proyecto ya que no habiamos tomado en cuenta varias partes  como lo era tapar los cables, entonces recorde que en mi casa utilizamos algo y aporte ideas nunevas que ayuadaron, también estuve  al pendiente que cosas no funcionaban para arreglarlas. 

Qué hizo mal  : Habia cosas quen no me salian y creo que evadia hacerlas porque me estresaban mucho, también creo que a veces soy un poco estricta porque quiero que las cosas ya se acaben pronto. 

Qué puedo mojorar: Ser más paciente y cuando algo se me dificulta tratar de hacerlo para seguir aprendiendo porque a veces solo lo evito y ser más observadora. 



## Monserrat Guadalupe Castañon Sanchez
(Qué hizo bien) Estuve al pendiente de lo que faltaba aunque a veces se me pasaba y aporté ideas (algunas no se tomaron en cuenta y ya me dio penita :"c) pero estuve tratando de que el proyecto se viera bonito y funcional :3. (Qué hizo mal) Creo que soy muy distraída y que no me concentro al cien porciento en una actividad ya que cuando no me sale  la primera me bloqueo y la hago sin prestar mucha atención :"c. (Qué puede mejorar) Ser más observadora al momento de realizar tareas y estar más al pendiente de todas las actividades que falten preguntando qué tareas son las que falta por realizar y en caso de no poder realizarlas pedir ayuda a mis compañeros que están dispuestos a ayudarme en todo :3
## Brayan Leonel Hernandéz Díaz


---
# Examén Teoríco

## Carmen Catalina Delgado Manzano
<img src=""/>

## Monserrat Guadalupe Castañon Sanchez
<img src=""/>

## Brayan Leonel Hernandéz Díaz
<img src="https://github.com/user-attachments/assets/9340c0ba-7512-4037-84b9-fb7073e8b40d"/>

---

## ✍️Integrantes de equipo

  - Carmen Catalina Delgado Manzano 
  - Monserrat Guadalupe Castañon Sanchez
  - Brayan Leonel Hernandez Díaz

---
