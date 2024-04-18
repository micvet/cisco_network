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
















