# **Curso Conceitos Básicos de Redes - Cisco Network Academy** <br>

# Módulo 2

## Clientes e Servidores

Todos os computadores conectados a uma rede e envolvidos na comunicação são chamados de hosts. Hosts podem desempenhar o papel de cliente, servidor ou ambos, 
dependendo do software instalado.
Servidores são hosts que fornecem informações, como e-mails ou páginas da web, para outros hosts na rede. Cada serviço requer um software de servidor específico; 
por exemplo, um servidor web usa um software de servidor web para fornecer serviços online.
Os clientes são hosts que solicitam e exibem informações obtidas do servidor. Exemplos de software cliente incluem navegadores da web como Internet Explorer, Safari, 
Mozilla Firefox ou Chrome.

### Redes ponto-a-ponto

Redes ponto-a-ponto (P2P) são redes onde computadores atuam como clientes e servidores simultaneamente ou separadamente. Em ambientes pequenos, muitos computadores podem funcionar como clientes e servidores, formando uma rede P2P. A rede P2P mais simples envolve dois computadores conectados diretamente, podendo trocar dados e serviços.Para redes P2P maiores, é necessário um dispositivo de rede, como um switch, para interconectar os computadores. Uma desvantagem das redes P2P é que o desempenho de um host pode ser afetado se atuar como cliente e servidor ao mesmo tempo. Em empresas de grande porte, servidores dedicados são necessários para lidar com altos volumes de tráfego de rede. 

* Vantagens da rede ponto-a-ponto:

  * Fácil de configurar.
  * Menos complexo.
  * Menor custo, pois dispositivos de rede e servidores dedicados podem não ser necessários.
  * Pode ser usada para tarefas simples, como transferir arquivos e compartilhar impressoras.

* Desvantagens da rede ponto-a-ponto:
  * Nenhuma administração centralizada.
  * Menor segurança.
  * Não é escalável.
  * Todos os dispositivos podem atuar como clientes e servidores, o que pode afetar o desempenho.

### Aplicações ponto-a-ponto

Aplicações ponto-a-ponto (P2P) permitem que um dispositivo atue como cliente e servidor simultaneamente. Todos os clientes também são servidores e vice-versa neste modelo e cada dispositivo final em uma aplicação P2P deve fornecer uma interface de usuário e executar um serviço em segundo plano.
Algumas aplicações P2P usam um sistema híbrido, onde o compartilhamento de recursos é descentralizado, mas os índices que apontam para as localizações de recursos são armazenados em um diretório centralizado. Em um sistema híbrido, cada peer acessa um servidor de índice para localizar recursos armazenados em outros peers.

### Múltiplas funções na rede

Um computador com software de servidor pode atender a vários clientes simultaneamente, oferecendo diversos serviço; um único computador pode executar vários tipos de software de servidor, como servidor de arquivos, servidor web e servidor de e-mail, em casa ou em uma empresa pequena. Da mesma forma, um único computador pode executar vários tipos de software cliente, com um software cliente para cada serviço necessário. Com vários softwares cliente instalados, um cliente pode se conectar a vários servidores ao mesmo tempo, permitindo tarefas como verificar e-mails, visualizar páginas web, enviar mensagens instantâneas e ouvir rádio pela Internet.

## Infraestrutura de Rede

O caminho de uma mensagem pode ser simples, como um único cabo entre dois computadores, ou complexo, atravessando redes globais. A infraestrutura de rede é a plataforma que suporta as comunicações, fornecendo canais estáveis e confiáveis, e inclui três categorias de componentes: dispositivos finais, dispositivos intermediários e meios físicos de rede.

* Dispositivos finais são os extremos da comunicação. São os dispositivos de rede mais familiares para as pessoas, e servem como a interface entre os usuários e a rede de comunicação. Alguns exemplos incluem computadores (estações de trabalho, laptops, servidores de arquivo, servidores Web), impressoras de rede, telefones, equipamentos de teleconferência, câmeras de segurança e dispositivos móveis (como smartphones, tablets, PDAs, leitores de cartão de débito/crédito sem fio e scanners de código de barras).

Um dispositivo final também é conhecido como host, e é a origem ou destino de uma mensagem transmitida pela rede. Para identificar hosts de forma exclusiva, são utilizados endereços. Quando um host inicia a comunicação, ele usa o endereço do host de destino para especificar onde a mensagem deve ser enviada.

![image](https://github.com/micvet/cisco_network/assets/86981990/4ce0e197-2e2f-425a-9cb7-ad2c18ffa594)

* Dispositivos intermediários incluem roteadores, switches e dispositivos de firewall, que facilitam o tráfego de rede.

![image](https://github.com/micvet/cisco_network/assets/86981990/58b63bf5-b062-4470-90b5-b83e24d171fc)

* Os meios físicos de rede são os meios pelos quais os dados são transmitidos, como redes sem fio, redes LAN com fio e redes WAN.

![image](https://github.com/micvet/cisco_network/assets/86981990/27e4913e-ca1c-4b4a-be19-b774b72104c3)

Dispositivos e meios físicos constituem os elementos físicos, ou hardware, de uma rede. Isso inclui componentes visíveis como laptops, PCs, switches, roteadores, access points sem fio e os cabos usados para conectar esses dispositivos. Em certos casos, alguns componentes podem não ser tão visíveis, como em meios físicos sem fio, onde as mensagens são transmitidas por meio de frequências de rádio invisíveis ou ondas infravermelhas.

## ISP's

Um provedor de serviços de Internet (ISP) atua como o elo entre a rede doméstica e a Internet. Pode ser uma empresa de TV a cabo local, um provedor de telefonia fixa, uma rede celular ou um provedor independente que aluga largura de banda de outra empresa. Além de fornecer conectividade, muitos ISPs oferecem serviços adicionais como contas de e-mail, armazenamento de rede, hospedagem de sites e serviços de segurança ou backup automático.

Os ISPs desempenham um papel fundamental na comunicação global da Internet, conectando usuários em todo o mundo através de uma rede de links interconectados. Esses links formam uma estrutura hierárquica que garante que o tráfego da Internet siga o caminho mais curto da origem ao destino.

![image](https://github.com/micvet/quality-assurance/assets/86981990/9486c59f-2f0b-48cc-8830-0b5b69936142)

### Backbone
É a espinha dorsal de uma rede. É a infraestrutura por trás da "estrada de informações" que fornece links de dados de alta velocidade para conectar redes de provedores de serviços globalmente. O principal meio físico usado para conectar o backbone da Internet é o cabo de fibra óptica, frequentemente instalado no subsolo para conectar cidades dentro de continentes e também passando sob o mar para conectar continentes, países e cidades.
