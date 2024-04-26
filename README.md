
# CP-2-Edge


# Projeto de Monitoramento com Arduino
 
Este projeto utiliza um Arduino para monitorar dados de temperatura, umidade e distância, empregando um sensor DHT11 e um sensor ultrassônico HC-SR04. Os dados são lidos a cada 4 segundos e enviados via porta serial em formato JSON.
 
## Componentes Necessários
 
- Arduino Uno (ou similar)

- Sensor de temperatura e umidade DHT11

- Sensor ultrassônico HC-SR04

- Resistores apropriados para o DHT11 (geralmente um resistor de 10kΩ entre VCC e o pino de dados)

- Cabos de conexão

- Protoboard
 
## Configuração do Hardware
 
### Sensor DHT11

1. Conecte o pino 1 do DHT11 ao VCC (5V).

2. Conecte o pino 2 do DHT11 ao pino digital 2 do Arduino.

3. Conecte um resistor de 10kΩ entre o pino 2 do DHT11 e o VCC.

4. Conecte o pino 4 do DHT11 ao GND.
 
### Sensor Ultrassônico HC-SR04

1. Conecte o pino VCC do HC-SR04 ao 5V do Arduino.

2. Conecte o pino GND do HC-SR04 ao GND do Arduino.

3. Conecte o pino Trig do HC-SR04 ao pino digital 9 do Arduino.

4. Conecte o pino Echo do HC-SR04 ao pino digital 10 do Arduino.
 
## Software
 
### Dependências

Este projeto requer a instalação das bibliotecas `DHT sensor library` e `ArduinoJson`. Ambas podem ser instaladas através do gerenciador de bibliotecas do Arduino IDE.
 
### Upload do código

1. Abra o Arduino IDE.

2. Conecte o Arduino ao seu computador via cabo USB.

3. Selecione o modelo correto de Arduino e a porta COM em `Ferramentas > Placa` e `Ferramentas > Porta`.

4. Copie o código fornecido neste README.

5. Pressione o botão `Upload` para carregar o código no Arduino.

## Montagem
Montagem física:
![image](https://github.com/felpschneider/sprint-3-edge/assets/143764606/a8256d2d-b1b4-444e-93a9-d2baebdde06c)

## Hive MQ
Segue abaixo a imagem da conexão feita na plataforma [HiveMQ](https://www.hivemq.com/) :

![image](https://github.com/felpschneider/sprint-3-edge/assets/143764606/c799a03c-147d-4207-9b5f-811d87232c7d)

## Tago.io 
Abaixo está uma screenshot do funcionamento da simulação no [Tago.io](https://tago.io):
![image](https://github.com/felpschneider/sprint-3-edge/assets/143764606/6b28ca2d-edd8-42b8-9eb6-350acf8a182d)

## Node-Red 
Foi criado um projeto para simulação no Node-Red, no qual foi utilizado um (Inject Json) para o recebimento de dados, uma (Function) para gerar valores aleatórios para temperatura, umidade e luminosidade, além de um (MQTT OUT) para mandar a simulação para o Tago.io.

![image](https://github.com/felpschneider/sprint-3-edge/assets/143764606/e61f2fc7-fddf-420f-bae7-eea1b6cab4ad)
 
## Dados

Os dados são enviados em formato JSON pela porta serial a cada 4000 milissegundos. Um exemplo dos dados enviados é:
 
```json

{

  "Temperatura": 22.3,

  "Umidade": 48.2,

  "Distancia": 175.5

}

```


## Integrantes

- Felipe Schneider - RM552643
- Maria Julia - RM553384
- Hugo Santos - RM553266
- Thiago Araujo - RM553477
- Vinícius Centurion - RM554063

