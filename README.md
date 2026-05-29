# TerraByte 🌱🚜

Sistema IoT para monitoramento inteligente de uma estufa agrícola utilizando ESP32, sensores ambientais, MQTT, Node-RED, OLED e banco de dados SQLite.

## 📌 Sobre o Projeto

O TerraByte é uma estufa inteligente desenvolvida para monitorar em tempo real as condições ambientais necessárias para o cultivo de plantas.

O projeto utiliza sensores conectados a um ESP32 para identificar:

- Temperatura ambiente
- Umidade do ar
- Luminosidade
- Pressão atmosférica
- Altitude

As informações são enviadas em tempo real utilizando o protocolo MQTT e exibidas em um dashboard no Node-RED, além de serem armazenadas em banco de dados SQLite para geração de histórico.

O sistema também possui um display OLED para visualização local dos dados e LEDs para indicar o status de funcionamento da estufa.

---

## ⚙️ Funcionalidades

* 🌡️ Monitoramento de temperatura
* 💧 Monitoramento de umidade do ar
* ☀️ Monitoramento de luminosidade
* 🌎 Monitoramento de pressão atmosférica
* ⛰️ Monitoramento de altitude
* 📡 Comunicação MQTT
* 💾 Armazenamento em banco SQLite
* 📊 Dashboard interativo no Node-RED
* 📜 Histórico de registros utilizando tabela dinâmica
* 🖥️ Exibição de informações em display OLED
* 🟢 LED verde para funcionamento normal
* 🔴 LED vermelho para indicação de falhas
* 🕒 Sincronização automática de horário via NTP

---

## 🛠️ Tecnologias Utilizadas

### Hardware

* ESP32
* Sensor DHT22
* Sensor LDR
* Sensor BMP180
* Display OLED SSD1306
* LED Vermelho
* LED Verde
* Protoboard
* Resistores

### Software

* Arduino IDE
* Node-RED
* SQLite
* MQTT
* HiveMQ Cloud
* Wokwi

### Linguagens

* C++
* SQL
* JavaScript

---

## 🔌 Estrutura do Sistema

ESP32 + Sensores
(DHT22 + LDR + BMP180)
        →
     MQTT
        →
   HiveMQ Cloud
        →
    Node-RED
        →
 Dashboard + SQLite

---

## 📡 Tópicos MQTT

| Tópico | Função |
|---------|---------|
| estufa/dht22/temperatura | Temperatura do ambiente |
| estufa/dht22/umidade | Umidade do ar |
| estufa/ldr/luminosidade | Intensidade luminosa |
| estufa/bmp180/temperatura | Temperatura do BMP180 |
| estufa/bmp180/pressao | Pressão atmosférica |
| estufa/bmp180/altitude | Altitude calculada |
| estufa/status | Status geral do sistema |
| estufa/erro | Mensagens de erro |

---

## 🚀 Instruções de Uso

### 🔌 1. Configuração do ESP32

Conectar os sensores e componentes:

- DHT22
- LDR
- BMP180
- Display OLED
- LED Verde
- LED Vermelho

(Carregue o código disponível no repositório.)

---

### 📡 2. Configurar o MQTT

Configure no código:

```cpp
const char* MQTT_SERVER = "seu_servidor_hivemq";
const int MQTT_PORT = 8883;
```

Informe também:

- Usuário MQTT
- Senha MQTT

---

### 📊 3. Executar o Node-RED

Importe o fluxo do Node-RED presente no repositório.

Configure:

- Conexão MQTT
- Banco SQLite
- Dashboard

---

### ▶️ 4. Iniciar o Sistema

Após iniciar:

- O ESP32 conectará ao Wi-Fi
- Conectará ao HiveMQ Cloud
- Iniciará a leitura dos sensores
- Enviará os dados automaticamente

O dashboard exibirá:

- Status do sistema
- Temperatura
- Umidade
- Luminosidade
- Pressão atmosférica
- Altitude
- Histórico de registros

---

## 🗄️ Banco de Dados

O projeto utiliza SQLite para armazenar os registros do monitoramento.

Exemplo de consulta SQL:

```sql
SELECT
    data_hora,
    umidade,
    luminosidade,
    temperatura,
    pressao,
    altitude
FROM historico_estufa
ORDER BY id DESC;
```

---

## 📊 Dashboard

O dashboard do Node-RED apresenta:

📍 Status do sistema

💧 Umidade

☀️ Luminosidade

🌡️ Temperatura

🌎 Pressão atmosférica

⛰️ Altitude

📜 Histórico em tabela dinâmica

📈 Indicadores gráficos (gauges)

---

## 📈 Resultados Parciais

### Até o momento, o sistema foi capaz de:

- realizar conexão Wi-Fi com ESP32
- conectar ao HiveMQ Cloud utilizando MQTT seguro
- monitorar temperatura e umidade utilizando DHT22
- monitorar luminosidade utilizando LDR
- monitorar pressão atmosférica e altitude utilizando BMP180
- registrar horários utilizando NTP
- armazenar informações em banco SQLite
- exibir dados em dashboard em tempo real
- exibir informações em display OLED
- gerar histórico organizado utilizando ui_table
- indicar falhas através dos LEDs de status

Os testes realizados no Wokwi e no Node-RED apresentaram funcionamento estável na comunicação entre os componentes do sistema.

---

## 🧪 Simulação

O projeto foi desenvolvido e testado utilizando a plataforma Wokwi para simulação do ESP32 e sensores.

---

## 👩‍💻 Time

### Carolina Nascimento Gonçalves
RM564786 - 2TDSPJ

### Julia Sayuri Kina
RM564555 - 2TDSPJ

### Emanuelly Ventura do Nascimento
RM562339 - 2TDSPJ

---

## 🌱 TerraByte

Tecnologia e agricultura conectadas para tornar o cultivo mais inteligente, sustentável e eficiente.
