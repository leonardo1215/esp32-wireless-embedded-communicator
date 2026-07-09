ESP32 Wireless Embedded Communicator
<img width="1600" height="1200" alt="menu" src="https://github.com/user-attachments/assets/c7ca480f-d406-4432-857c-abdfbc3a5db8" />
<img width="804" height="861" alt="WhatsApp Image 2026-07-08 at 22 58 50 (1)" src="https://github.com/user-attachments/assets/fca9fb58-2fe5-4482-a445-ef1d3644c08a" />
<img width="846" height="1014" alt="WhatsApp Image 2026-07-08 at 22 58 49" src="https://github.com/user-attachments/assets/4f1ab2c4-9950-4380-801c-2adb46d50569" />
<img width="811" height="871" alt="WhatsApp Image 2026-07-08 at 22 58 48" src="https://github.com/user-attachments/assets/a5719944-0b50-4dce-9fbb-3a85fac9c4b5" />
<img width="865" height="965" alt="WhatsApp Image 2026-07-08 at 22 58 48 (1)" src="https://github.com/user-attachments/assets/83739291-4e0b-4ce0-8929-8992319a5b89" />
<img width="1200" height="1600" alt="WhatsApp Image 2026-07-08 at 22 58 51 (1)" src="https://github.com/user-attachments/assets/3e08251c-82d9-4b38-a02c-085173b6d4c1" />
# ESP32 Wireless Embedded Communicator

Sistema de comunicação embarcada desenvolvido utilizando **ESP32**, **NRF24L01** e **OLED SSD1306**, permitindo comunicação bidirecional entre dois dispositivos através de um protocolo proprietário com confirmação de entrega (ACK).

# Demonstração

## Recursos implementados

- Comunicação sem fio entre dois ESP32
- Protocolo proprietário utilizando NRF24L01
- Confirmação de entrega (ACK)
- Interface gráfica OLED
- Sistema de Menu
- Tela de Status
- Tela "Sobre"
- Feedback sonoro através de buzzer
- Tratamento de falhas de transmissão
- Comunicação Bidirecional

---

# Hardware Utilizado

| Quantidade | Componente |
|------------|------------|
| 2 | ESP32 DevKit V1 |
| 2 | NRF24L01 + Antena |
| 2 | Display OLED SSD1306 0.96" I2C |
| 2 | Push Button |
| 2 | Active Buzzer |
| 2 | Protoboard |
| Diversos | Jumpers |

---

# Pinagem

## Display OLED (SSD1306)

| OLED | ESP32 |
|------|--------|
| VCC | 3V3 |
| GND | GND |
| SDA | GPIO 21 |
| SCL | GPIO 22 |

---

## NRF24L01

| NRF24L01 | ESP32 |
|-----------|--------|
| VCC | 3V3 |
| GND | GND |
| CE | GPIO 4 |
| CSN | GPIO 5 |
| SCK | GPIO 18 |
| MOSI | GPIO 23 |
| MISO | GPIO 19 |
| IRQ | Não utilizado |

---

## Botão

| Botão | ESP32 |
|---------|--------|
| Pino 1 | GPIO 32 |
| Pino 2 | GND |

Modo utilizado:

```cpp
pinMode(32, INPUT_PULLUP);
```

---

## Buzzer

| Buzzer | ESP32 |
|----------|--------|
| Positivo | GPIO 25 |
| Negativo | GND |

---

# Ligações

```
                    ESP32

             +------------------+
             |                  |
3V3 ---------|------------------+---------------- OLED VCC
             |                  |
             |                  +---------------- NRF24L01 VCC
             |
GND ---------|------------------+---------------- OLED GND
             |                  |
             |                  +---------------- NRF24L01 GND
             |                  |
             |                  +---------------- Buzzer (-)
             |                  |
             |                  +---------------- Botão
             |
GPIO21 ------+--------------------------- OLED SDA
GPIO22 ------+--------------------------- OLED SCL

GPIO18 ------+--------------------------- NRF24L01 SCK
GPIO19 ------+--------------------------- NRF24L01 MISO
GPIO23 ------+--------------------------- NRF24L01 MOSI
GPIO4 -------+--------------------------- NRF24L01 CE
GPIO5 -------+--------------------------- NRF24L01 CSN

GPIO25 ------+--------------------------- Buzzer (+)

GPIO32 ------+--------------------------- Botão
                                         |
                                        GND
```

---

# Interface

O firmware possui uma interface gráfica desenvolvida para o display OLED.

## Tela Principal

- Quantidade de mensagens enviadas
- Quantidade de mensagens recebidas
- Mensagens entregues
- Falhas de comunicação

---

## Menu

- Enviar alerta
- Status
- Sobre
- Sair

---

## Telas do Sistema

- Enviando...
- Entregue
- Falha
- Alerta recebido
- Status
- Sobre

---

# Funcionamento

1. O usuário pressiona o botão.
2. O ESP32 transmite um pacote pelo NRF24L01.
3. O segundo dispositivo recebe a mensagem.
4. Um ACK é enviado automaticamente.
5. O dispositivo transmissor confirma a entrega.
6. O display informa o resultado da comunicação.

---

# Organização do Projeto

```
ESP32_Wireless_Embedded_Communicator/

│
├── ESP32_A/
│     └── ESP32_A.ino
│
├── ESP32_B/
│     └── ESP32_B.ino
│
├── README.md
│
└── images/
```

---

# Tecnologias

- ESP32
- NRF24L01
- Arduino Framework
- C++
- SPI
- I2C
- OLED SSD1306
- RF24 Library

---

# Próximas melhorias

- Histórico de mensagens
- Indicador de intensidade do sinal (RSSI)
- Sistema de criptografia
- Comunicação com múltiplos dispositivos
- Caixa impressa em 3D
- Firmware modular (.h / .cpp)
- Atualização OTA

---

# Autor

**Leonardo Camargo**

LinkedIn:
> https://www.linkedin.com/in/leonardocamargo12/

GitHub:
> (Adicionar link do repositório)

---

## Licença

Este projeto é distribuído sob a licença MIT.
