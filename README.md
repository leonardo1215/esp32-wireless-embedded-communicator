ESP32 Wireless Embedded Communicator

Embedded communication system developed using ESP32, NRF24L01 and OLED displays.

Features
Bidirectional wireless communication
ACK protocol
OLED graphical interface
Menu system
Statistics screen
Transmission confirmation
Audible feedback
Modular firmware

Hardware

ESP32 DevKit V1 ×2
NRF24L01 ×2
OLED SSD1306 0.96" ×2
Push Button ×2
Active Buzzer ×2


ESP32 DevKit V1
Display OLED SSD1306 (I2C)
OLED	ESP32
VCC	3V3
GND	GND
SDA	GPIO 21
SCL	GPIO 22
NRF24L01

Importante: alimente em 3,3 V. Nunca use 5 V.

NRF24L01	ESP32
VCC	3V3
GND	GND
CE	GPIO 4
CSN (CS)	GPIO 5
SCK	GPIO 18
MOSI	GPIO 23
MISO	GPIO 19
IRQ	Não conectado



Botão Principal

Este botão faz:

Clique curto → Enviar alerta
Clique longo → Abrir menu

Buzzer

Você está usando buzzer ativo.

Buzzer	ESP32
+	GPIO 25
-	GND

-	Alimentação

Todos os dispositivos compartilham o mesmo GND.

ESP32 3V3
│
├── OLED
└── NRF24L01

ESP32 GND
│
├── OLED
├── NRF24L01
├── Botão
└── Buzzer


SPI do ESP32

Esses pinos são nativos do barramento SPI.

Função	GPIO
MOSI	23
MISO	19
SCK	18
I2C
Função	GPIO
SDA	21
SCL	22


<img width="1600" height="1200" alt="menu" src="https://github.com/user-attachments/assets/c7ca480f-d406-4432-857c-abdfbc3a5db8" />
<img width="804" height="861" alt="WhatsApp Image 2026-07-08 at 22 58 50 (1)" src="https://github.com/user-attachments/assets/fca9fb58-2fe5-4482-a445-ef1d3644c08a" />
<img width="846" height="1014" alt="WhatsApp Image 2026-07-08 at 22 58 49" src="https://github.com/user-attachments/assets/4f1ab2c4-9950-4380-801c-2adb46d50569" />
<img width="811" height="871" alt="WhatsApp Image 2026-07-08 at 22 58 48" src="https://github.com/user-attachments/assets/a5719944-0b50-4dce-9fbb-3a85fac9c4b5" />
<img width="865" height="965" alt="WhatsApp Image 2026-07-08 at 22 58 48 (1)" src="https://github.com/user-attachments/assets/83739291-4e0b-4ce0-8929-8992319a5b89" />
<img width="1200" height="1600" alt="WhatsApp Image 2026-07-08 at 22 58 51 (1)" src="https://github.com/user-attachments/assets/3e08251c-82d9-4b38-a02c-085173b6d4c1" />


               Diagrama elétrico
                    ESP32

             +------------------+
             |                  |
3V3 ---------|------------------+---------------- OLED VCC
             |                  |
             |                  +---------------- NRF VCC
             |
GND ---------|------------------+---------------- OLED GND
             |                  |
             |                  +---------------- NRF GND
             |                  |
             |                  +---------------- Buzzer (-)
             |                  |
             |                  +---------------- Botão
             |
GPIO21 ------+--------------------------- OLED SDA
GPIO22 ------+--------------------------- OLED SCL

GPIO18 ------+--------------------------- NRF SCK
GPIO19 ------+--------------------------- NRF MISO
GPIO23 ------+--------------------------- NRF MOSI
GPIO4 -------+--------------------------- NRF CE
GPIO5 -------+--------------------------- NRF CSN

GPIO25 ------+--------------------------- Buzzer (+)

GPIO32 ------+--------------------------- Botão
                                         |
                                        GND


