# IPV4 e Segmentacao de Rede

## Unicast

A transmissão unicast é quando um dispositivo envia uma mensagem para outro dispositivo em uma comunicação um-para-um. Um pacote unicast tem um endereço IP de 
destino que é único, indo para um único destinatário. O endereço IP de origem sempre será unicast, independentemente do tipo de endereço IP de destino (unicast, 
broadcast ou multicast).

## Broadcast

A transmissão broadcast é quando um dispositivo envia uma mensagem para todos os dispositivos em uma rede, sendo uma comunicação de um para todos. Os pacotes de 
broadcast IPv4 têm o endereço IP de destino com todos os bits na parte do host definidos como 1s. É importante notar que o IPv6 não utiliza pacotes de broadcast. 
Esses pacotes devem ser processados por todos os dispositivos no mesmo domínio de broadcast, identificando todos os hosts no mesmo segmento de rede. Existem dois 
tipos de broadcast: direcionado, enviado para todos os hosts em uma rede específica, e limitado, enviado para 255.255.255.255. Roteadores, por padrão, não encaminham 
broadcasts.

O tráfego broadcast consome recursos na rede, pois todos os hosts receptores na rede precisam processar os pacotes. Para preservar o desempenho da rede e dos 
dispositivos, é essencial limitar o tráfego broadcast. Uma maneira de fazer isso é subdividir as redes, o que ajuda os roteadores a separar os domínios de 
broadcast. Isso pode melhorar o desempenho ao reduzir o excesso de tráfego broadcast, garantindo que apenas os dispositivos relevantes recebam e processem os 
pacotes necessários.

## Multicast

A transmissão multicast reduz o tráfego na rede, permitindo que um host envie um único pacote para um conjunto selecionado de hosts que participam de um grupo 
multicast. Os pacotes multicast têm um endereço IP de destino que é um endereço multicast, reservado no intervalo IPv4 de 224.0.0.0 a 239.255.255.255. Os hosts que
recebem esses pacotes são chamados de clientes multicast e se inscrevem nos grupos multicast por meio de serviços solicitados por um programa cliente.

Cada grupo multicast é identificado por um único endereço IPv4 multicast de destino. Quando um host se inscreve em um grupo multicast, ele processa pacotes 
endereçados a esse endereço multicast, além de seu próprio endereço unicast exclusivo.

Protocolos de roteamento, como OSPF, usam transmissões multicast. Por exemplo, os roteadores habilitados com OSPF se comunicam entre si usando o endereço 
multicast reservado 224.0.0.5. Apenas dispositivos habilitados com OSPF processarão esses pacotes, enquanto os demais os ignorarão.

## Tipos de endereço IPV4

### Endereços IPv4 públicos e privados


Existem diferentes tipos de endereços IPv4, alguns reservados para roteamento na Internet e outros para redes internas. Como administrador de rede, é importante 
entender esses tipos de endereços e quando usá-los. Os endereços públicos são roteados globalmente entre os provedores de serviços de Internet, enquanto os 
privados são utilizados internamente pelas organizações. Eles foram introduzidos nos anos 90 devido ao esgotamento do espaço de endereços IPv4. A solução a longo 
prazo para esse problema foi o IPv6.

A solução a longo prazo para o esgotamento de endereços IPv4 foi o IPv6.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/3ab1a35f-fe5b-43ed-9c63-c88f7e5e2bc1)


A maioria das redes internas, desde grandes empresas até redes domésticas, utiliza endereços IPv4 privados para endereçar todos os dispositivos internos, 
incluindo hosts e roteadores. No entanto, esses endereços não são roteáveis globalmente.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/e65ced68-fabf-404e-a46b-7a36d319f859)

Antes de encaminhar um pacote, o ISP deve traduzir o endereço IPv4 de origem, que é privado, para um endereço IPv4 público usando o NAT (Network Address 
Translation). O NAT é utilizado para converter entre endereços IPv4 privados e públicos, geralmente realizado no roteador que conecta a rede interna à rede do ISP. 
Os endereços IPv4 privados na intranet da organização são traduzidos para endereços IPv4 públicos antes de serem encaminhados para a Internet.

## Endereços IPv4 de Uso Especial


Existem endereços especiais na rede, como o endereço de loopback (127.0.0.0/8 ou 127.0.0.1 a 127.255.255.254), comumente identificado como 127.0.0.1. Esses endereços são usados por um host para direcionar tráfego para si mesmo. Por exemplo, o comando ping é usado para testar conexões com outros hosts, mas também pode ser usado para testar a configuração de IP do próprio dispositivo.

### Endereços locais de link

Os endereços locais de link (169.254.0.0/16 ou 169.254.0.1 a 169.254.255.254) são conhecidos como endereços APIPA (Auto-Configuração de IP Privado Automático) ou endereços auto-atribuídos. Eles são utilizados por clientes Windows para se autoconfigurarem quando não conseguem obter um endereçamento IP por outros métodos. Esses endereços podem ser utilizados em uma conexão ponto a ponto, mas não são comumente empregados para esse fim.

## Endereçamento Classful Legado

Em 1981, os endereços IPv4 foram atribuídos usando o método de endereçamento classful, conforme definido na RFC 790. Nesse sistema, os clientes recebiam um endereço de rede baseado em uma das três classes: A, B ou C.

Classe A (0.0.0.0/8 a 127.0.0.0/8): Projetada para suportar redes extremamente grandes, com mais de 16 milhões de endereços de host por rede.
Classe B (128.0.0.0/16 a 191.255.0.0/16): Projetada para redes de tamanho moderado a grande, com até aproximadamente 65.000 endereços de host por rede.
Classe C (192.0.0.0/24 a 223.255.255.0/24): Projetada para redes pequenas, com no máximo 254 hosts por rede.
Além disso, havia um bloco multicast Classe D (224.0.0.0 a 239.0.0.0) e um bloco de endereço experimental Classe E (240.0.0.0 a 255.0.0.0).

Naquela época, com um número limitado de computadores conectados à Internet, o endereçamento classful era eficaz. No entanto, as classes A e B tinham um grande número de endereços de host, enquanto a classe C tinha muito poucos. Isso resultou na subutilização da maioria dos endereços IPv4 disponíveis.

Na década de 1990, com a popularização da World Wide Web (WWW), o método de endereçamento clássico foi substituído pelo endereçamento sem classe, que é amplamente utilizado hoje em dia. Este método permite uma distribuição mais eficiente dos endereços IPv4 públicos, baseando-se no número de endereços que podem ser justificados.

## Atribuição de Endereços IP

Os endereços IPv4 públicos são globalmente roteados pela Internet e devem ser exclusivos. A IANA gerencia e aloca blocos de endereços IPv4 e IPv6 aos registros regionais de Internet (RIRs), responsáveis por fornecer endereços IP aos ISPs e organizações. Existem cinco RIRs responsáveis por essa alocação, e as organizações podem obter seus endereços diretamente de um RIR, sujeitas às políticas específicas desse RIR.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/fcf9f882-7d9f-4131-b53c-b323aa76787b)

* AfriNIC(Centro de Informação de Redes Africanas) - Região da África
* APNIC(Centro de informações de redes da Ásia-Pacífico) - Região Ásia/Pacífico
* ARIN(Registro Americano de Números da Internet) - Região da América do Norte
* LACNIC(Registro regional de endereços IP da América Latina e do Caribe) - América Latina e algumas ilhas do Caribe
* RIPE NCC(Centro de coordenação da rede Réseaux IP Européens) - Europa, Oriente Médio e Ásia Central

## Segmentação de Rede

### Domínios de Broadcast e Segmentação

Em uma rede, transmissões são e-mails ou mensagens enviadas a todos os membros, mas nem sempre são relevantes para todos. Na LAN Ethernet, dispositivos usam broadcasts e o ARP para encontrar outros dispositivos. O ARP envia broadcasts para descobrir endereços MAC associados aos IPs. Dispositivos também usam serviços para se localizar. Switches encaminham broadcasts para todas as interfaces, exceto a de origem.

Os roteadores não propagam broadcasts. Quando um roteador recebe um broadcast em uma interface, ele não o encaminha para outras interfaces. Assim, cada interface do roteador conecta-se a um domínio de broadcast específico, e as transmissões são limitadas a esse domínio.

**Exemplificando de maneira mais fácil:**

Imagine que você tem uma rede de computadores, como uma escola. Cada computador na escola precisa se comunicar com os outros para compartilhar informações, como um trabalho de grupo.

Agora, para que os computadores se comuniquem, eles usam algo chamado de "broadcast". É como gritar em uma sala cheia de pessoas para que todos possam ouvir.

Mas agora, vamos pensar em um roteador. Um roteador é como um carteiro que entrega mensagens entre diferentes casas (ou redes de computadores).

Aqui está o ponto chave: os roteadores não gostam de gritar para todos como os computadores fazem. Eles são mais como mensageiros discretos. Quando um roteador recebe uma mensagem de "grito" (um broadcast) de um computador em uma de suas interfaces, ele pensa: "Isso é apenas para os computadores nesta sala", então ele não o entrega para todas as outras salas (ou interfaces).

Então, para simplificar, cada interface do roteador está conectada a uma sala separada (ou domínio de broadcast), e ele só entrega mensagens dentro dessa sala. Isso mantém as coisas organizadas e evita que a rede fique muito barulhenta!

Um grande domínio de broadcast ocorre quando muitos hosts estão conectados à mesma rede. Isso pode levar a problemas de desempenho, pois os hosts podem gerar uma quantidade excessiva de tráfego de broadcast. Por exemplo, na LAN 1 da figura, com 400 usuários, o grande número de broadcasts pode causar lentidão na rede e nos dispositivos, pois cada pacote de broadcast deve ser aceito e processado individualmente.


Para resolver o problema do grande domínio de broadcast, é necessário dividir a rede em sub-redes menores. Isso é feito através de um processo chamado divisão em sub-redes. Com isso, os broadcasts são propagados apenas dentro das sub-redes individuais, garantindo que um broadcast na LAN 1 não afete a LAN 2.

### Razões para Segmentar Redes


A divisão em sub-redes não apenas reduz o tráfego total da rede e melhora o desempenho, mas também permite que o administrador implemente políticas de segurança, determinando quais sub-redes podem ou não se comunicar entre si. Além disso, ela reduz o número de dispositivos afetados por problemas de tráfego anormal ou intenções maliciosas. Existem diversas maneiras de usar sub-redes para gerenciar dispositivos de rede.

**Formas de segmentar a rede:**

* Localização:
![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/c4a2b80a-3c32-4d7d-86df-26f750352472)
* Grupo ou função:
![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/9f734dc7-02ef-42e8-bb14-211622475582)
* Tipos de dispositivos:
![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/2f41a779-2847-4c25-ba7f-fde3db25c18c)


Os administradores de rede têm flexibilidade para criar sub-redes usando qualquer divisão que faça sentido para a rede. Nas figuras, as sub-redes são identificadas por comprimentos de prefixo. É crucial que todos os administradores de redes compreendam esse processo de divisão em sub-redes. Existem diversos métodos para auxiliar nesse entendimento, e embora possa parecer complicado inicialmente, com atenção aos detalhes e prática, a criação de sub-redes se tornará mais fácil.






