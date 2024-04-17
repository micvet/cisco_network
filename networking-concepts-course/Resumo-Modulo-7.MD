# A Camada de Acesso

## Encapsulamento e o quadro Ethernet

### Frame Ethernet

A Ethernet é uma tecnologia de rede com fio usada em LANs, operando nas camadas de enlace de dados e física. Ela suporta larguras de banda de 10 Mbps a 100 Gbps e utiliza diferentes tipos de cabos, como par 
trançado, fibra óptica e cabos coaxiais. Os padrões da Ethernet são definidos pelos padrões IEEE 802.2 e 802.3.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/6b85f00d-0acd-4b53-9666-f917f419933b)

As subcamadas de link de dados, LLC e MAC, desempenham papéis distintos na camada de enlace de dados:

Subcamada LLC: Responsável pela comunicação entre o software de rede e o hardware do dispositivo. Ela identifica o protocolo da camada de rede usado no quadro, permitindo que diferentes protocolos da camada 3 
compartilhem a mesma interface de rede e mídia.

Subcamada MAC: Implementada em hardware, é responsável pelo encapsulamento de dados e controle de acesso à mídia. Fornece endereçamento de camada de enlace de dados e é integrada a diversas tecnologias de camada 
física, como Ethernet (IEEE 802.3) e Wi-Fi (IEEE 802.11).

### Subcamada MAC

A subcamada MAC, na IEEE 802.3, desempenha duas funções principais:

* Encapsulamento de Dados: Inclui a estrutura interna do frame Ethernet, endereçamento MAC de origem e destino para entrega dentro da mesma LAN, e um trailer de sequência de verificação de quadro (FCS) para 
detecção de erro.

* Acesso à Mídia: Define especificações para diferentes padrões de comunicação Ethernet em diversos tipos de mídia, como cobre e fibra.
![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/774c7743-40f3-4601-99fc-180fb1d93b15)

Na Ethernet legada, usando topologia de barramento ou hubs, ocorre um meio half-duplex compartilhado. Isso implica no uso do método de acesso CSMA/CD (Carrier Sense Multiple Access with Collision Detection), 
onde apenas um dispositivo pode transmitir por vez. O CSMA/CD detecta colisões quando vários dispositivos tentam transmitir simultaneamente, fornecendo um algoritmo de recuo para retransmissão.

Atualmente, as LANs Ethernet usam switches operando em full-duplex. Com comunicações full-duplex e switches Ethernet, não é necessário o controle de acesso CSMA/CD.

### Campos Ethernet

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

## Encapsulamento

Assim como uma carta é colocada dentro de um envelope para ser entregue, as mensagens de computador são encapsuladas em um formato específico, chamado de quadro, antes de serem enviadas pela rede. O processo de encapsulamento garante que a mensagem seja entregue corretamente, fornecendo informações como o endereço de destino e o endereço do host de origem. Se a mensagem não estiver formatada corretamente, ela não será entregue nem processada pelo host de destino.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/284da94b-e9e0-46eb-8c14-8a566e2833ef)

**Analogia com o processo de encapsulamento:**<br>

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/671fa05e-0818-41be-9ac4-e2a1f8073eb7)

### Switches Ethernet

Switches Ethernet são dispositivos de rede usados para interconectar dispositivos em uma rede local (LAN). Eles operam na camada de enlace de dados do modelo OSI e são projetados para direcionar o tráfego de rede com base nos endereços MAC dos dispositivos conectados.

A principal função de um switch Ethernet é encaminhar pacotes de dados apenas para o dispositivo de destino correto, em vez de transmiti-los para todos os dispositivos na rede, como acontece em uma rede de hub. Isso é feito examinando o endereço MAC de destino de cada pacote de dados e encaminhando-o apenas para a porta do switch que está conectada ao dispositivo de destino.

Os switches Ethernet oferecem várias portas para conectar dispositivos, geralmente variando de 4 a 48 portas ou até mais em switches empresariais. Eles também podem suportar diferentes velocidades de conexão, como 10/100/1000 Mbps (megabits por segundo) ou até 10 Gbps (gigabits por segundo) em switches de alta velocidade.

Em resumo, os switches Ethernet são fundamentais para redes locais modernas, pois oferecem uma maneira eficiente de interconectar dispositivos, garantindo uma comunicação rápida e confiável. Eles são amplamente utilizados em ambientes domésticos, empresariais e industriais para criar redes de computadores.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/ee456ee0-61e9-41b1-ace7-546c312836fa)

### Tabela de Endereçamento MAC

Uma tabela de endereços MAC (Media Access Control) é uma lista de endereços MAC associados aos dispositivos conectados a um switch Ethernet em uma rede local (LAN). Ela é usada pelo switch para determinar para qual porta encaminhar pacotes de dados com base no endereço MAC de destino.

Quando um dispositivo é conectado a um switch Ethernet, o switch registra o endereço MAC do dispositivo e a porta à qual ele está conectado em sua tabela de endereços MAC. Isso permite que o switch direcione eficientemente os pacotes de dados apenas para a porta correta, em vez de transmiti-los para todas as portas, reduzindo o tráfego desnecessário na rede.

Ela é  dinâmica e é atualizada conforme os dispositivos se conectam ou desconectam da rede. Quando um pacote de dados é recebido pelo switch, ele verifica a tabela de endereços MAC para determinar a porta de destino e encaminha o pacote apenas para essa porta, mantendo assim a eficiência e a segurança da rede.

**EXEMPLO:**

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/2658a8a2-c79e-4b4c-b668-097002047f39)

Um switch Ethernet usa endereços MAC da Camada 2 para encaminhar ou descartar quadros para outros dispositivos na rede. Ele não se importa com os dados transportados no quadro, como pacotes IPv4 ou IPv6. Em vez disso, toma suas decisões com base exclusivamente nos endereços MAC Ethernet.

Ao receber um quadro, o switch verifica sua tabela de endereços MAC para determinar para qual porta encaminhar o quadro. Se o endereço de destino estiver na tabela, o quadro é encaminhado apenas para a porta correspondente. Caso contrário, o switch transmite o quadro para todas as portas, exceto a porta de origem. A tabela de endereços MAC é atualizada conforme os dispositivos são conectados e desconectados da rede.

Quando um quadro entra em um switch, ele verifica o endereço MAC de origem e a porta pela qual o quadro entrou. Se o endereço MAC de origem não estiver na tabela, o switch adiciona uma nova entrada com o endereço MAC e a porta de entrada. Se o endereço já estiver na tabela, o switch atualiza o tempo de atualização para essa entrada. Geralmente, os switches mantêm cada entrada por 5 minutos. Se um endereço MAC existir em uma porta diferente, o switch substitui a entrada anterior pela nova, atualizando o número da porta.

Quando um quadro chega a um switch, ele verifica o endereço MAC de destino do quadro. Se for um endereço unicast e estiver na tabela de endereços MAC, o switch encaminha o quadro pela porta correspondente. Se o endereço não estiver na tabela, o switch encaminha o quadro por todas as portas, exceto a porta de entrada, em um processo chamado de unicast desconhecido. Se o endereço for de broadcast ou multicast, o quadro é enviado por todas as portas, exceto a porta de entrada.







