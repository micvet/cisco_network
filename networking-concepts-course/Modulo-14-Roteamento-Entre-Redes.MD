# Roteamento entre Redes

## A necessidade do roteamento

O roteamento é essencial para permitir que dispositivos em diferentes redes se comuniquem entre si, como residências, empresas e a Internet. Roteadores são dispositivos de rede que conectam várias redes IP de Camada 3 e desempenham funções importantes na distribuição eficiente do tráfego.

Enquanto os switches operam na Camada 2 e usam endereços MAC para encaminhar pacotes, os roteadores operam na Camada 3 e baseiam suas decisões de encaminhamento nos endereços IP. Quando um dispositivo envia um pacote para um destino remoto, o roteador examina o endereço IP de destino para determinar o melhor caminho para encaminhar o pacote.

O roteador desencapsula o pacote, lê o endereço IP de destino e usa a porção de rede desse endereço para identificar a rede correta para encaminhar o pacote. Se os endereços IP de origem e destino estiverem em redes diferentes, o pacote é encaminhado para o roteador adequado.

Por exemplo, se um host na rede 1.1.1.0 precisa enviar um pacote para um host na rede 5.5.5.0, o pacote é enviado para o roteador. O roteador lê o endereço IP de destino, determina a rota apropriada e encaminha o pacote para o destino, encapsulando-o novamente em um novo quadro para entrega.

Assim, os roteadores desempenham um papel crucial no encaminhamento eficiente de pacotes entre redes, garantindo que as mensagens cheguem aos seus destinos corretamente, mesmo quando os hosts estão em redes distintas.

### Entradas da Tabela de Roteamento

Os roteadores movem informações entre redes locais e remotas, utilizando tabelas de roteamento para armazenar informações sobre como alcançar essas redes. Essas tabelas contêm endereços de redes e os melhores caminhos para acessá-los, mas não estão relacionadas aos endereços individuais dos hosts.

As tabelas de roteamento podem ser atualizadas dinamicamente, com informações recebidas de outros roteadores na rede, ou inseridas manualmente por um administrador de rede. Os roteadores usam essas tabelas para determinar qual interface deve ser usada para encaminhar uma mensagem para o destino desejado.

Se um roteador não puder determinar para onde encaminhar uma mensagem, ele a descartará. Para evitar isso, os administradores de rede podem configurar uma rota padrão na tabela de roteamento. Esta rota padrão especifica a interface através da qual o roteador envia um pacote contendo um endereço de rede IP desconhecido, normalmente conectando-se a outro roteador que pode encaminhar o pacote para a rede de destino final.

**Tabela de roteamento:**

Uma tabela de roteamento é uma estrutura de dados utilizada por roteadores e sistemas operacionais de rede para determinar o caminho mais adequado para encaminhar pacotes de dados de origem para seus destinos. Entre suas funcionalidades, podemos destacar:

1. Armazenamento de informações de roteamento: contém informações sobre as redes alcançáveis e os caminhos disponíveis para chegar a essas redes. Cada entrada na tabela de roteamento inclui o endereço da rede de destino e o próximo salto, ou seja, o endereço IP do próximo roteador na rota.

2. Decisão de encaminhamento: quando um roteador recebe um pacote de dados, ele consulta sua tabela de roteamento para determinar qual interface deve ser usada para encaminhar o pacote. Ele seleciona a entrada na tabela de roteamento que melhor corresponde ao endereço de destino do pacote e utiliza as informações contidas nessa entrada para tomar a decisão de encaminhamento.

3. Atualização dinâmica e estática: podem ser atualizadas dinamicamente por meio de protocolos de roteamento, nos quais os roteadores trocam informações de roteamento entre si para manter suas tabelas atualizadas com as melhores rotas disponíveis.
Além disso, os administradores de rede podem configurar rotas estáticas manualmente, adicionando entradas à tabela de roteamento para redes específicas ou para definir uma rota padrão.

4. Priorização de rotas: podem incluir várias rotas para o mesmo destino, com diferentes métricas ou custos associados a cada rota. Isso permite que o roteador selecione a rota mais adequada com base em critérios como largura de banda, atraso ou confiabilidade.

5. Resolução de problemas de rede: são uma ferramenta valiosa para diagnóstico e resolução de problemas de rede. Os administradores de rede podem examinar a tabela de roteamento para identificar rotas incorretas, problemas de conectividade ou gargalos de tráfego.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/863c5f27-1b9d-4358-9e70-0abbe5140602)

### O Gateway Padrão

Quando um host precisa enviar uma mensagem para um destino em uma rede remota, ele usa um roteador. O host inclui o endereço IP do destino no pacote, mas ao encapsular o pacote em um quadro, ele utiliza o endereço MAC do roteador como destino. O host de origem determina o endereço MAC do roteador através do endereço de gateway padrão configurado em suas configurações de TCP/IP. Esse endereço é o da interface do roteador na mesma rede local do host de origem.

Todos os hosts na rede local usam esse endereço de gateway padrão para enviar mensagens ao roteador. Utilizando o ARP, o host de origem descobre o endereço MAC correspondente ao endereço IPv4 do gateway padrão. Esse endereço MAC é então colocado no quadro, direcionando-o para o roteador e permitindo a comunicação com redes remotas.

É fundamental que o gateway padrão correto esteja configurado em cada host na rede local. Caso contrário, se o gateway padrão não estiver definido ou estiver incorreto nas configurações TCP/IP, as mensagens endereçadas a hosts em redes remotas não poderão ser entregues.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/7c766d1c-f21b-42ea-b784-26572a7a0d9b)

## Criando uma LAN

### Redes de Área Local (LAN)

O termo "Rede de Área Local" (LAN) refere-se a uma rede ou grupo de redes locais interconectadas sob o mesmo controle administrativo. Originalmente, as LANs eram pequenas redes em uma única localização física, mas agora podem incluir várias centenas de hosts em vários prédios. Todas as redes locais em uma LAN são administradas conjuntamente e geralmente usam protocolos Ethernet ou sem fio, suportando altas taxas de transmissão.

Uma "Intranet" é uma LAN privada pertencente a uma organização e acessada exclusivamente por membros autorizados.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/3f2b8347-a1be-4e62-b84f-c4f368b79a77)

###  Segmentos de rede local e remota

Dentro de uma LAN, os hosts podem ser colocados em uma única rede local ou divididos entre várias redes interconectadas por um dispositivo na camada de distribuição. A decisão sobre como posicionar os hosts depende dos objetivos específicos da rede e dos requisitos de desempenho.

Essa distribuição pode ocorrer de algumas formas. Vejamos:

* Todos os hosts em um segmento de rede local:

Colocar todos os hosts em uma única rede local permite que eles se comuniquem diretamente entre si, facilitando a visibilidade e o acesso aos dispositivos. No entanto, à medida que a rede cresce, pode ocorrer um aumento significativo no tráfego de broadcast, o que pode diminuir o desempenho da rede. Em um projeto de rede simples, essa abordagem pode ser vantajosa devido à menor complexidade e custo reduzido. No entanto, para redes maiores, pode ser benéfico mover alguns hosts para redes remotas para melhorar o desempenho geral da rede.

**Vantagens de um único segmento local:**

Adequado para redes mais simples
Menos complexidade e custo reduzido
Facilita a comunicação direta entre dispositivos
Transferência de dados mais rápida e acesso facilitado aos dispositivos

**Desvantagens de um único segmento local:**

Aumento do tráfego de broadcast, o que pode diminuir o desempenho da rede
Dificuldade na implementação de QoS (Quality of Service)
Dificuldade na implementação de medidas de segurança

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/a089a838-bdd0-4aa8-9a53-65e3c3a76720)

* Hosts em um segmento remoto:
Ao adicionar hosts em uma rede remota, o impacto nas demandas de tráfego pode ser reduzido, já que as redes são divididas e os pacotes de dados são encaminhados de forma mais eficiente. No entanto, sem o uso de roteamento, os hosts em uma rede não podem se comunicar diretamente com os hosts em outra rede. Isso aumenta a complexidade da configuração de rede e pode introduzir atrasos nos pacotes enviados de uma rede local para outra.

**Vantagens:**

Mais adequado para redes maiores e complexas
Divide domínios de transmissão e reduz o tráfego
Pode melhorar o desempenho em cada segmento
Oculta as máquinas para usuários em outros segmentos de rede local
Pode fornecer maior segurança
Pode melhorar a organização da rede

**Desvantagens:**

Requer o uso de roteamento na camada de distribuição
Roteadores podem retardar o tráfego entre segmentos
Maior complexidade e custos adicionais (necessita de roteadores)

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/90582e9b-d765-4d26-8d06-503b223bf200)



