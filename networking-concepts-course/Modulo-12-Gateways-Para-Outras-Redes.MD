# Gateways para outras redes

## Limites de rede

Em uma rede, um gateway é um ponto de entrada ou saída que conecta dois sistemas ou redes diferentes. Ele atua como um intermediário que facilita a comunicação entre esses sistemas, permitindo que eles troquem informações e dados.

A função principal de um gateway em uma rede é traduzir os protocolos de comunicação usados por cada sistema, garantindo a interoperabilidade entre eles. Por exemplo, se uma rede usa um protocolo de comunicação específico, como TCP/IP, e outra rede usa um protocolo diferente, como IPX/SPX, o gateway traduzirá os dados entre esses protocolos para que os sistemas possam se comunicar.

Além disso, os gateways podem fornecer outras funcionalidades, como:

* Roteamento de tráfego: Encaminhando pacotes de dados entre redes, determinando o caminho mais eficiente para entrega.
* Segurança: Implementando firewalls e filtros para proteger a rede contra ameaças externas, como hackers e malware.
* Tradução de endereços de rede (NAT): Permitindo que múltiplos dispositivos compartilhem um único endereço IP público, ocultando a estrutura interna da rede.
* Gerenciamento de protocolos: Convertendo entre diferentes formatos de mensagem ou protocolos de aplicação.
* Integração de sistemas: Permitindo que sistemas heterogêneos se comuniquem e cooperem entre si.

**Exemplos de gateways em diferentes contextos:**

* Um roteador que conecta uma rede local a uma rede de área ampla (WAN), como a Internet.
* Um gateway de pagamento que facilita transações entre um comerciante online e uma instituição financeira.
* Um gateway de API que permite que aplicativos se comuniquem entre si através de interfaces de programação.
* Um gateway de voz sobre IP (VoIP) que conecta chamadas telefônicas tradicionais à internet.

**Exemplo do funcionamento de um Gateway em uma rede doméstica:**

Conexão com a Internet: O gateway (roteador) está conectado ao modem de banda larga fornecido pelo provedor de serviços de Internet (ISP). Esta conexão pode ser feita via cabo Ethernet, fibra óptica, DSL, ou outro tipo de conexão.
Atribuição de Endereços IP: O gateway atribui endereços IP aos dispositivos na rede doméstica usando o Protocolo de Configuração Dinâmica de Host (DHCP). Isso permite que cada dispositivo tenha uma identificação única na rede e possa se comunicar com outros dispositivos e com a Internet.
Roteamento de Tráfego: O gateway roteia o tráfego de dados entre os dispositivos na rede local e a Internet. Ele decide para onde enviar os pacotes de dados com base nos endereços IP de origem e destino. Se o destino estiver na rede local, o roteador direciona o tráfego internamente. Se o destino estiver fora da rede local, o roteador envia o tráfego para a Internet através do modem.
Firewall: Muitos gateways incluem um firewall para proteger a rede doméstica contra ameaças externas, como ataques de hackers e malware. O firewall monitora o tráfego de entrada e saída e aplica regras de segurança para bloquear ou permitir determinados tipos de tráfego.
Tradução de Endereços de Rede (NAT): O gateway usa NAT para permitir que vários dispositivos na rede doméstica compartilhem um único endereço IP público fornecido pelo ISP. Isso é útil porque os ISPs geralmente fornecem apenas um único endereço IP para uma conexão residencial, e NAT permite que múltiplos dispositivos compartilhem essa conexão.


### ARP Protocol

ARP significa "Address Resolution Protocol" (Protocolo de Resolução de Endereços) e é uma parte fundamental do funcionamento das redes de computadores. O ARP é usado para mapear endereços IP (Internet Protocol) para endereços físicos de rede, conhecidos como endereços MAC (Media Access Control).

Quando um dispositivo em uma rede local precisa se comunicar com um dispositivo em outra rede ou fora da rede local, ele precisa saber o endereço MAC do gateway, pois o gateway é o ponto de saída para alcançar dispositivos em outras redes. O ARP é usado para descobrir o endereço MAC associado ao endereço IP do gateway.

Se um dispositivo em uma rede local quer enviar um pacote de dados para um servidor na Internet, antes de enviar o pacote, ele precisa saber o endereço MAC do gateway, que é o próximo salto para alcançar o servidor. O dispositivo emite uma solicitação ARP para descobrir o endereço MAC do gateway. Uma vez que o gateway responde com seu endereço MAC, o dispositivo pode enviar o pacote de dados para o gateway, que então encaminha o pacote para a rede externa. Todos os dispositivos na rede recebem essa solicitação ARP, mas apenas o dispositivo com o endereço IP correspondente responde, enviando seu endereço MAC de volta ao dispositivo que fez a pergunta.

Após receber a resposta ARP, o dispositivo que iniciou a solicitação mantém em cache o mapeamento de endereço IP para endereço MAC em uma tabela ARP. Isso evita a necessidade de fazer a mesma solicitação ARP repetidamente para o mesmo dispositivo, economizando largura de banda e tempo.

O ARP é uma parte essencial do funcionamento das redes locais (LANs) e é uma das primeiras etapas no processo de comunicação entre dispositivos em uma rede. Sem o ARP, os dispositivos não seriam capazes de se comunicar entre si na camada de enlace de dados.

### Roteadores como Gateways

O roteador atua como um gateway para permitir a comunicação entre hosts em diferentes redes. Cada interface do roteador está ligada a uma rede distinta, com um endereço IPv4 que identifica a rede local. Os hosts devem usar o roteador como gateway para acessar outras redes, conhecido como o endereço de gateway padrão, que pode ser configurado estaticamente ou obtido via DHCP.

Quando um roteador sem fio é configurado como servidor DHCP, ele atribui automaticamente seu próprio endereço IPv4 como o gateway padrão para os hosts da rede local. Isso facilita o encaminhamento de mensagens para redes externas, incluindo a Internet.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/ad39d4bd-0fd1-4e65-a3e4-aa4cc94687fa)

### Roteadores como limites entre redes

O roteador sem fio atua como servidor DHCP para os hosts locais, conectados via cabo Ethernet ou sem fio, em uma rede interna. Ele atribui endereços privados aos hosts, garantindo que a rede interna não seja acessada diretamente da Internet. O endereço IPv4 padrão do roteador sem fio é geralmente o primeiro endereço de host na rede, e ele fornece esses endereços, além de informações de máscara de sub-rede e seu próprio endereço IPv4 como gateway padrão, quando configurado como servidor DHCP.

Quando conectado a um ISP, o roteador sem fio atua como cliente DHCP para receber um endereço IPv4 roteável pela Internet para sua interface de Internet, permitindo que os hosts locais acessem a Internet. Dessa forma, o roteador sem fio atua como um limite entre a rede interna e a Internet externa.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/0a7f3185-afe3-43fb-aff2-a52113516c4d)

## Tradução de Endereço de Rede (NAT)

NAT (Tradução de Endereço de Rede) é uma técnica utilizada em redes de computadores para permitir que múltiplos dispositivos em uma rede local compartilhem um único endereço IP público para se comunicar com a Internet. Isso é importante devido à escassez de endereços IP públicos disponíveis e também contribui para a segurança da rede, pois oculta a topologia interna da rede.

Quando os dispositivos da rede local se comunicam com a Internet, o roteador ou dispositivo NAT intercepta essas solicitações e substitui os endereços IP privados dos dispositivos locais por um único endereço IP público fornecido pelo ISP. Isso permite que os dispositivos na Internet respondam ao roteador NAT, que então encaminha as respostas de volta para os dispositivos corretos na rede local, com base nas informações de tradução de endereços mantidas em uma tabela interna.

* Tipos de NAT:
NAT estático: Neste tipo de NAT, as traduções de endereços IP são configuradas manualmente e são permanentes. Cada endereço IP privado é mapeado para um endereço IP público específico.
NAT dinâmico: Neste tipo, as traduções de endereços IP são criadas dinamicamente conforme necessário, à medida que os dispositivos na rede local iniciam sessões de comunicação com a Internet. Isso maximiza o uso dos endereços IP públicos disponíveis.

* Port Address Translation (PAT):
Também conhecido como NAT de sobrecarga, o PAT é uma forma específica de NAT dinâmico onde várias traduções de endereço IP privado para endereço IP público são baseadas não apenas nos endereços IP, mas também nas portas de origem dos dispositivos na rede local. Isso permite que vários dispositivos compartilhem um único endereço IP público usando portas diferentes.

* Conservação de Endereços IP Públicos:
Uma das principais razões para usar NAT é a conservação de endereços IP públicos. Com NAT, uma organização pode usar apenas um pequeno número de endereços IP públicos, mesmo com muitos dispositivos na rede local, reduzindo assim a necessidade de endereços IP públicos atribuídos individualmente a cada dispositivo.

* Segurança:
NAT também fornece uma camada adicional de segurança, pois oculta a topologia interna da rede local. Dispositivos na Internet só veem o endereço IP público do roteador NAT, não os endereços IP privados dos dispositivos individuais na rede local. Isso dificulta ataques direcionados a dispositivos específicos na rede local.
Compatibilidade com IPv6:
Embora NAT seja amplamente usado com IPv4 devido à escassez de endereços IP públicos, o IPv6 tem um espaço de endereçamento muito maior e geralmente não requer NAT para conservação de endereços IP. No entanto, NAT66 (NAT para IPv6) ainda é uma opção para implementar políticas de segurança e ocultar a topologia interna da rede.
 
* Implementação:
A NAT é implementada em dispositivos de rede, como roteadores ou firewalls, que atuam como gateways entre redes locais e a Internet. O software de NAT nos dispositivos é responsável por traduzir os endereços IP e portas conforme necessário.

### Funcionamento do NAT em uma rede LAN:

1. Rede Local (LAN):
Os dispositivos na rede local são configurados com endereços IP privados, que são reservados para uso em redes locais e não são roteáveis pela Internet.
Cada dispositivo tem um endereço IP privado exclusivo dentro da rede local.

2. Dispositivo NAT (como um roteador):
O dispositivo NAT é tipicamente um roteador que conecta a rede local à Internet.
Ele possui pelo menos duas interfaces de rede: uma conectada à rede local e outra conectada à Internet.

3. Tabela de Tradução de Endereços (NAT Table):
O dispositivo NAT mantém uma tabela de tradução de endereços que associa os endereços IP e portas locais dos dispositivos da rede local aos endereços IP e portas externas usados para se comunicar com a Internet.
Esta tabela é dinamicamente atualizada conforme os dispositivos na rede local iniciam sessões de comunicação com a Internet.

4. Início da Comunicação:
Quando um dispositivo na rede local deseja iniciar uma comunicação com um destino na Internet, ele envia um pacote de dados.
O pacote contém o endereço IP de origem (um endereço IP privado da rede local) e a porta de origem.

5. Tradução de Endereço:
O dispositivo NAT intercepta o pacote de dados antes de encaminhá-lo para a Internet.
Ele substitui o endereço IP de origem e a porta de origem no cabeçalho do pacote com seu próprio endereço IP público e uma porta externa única.
O dispositivo NAT também registra essa tradução na tabela de tradução de endereços.

6. Encaminhamento para o Destino:
O pacote de dados modificado é então encaminhado para a Internet usando o endereço IP do destino.
Quando o destino responde, o roteador mantém o controle das traduções feitas anteriormente e direciona a resposta de volta para o dispositivo local correspondente, usando a tabela de tradução de endereços.

7. Resposta do Destino:
Quando a resposta chega ao roteador, ele consulta a tabela de tradução de endereços para encontrar o endereço IP privado e a porta de origem original do dispositivo local.
O roteador substitui o endereço IP de destino e a porta de destino no cabeçalho do pacote com o endereço IP privado e a porta de origem original do dispositivo local. O pacote é então encaminhado para o dispositivo local na rede local.

