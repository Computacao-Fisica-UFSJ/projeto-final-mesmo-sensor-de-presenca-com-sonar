[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/bQrFkq0H)

# Jardim Inteligente

## Andamento do projeto
- **Antes da aula do dia 25/11:** Estrutura de ligações dos modulos ao protoboard e Arduino; Implementação do código de controle do visor LCD e inicio do controle da bomba de água.
- **Aula do dia 25/11:** Pesquisa e tentativa de implementar a comunicação do arduino com um módulo wifi.
- **Aula do dia 26/11:** Conseguimos implementar a comunicação do arduino com o módulo wifi e estabelecemos um código que gera um servidor web em resposta. O site ainda esta sendo implmenetado. Tudo isso acarretou na mudança o placa utilizada de um arduino UNO para um arduino Mega.
- **Semana 01/12 a 05/12:** Criação do esquemático no Fritzing; Criação do site que será usado para ver informações e controlar a aplicação;
- **Aulas dos dias 10/12 e 11/12:** Tentativas de fazer o html criado para o site funcionar corretamente; Finalização das configurações referentes à bomba de água; Implementação do sistema de rega automatica baseada em um horario configurável.


## Contextualização
Com o avanço da automação residencial e da Internet das Coisas (IoT), tornou-se cada vez mais comum o desenvolvimento e a aplicação de sistemas de monitoramento capazes de controlar dispositivos presentes em residências. Nesse contexto, o cuidado com plantas na agricultura doméstica pode ser aprimorado por meio do monitoramento de variáveis ambientais, como umidade e temperatura.
Este projeto consiste na criação de um jardim inteligente que, por meio de um sensor de umidade, verifica a porcentagem de água presente no solo de um vaso de planta, acionando uma bomba d’água sempre que necessário. Além disso, o sistema conta com um servidor embarcado que disponibiliza uma interface web para o controle manual da irrigação. 

### Motivação

## Aplicações

## Lista de Materiais
| Nome               | Imagem             |
| ------------------ | ------------------ |
| Arduino Mega 2560  | <img src="https://vidadesilicio.com.br/wp-content/uploads/2021/09/1901-jpg.webp" alt="Foto arduino mega 2560" width="300px"> |
| Sensor de umidade do solo HW-080 | <img src="https://curtocircuito.com.br/media/catalog/product/cache/31a7b9a8d1a38183c94fb2deca9ba15c/_/s/_s_e_sensor_umidade_do_solo_1.jpg" alt="Foto sensor de umidade HW-080" width="300px"> |
| Visor Grove-LCD RGB Backlight | <img src="https://seeeddoc.github.io/Grove-LCD_RGB_Backlight/img/Serial_LEC_RGB_Backlight_Lcd.jpg" alt="Foto visor Grove-LCD RGB Backlight" width="300px"> |
| Modulo Wifi ESP8266 | <img src="https://images.tcdn.com.br/img/img_prod/672486/modulo_wifi_esp01_esp8266_43_1_d8e1fc79a4a87d5429704b3788615b70_20241128103856.jpg" alt="Foto Módulo Wifi ESP-01" width="300px"> |
| Adaptador ESP-01 | <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTwWG1IF6Woep4x9cUgK93tCzz57YrjBdrpzw&s" alt="Foto adaptador para ESP8266" width="300px">
| Bomba de água submersível | <img src="https://http2.mlstatic.com/D_NQ_NP_764687-MLB77866730739_072024-O.webp" alt="Foto bomba de água submersível" width="300px"> |
| Fonte externa a base de 4 pilhas AA | <img src="https://http2.mlstatic.com/D_NQ_NP_663814-MLB91476942282_092025-O.webp" alt="Foto fonte externa 4 pilhas" width="300px"> |
| Botões | <img src="https://guiarobotica.com/wp-content/uploads/2020/04/Push-Button-Arduino-e1586870732801.jpg.webp" alt="Foto botão" width="300px"> |
| Relé 1 canal JQC3F-05VDC-C 5V | <img src="https://images.tcdn.com.br/img/img_prod/648216/modulo_rele_arduino_1_canal_5v_10a_jqc3f_05vdc_c_152044_1_5073a7355c9187c39427fd090a2fb630.jpg" alt="Foto Relé JQC3F-05VDC-C 5V" width="300px"> |
| Jumpers macho-macho | <img src="https://images.tcdn.com.br/img/img_prod/650361/20x_cabo_jumper_macho_x_macho_20_cm_825_1_a25c47ea7e7348d431f946aa9ff09121.png" alt="jumpers macho-macho" width="300px"> |
| Jumpers macho-fêmea | <img src="https://images.tcdn.com.br/img/img_prod/672486/kit_500_jumpers_dupont_macho_femea_20_cm_2007_1_f16e740756d14fd65a3d62d6b08f9929_20241128103839.jpg" alt="jumpers macho-fêmea" width="300px"> |

## Bibliotecas usadas
- **rgb_lcd.h:** Biblioteca usada para controlar o visor Grove-LCD RBG Backlight.
- **Wire.h:** (precisa?)

## Diagrama de montagem
<img src="https://github.com/Computacao-Fisica-UFSJ/projeto-final-AlmadaLuiz14/blob/main/EsquemaFritzing/tpFinal_bb.png" alt="Imagem do diagrama de montagem">
Esse projeto foi montado usando um conjunto de componentes e conexões. Falaremos sobre cada conjunto de módulos para priorizar a organização e o entendimento.

- **Protoboard:** O protoboard aqui serve, pricipalmente como distribuidor de energia já que recebe a alimentação das portas 5V e GND do arduino e todos os outros componentes pegam energia de um de seus pontos. Além disso, há também dois botões que se comunicam com o arduino através de uma comunicação com as portas digitais 8 e 10.
- **Visor LCD:** O visor Grove-LCD RGB Backlight, além das ligações de alimentação com o protoboard, possui seus pino SDA e SCL ligados ao arduino nessas respectivas entradas (portas 20 e 21, respectivamente, do arduino Mega 2560)..
- **ESP:** O módulo wifi ESP8266 está conectado ao adaptador ESP-01 que, por sua vez, está conectado ao protoboard para energia e às portas digitais 18 (TX1) e 19 (RX1) do arduino (ligadas, respectivamente, ao RX e TX do ESP-01).
- **Relé e bomba d'água:** O Relé JQC3F-05VDC-C 5V possui duas partes d.d9 conexão: O "interruptor" e o controlador do "interruptor".
  - Na parte responsável pelo “interruptor”, o VCC (fio vermelho) da bomba d’água está conectado ao terminal NC (Normalmente fechado) do relé, e o VCC (fio vermelho) da fonte de pilhas está conectado ao terminal C (Comum). Dessa forma, quando o relé estiver desativado, o circuito permanece aberto e a bomba fica desligada. Quando o relé for acionado, o circuito se fecha, permitindo a passagem de corrente, e a bomba será ligada.
  - Na parte do controlador do relé, os pinos de alimentação estão conectados à protoboard por meio de jumpers, e o pino IN está ligado à porta digital 2 do Arduino, responsável por enviar o sinal de controle.
  - Além disso, é importante destacar que o GND (fio preto) da bomba d’água e o GND da fonte de pilhas devem estar conectados entre si, garantindo que ambos compartilhem o mesmo referencial negativo do circuito.

- **Sensor de umidade:** O sensor de umidade da terra HW-080 possui um controlador e eles são conectados entre si através de dois jumpers de alimenatção. O controlador, por sua vez, é conectado ao protoboard para receber energia e ao arduino, na porta analógica A0, para transferência de dados. 


## Foto do projeto

## Vídeo de funcionamento
[Link para o vídeo](https://drive.google.com/drive/folders/1RQaMnDNWxTeHiCYr-p0Y3ENLBdyxyKBA?usp=sharing)

## Problemas encontrados

## Referências usadas
