# A Camada de Acesso

## Frame Ethernet

A Ethernet é uma tecnologia de rede com fio usada em LANs, operando nas camadas de enlace de dados e física. Ela suporta larguras de banda de 10 Mbps a 100 Gbps e utiliza diferentes tipos de cabos, como par 
trançado, fibra óptica e cabos coaxiais. Os padrões da Ethernet são definidos pelos padrões IEEE 802.2 e 802.3.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/fad82183-5957-4253-abac-ad374e9e9430)


As subcamadas de link de dados, LLC e MAC, desempenham papéis distintos na camada de enlace de dados:

Subcamada LLC: Responsável pela comunicação entre o software de rede e o hardware do dispositivo. Ela identifica o protocolo da camada de rede usado no quadro, permitindo que diferentes protocolos da camada 3 
compartilhem a mesma interface de rede e mídia.

Subcamada MAC: Implementada em hardware, é responsável pelo encapsulamento de dados e controle de acesso à mídia. Fornece endereçamento de camada de enlace de dados e é integrada a diversas tecnologias de camada 
física, como Ethernet (IEEE 802.3) e Wi-Fi (IEEE 802.11).

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/397706d0-1a73-4928-ad92-fff40d512258)

## Subcamada MAC

A subcamada MAC, na IEEE 802.3, desempenha duas funções principais:

* Encapsulamento de Dados: Inclui a estrutura interna do frame Ethernet, endereçamento MAC de origem e destino para entrega dentro da mesma LAN, e um trailer de sequência de verificação de quadro (FCS) para 
detecção de erro.

* Acesso à Mídia: Define especificações para diferentes padrões de comunicação Ethernet em diversos tipos de mídia, como cobre e fibra.
![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/774c7743-40f3-4601-99fc-180fb1d93b15)

Na Ethernet legada, usando topologia de barramento ou hubs, ocorre um meio half-duplex compartilhado. Isso implica no uso do método de acesso CSMA/CD (Carrier Sense Multiple Access with Collision Detection), 
onde apenas um dispositivo pode transmitir por vez. O CSMA/CD detecta colisões quando vários dispositivos tentam transmitir simultaneamente, fornecendo um algoritmo de recuo para retransmissão.

Atualmente, as LANs Ethernet usam switches operando em full-duplex. Com comunicações full-duplex e switches Ethernet, não é necessário o controle de acesso CSMA/CD.

## Campos Ethernet

O Ethernet frame possui um tamanho mínimo de 64 bytes e máximo de 1518 bytes, incluindo todos os campos do endereço MAC de destino até o campo de sequência de verificação de quadro (FCS). O campo de preâmbulo 
não é contado no tamanho do quadro.

Quadros com menos de 64 bytes são chamados de "fragmentos de colisão" e são descartados automaticamente pelas estações receptoras. Aqueles com mais de 1500 bytes são chamados de "jumbo" ou "quadros gigantes".

Se um quadro transmitido estiver abaixo do tamanho mínimo ou acima do tamanho máximo, o dispositivo receptor o descarta. Esses quadros perdidos são geralmente resultado de colisões ou interferências indesejadas, 
sendo considerados inválidos. Os quadros jumbo são suportados pela maioria dos switches e placas de rede Fast Ethernet e Gigabit Ethernet.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/7bfa148d-627e-469a-bf3d-2160a18ffd33)

### Campos:

* Preamble: O preâmbulo é uma sequência de bits que serve para sincronizar os relógios dos dispositivos de rede. Ele prepara os dispositivos receptores para receberem o quadro de dados que está sendo transmitido.

* Start Frame Delimiter (SFD): Este campo marca o final do preâmbulo e o início do cabeçalho do quadro. Ele indica aos dispositivos receptores que o cabeçalho do quadro está prestes a começar.* 

* Header (Cabeçalho):

  * Endereço MAC de Destino: Identifica o dispositivo de destino para o qual o quadro está sendo enviado.
  * Endereço MAC de Origem: Identifica o dispositivo que está enviando o quadro.

* Lenght Type/EtherType: Indica o tipo de protocolo encapsulado nos dados do quadro, como IPv4, IPv6, ARP, etc.

* Dados: Esta seção contém os dados reais que estão sendo transmitidos. Eles podem variar em tamanho dependendo do protocolo encapsulado.

* Frame Check Sequence (FCS): É um campo que contém um valor de verificação de redundância cíclica (CRC) calculado a partir dos dados do quadro. É usado pelos dispositivos receptores para verificar se os dados 
foram transmitidos corretamente, detectando quaisquer erros de transmissão.

Inter-Frame Gap (IFG): É um período de tempo entre os quadros Ethernet consecutivos. Ele permite que os dispositivos de rede se preparem para receber o próximo quadro.



