# O Processo de ARP

## MAC e IP

### Destino de uma mesma rede

Quando um host precisa enviar uma mensagem para um dispositivo de destino na mesma rede Ethernet, ele utiliza o endereço MAC desse dispositivo. No entanto, se o destino estiver em uma rede diferente, o host utiliza o endereço IP do dispositivo. Para descobrir o endereço MAC correspondente a um endereço IP, o host executa a resolução de endereços.

Na resolução de endereços, o host associa o endereço IP do destino ao seu endereço MAC correspondente. Isso permite que o host envie o pacote de dados para o dispositivo de destino corretamente. Dessa forma, os endereços físicos (MAC) são usados para comunicações de NIC para NIC na mesma rede Ethernet, enquanto os endereços lógicos (IP) são utilizados para enviar pacotes entre redes.

Portanto, a resolução de endereços desempenha um papel crítico na comunicação eficaz entre dispositivos em uma rede Ethernet, garantindo que os pacotes sejam entregues aos dispositivos corretos, independentemente de estarem na mesma rede ou em redes remotas.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/5a73be99-0071-490b-9b52-1edf0c2a0e55)

No exemplo, PC1 deseja enviar um pacote para PC2. A figura exibe os endereços MAC de destino e de origem da Camada 2 e o endereçamento IPv4 da Camada 3 que seriam incluídos no pacote enviado a partir do PC1.

O quadro Ethernet da camada 2 contém o seguinte:

Endereço MAC de destino — Este é o endereço MAC simplificado de PC2, 55-55-55.
Endereço MAC de origem — Este é o endereço MAC simplificado da NIC Ethernet em PC1, aa-aa-aa .
O pacote IP da camada 3 contém o seguinte:

Endereço IPv4 de origem — Este é o endereço IPv4 de PC1, 192.168.10.10 .
Endereço IPv4 dedestino — Este é o endereço IPv4 de PC2, 192.168.10.11.

### DEstino de uma rede remota

Quando um dispositivo precisa enviar dados para um endereço IP de destino em uma rede remota, o endereço MAC de destino será o endereço MAC do gateway padrão do dispositivo, ou seja, a interface do roteador conectada à rede local.

Por exemplo, se um dispositivo em uma rede local precisa enviar dados para um endereço IP fora da sua rede local, ele usa o endereço MAC do gateway padrão (o roteador) como destino para o pacote. O roteador então encaminha o pacote para a rede remota, utilizando seu próprio endereço MAC para encaminhamento dentro da rede local.

Essa prática é essencial para garantir que os pacotes sejam encaminhados corretamente para redes remotas através do gateway padrão, permitindo a comunicação entre dispositivos em diferentes redes locais e a Internet.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/c6ff50d8-c1c4-4c68-b073-4c640ebecc68)

No exemplo, PC1 deseja enviar um pacote para PC2. O PC2 está localizado na rede remota. Como o endereço IPv4 de destino não está na mesma rede local que PC1, o endereço MAC de destino é o do gateway padrão local, no roteador.

Os roteadores examinam o endereço IPv4 destino para determinar o melhor caminho para encaminhar o pacote IPv4. Quando o roteador recebe o quadro Ethernet, ele desencapsula as informações da Camada 2. Usando o endereço IPv4 de destino, ele determina o dispositivo do próximo salto e, em seguida, encapsula o pacote IPv4 em um novo quadro (da camada de enlace) para a interface de saída.

No nosso exemplo, o R1 agora encapsularia o pacote com novas informações de endereço da Camada 2, conforme mostrado na figura.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/0ec73e79-a726-442b-9849-ef0317a59f63)

O novo endereço MAC de destino seria o da interface G0/0/1 em R2 e o novo endereço MAC de origem seria o da interface G0/0/1 em R1.

Ao longo de cada link do caminho, um pacote IP é encapsulado em um quadro. O quadro é específico para a tecnologia do enlace associado a esse link, como Ethernet. Se o dispositivo do próximo salto for o destino final, o endereço MAC de destino será o da NIC Ethernet do dispositivo, conforme mostrado na figura.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/d5b3a8b1-0ba8-445c-bc46-634506aa2367)

Como os endereços IP dos pacotes IP em um fluxo de dados são associados aos endereços MAC em cada link ao longo do caminho até o destino? Para pacotes IPv4, isso é feito através de um processo chamado ARP (Address Resolution Protocol). Para pacotes IPv6, o processo é ICMPv6 Neighbor Discovery (ND).

### NIC

Uma NIC (Network Interface Card), também conhecida como placa de rede ou adaptador de rede, é um componente de hardware que permite que um dispositivo, como um computador ou um roteador, se conecte a uma rede de computadores para comunicação com outros dispositivos na mesma rede.

Características e funcionamento:

* Componente de Hardware: é um dispositivo de hardware que é instalado em um computador ou dispositivo para fornecer conectividade de rede. Ela pode ser integrada à placa-mãe do computador ou conectada através de uma porta de expansão, como PCI, PCIe ou USB.

* Conectividade Física: possui uma porta física, como um conector Ethernet RJ-45, para conexão com cabos de rede. Dependendo do tipo de rede, a NIC pode ter outros tipos de conectores, como fibra óptica ou Wi-Fi.

* Funções Básicas: sua principal função é permitir que o dispositivo se comunique com outros dispositivos em uma rede. Ela converte dados digitais do dispositivo em sinais elétricos ou ópticos para transmissão pela rede e vice-versa.

* Endereço MAC: Cada NIC possui um endereço MAC (Media Access Control), que é um identificador único atribuído pelo fabricante. Este endereço é gravado na memória da NIC e é utilizado para identificar exclusivamente o dispositivo em uma rede Ethernet.

* Suporte a Protocolos de Rede: é projetada para suportar os protocolos de rede específicos da rede à qual está conectada. Por exemplo, uma NIC Ethernet suporta os padrões Ethernet, enquanto uma NIC Wi-Fi suporta os padrões Wi-Fi.

* Controlador de Dispositivo: requer um controlador de dispositivo (driver) para funcionar corretamente com o sistema operacional do dispositivo hospedeiro. O driver é responsável por controlar as operações da NIC e traduzir os dados entre o sistema operacional e a NIC.

* Modos de Operação: pode operar em diferentes modos, como modo half-duplex (comunicação bidirecional, mas não simultânea) ou modo full-duplex (comunicação bidirecional simultânea), dependendo das capacidades da NIC e da configuração da rede.

* Funcionalidades Avançadas: algumas oferecem funcionalidades avançadas, como offloading de tarefas de rede para liberar recursos da CPU, suporte a VLANs (Virtual LANs) para segmentação de redes e suporte a tecnologias de criptografia para comunicações seguras.

## Contenção de Broadcast

### Broadcast

Broadcast é um termo comumente usado em redes de computadores para descrever o envio de uma mensagem para todos os dispositivos em uma rede. Quando uma mensagem é enviada para o endereço de broadcast da rede, ela é entregue a todos os dispositivos conectados àquela rede, em vez de ser direcionada a um dispositivo específico.
O uso de broadcast é útil em cenários onde uma mensagem precisa ser entregue a todos os dispositivos em uma rede, como atualizações de sistema, anúncios de serviço ou solicitações de descoberta de dispositivos.
Embora os broadcasts sejam úteis, também podem consumir largura de banda desnecessária em redes grandes, especialmente se forem usados com muita frequência. Por esse motivo, é importante usar transmissões de broadcast com moderação e considerar alternativas mais eficientes, como multicasting, quando apropriado.

### Domínios de Broadcast

Quando um host recebe uma mensagem endereçada ao endereço de broadcast, ele a processa como se fosse destinada diretamente a ele. Da mesma forma, ao enviar uma mensagem de broadcast, os switches a encaminham para todos os hosts na mesma rede local, criando o que é chamado de domínio de broadcast. Se muitos hosts estiverem no mesmo domínio de broadcast, o tráfego pode se tornar excessivo, limitando a capacidade da rede. Para lidar com isso, é comum dividir a rede local em vários domínios de broadcast usando roteadores, melhorando assim o desempenho da rede.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/625021f4-ee58-4c9c-a4d1-5c588102295d)

### Comunicação na camada de Acesso

Em uma rede Ethernet local, uma NIC só aceitará um quadro se o endereço de destino corresponder ao seu próprio endereço MAC ou se for o endereço MAC de broadcast. No entanto, a maioria dos aplicativos de rede se baseia nos endereços IP lógicos para identificar a localização dos servidores e clientes.

Quando um host emissor conhece apenas o endereço IP lógico do destinatário, ele precisa determinar o endereço MAC correspondente para enviar o quadro. Para isso, ele utiliza um protocolo chamado ARP (Address Resolution Protocol) no caso do IPv4, ou Descoberta de Vizinhos (Neighbor Discovery) no caso do IPv6. Esses protocolos permitem que o host emissor descubra o endereço MAC associado a um determinado endereço IP dentro da mesma rede local, garantindo assim a entrega correta dos dados.

### ARP

O processo ARP (Address Resolution Protocol) é composto por três etapas para descobrir e armazenar o endereço MAC de um host na rede local quando apenas o endereço IPv4 do host é conhecido:

O host remetente cria e envia um quadro destinado ao endereço MAC de broadcast. Dentro do quadro, há uma mensagem contendo o endereço IPv4 do host de destino que se deseja alcançar.
Todos os hosts na rede recebem o quadro de broadcast e comparam o endereço IPv4 na mensagem com o endereço IPv4 configurado em cada host. Quando um host encontra um endereço IPv4 correspondente, ele responde enviando seu endereço MAC de volta para o host emissor original.
O host emissor recebe a mensagem de resposta contendo o endereço MAC do host de destino e armazena essas informações em uma tabela chamada tabela ARP.
Uma vez que o host emissor possui o endereço MAC do host de destino em sua tabela ARP, ele pode enviar quadros diretamente ao destino sem precisar fazer uma solicitação ARP novamente. No entanto, é importante ressaltar que como as mensagens ARP dependem de quadros de broadcast para entregar as solicitações, todos os hosts na rede IPv4 local devem estar no mesmo domínio de broadcast para o processo de ARP funcionar corretamente.








