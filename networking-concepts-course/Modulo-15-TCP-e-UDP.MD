# TCP e UDP

## TCP

O Protocolo de Controle de Transmissão (TCP - Transmission Control Protocol) é um dos principais protocolos de comunicação da Internet. Ele opera na camada de transporte do modelo TCP/IP e é responsável por garantir a entrega confiável de dados entre dispositivos em uma rede. 
o Protocolo de Controle de Transmissão (TCP) funciona através de uma série de etapas e mecanismos que garantem a comunicação confiável entre os dispositivos em uma rede:

1. Handshaking de Conexão: Antes de iniciar a transmissão de dados, o TCP estabelece uma conexão entre os dispositivos de origem e destino. Isso é feito por meio de um processo de três vias de handshaking. Primeiro, o cliente envia um segmento SYN (synchronize) para o servidor. O servidor responde com um segmento SYN-ACK (synchronize-acknowledgment), indicando que está pronto para estabelecer a conexão. Finalmente, o cliente envia um segmento ACK para confirmar a conexão. Com a conexão estabelecida, os dispositivos podem começar a enviar dados.

2. Segmentação de Dados: Antes de enviar os dados pela rede, o TCP divide-os em segmentos menores. Cada segmento contém uma parte dos dados, além de informações de controle, como números de sequência e de confirmação.

3. Transmissão e Recebimento de Dados: Uma vez que a conexão está estabelecida, os segmentos de dados são enviados do dispositivo de origem para o dispositivo de destino. O TCP monitora ativamente o envio e recebimento de segmentos, usando números de sequência para garantir que os segmentos sejam entregues na ordem correta e sem erros.

4. Controle de Fluxo: Durante a transmissão de dados, o TCP controla a quantidade de dados que pode ser enviada de uma vez, com base na capacidade da rede e na disponibilidade do receptor. Isso é feito através de um mecanismo de controle de fluxo, no qual o receptor informa ao remetente sua capacidade atual de processamento.

5. Controle de Congestionamento: O TCP monitora ativamente a rede em busca de sinais de congestionamento e ajusta a taxa de transmissão de dados para evitar congestionamentos. Isso é feito reduzindo a taxa de transmissão quando detecta congestionamento e aumentando gradualmente a taxa quando a rede está menos congestionada.

6. Confirmação de Recebimento: Após receber cada segmento de dados, o dispositivo de destino envia uma confirmação (ACK) de volta ao dispositivo de origem. Se o dispositivo de origem não receber uma confirmação dentro de um determinado período de tempo, ele retransmitirá o segmento.

O TCP garante que os dados sejam entregues de forma confiável, o que significa que ele verifica se todos os pacotes foram entregues sem erros e na ordem correta. Ele usa técnicas como retransmissão de pacotes perdidos, controle de fluxo e controle de congestionamento para garantir essa confiabilidade.

Usos do TCP:

* Transferência de arquivos: o TCP é amplamente utilizado para transferir arquivos pela Internet devido à sua confiabilidade na entrega de dados.
Navegação na web: sempre que você acessa um site, o TCP é usado para garantir que os dados do site sejam entregues ao seu navegador de forma confiável.
* E-mail: o TCP é usado para enviar e receber e-mails, garantindo que as mensagens sejam entregues corretamente.
* Aplicativos de mensagens instantâneas: aplicativos de mensagens como o WhatsApp e o Facebook Messenger usam o TCP para garantir a entrega de mensagens de forma confiável e em tempo real.



## UDP

Protocolo de Datagrama de Usuário (UDP - User Datagram Protocol) é outro protocolo importante da camada de transporte no modelo TCP/IP. Ele oferece uma comunicação não confiável e sem conexão entre os dispositivos em uma rede.

Ao contrário do TCP, que garante a entrega confiável de dados, o UDP não oferece garantias de entrega. Isso significa que os dados enviados por UDP podem ser perdidos, duplicados ou entregues fora de ordem. No entanto, essa abordagem tem a vantagem de ser mais rápida e eficiente em termos de largura de banda, pois não há sobrecarga associada ao controle de fluxo, controle de congestionamento e retransmissão de pacotes.
Ele 
é um protocolo sem conexão, o que significa que não é necessário estabelecer uma conexão antes de enviar dados. Os pacotes UDP são enviados individualmente e de forma independente uns dos outros. Isso torna o UDP ideal para aplicativos que exigem uma comunicação de baixa latência, como jogos online e transmissões de áudio e vídeo em tempo real.
Assim como o TCP, o UDP encapsula os dados em datagramas antes de enviá-los pela rede. Cada datagrama UDP contém informações de cabeçalho, incluindo portas de origem e destino, além dos dados propriamente ditos.
Como o UDP não oferece garantias de entrega, ele também não inclui mecanismos de controle de fluxo ou controle de congestionamento. Isso significa que os aplicativos que usam UDP devem implementar seus próprios mecanismos para lidar com esses problemas, se necessário.
Usos do UDP: O UDP é amplamente utilizado em uma variedade de aplicativos e serviços da Internet, especialmente aqueles que exigem comunicação em tempo real e baixa latência. 

Funcionamento:
1. Encapsulamento de Dados: Antes de enviar os dados pela rede, o UDP encapsula os dados em datagramas. Cada datagrama UDP consiste em um cabeçalho UDP seguido pelos dados a serem transmitidos. O cabeçalho UDP inclui informações como as portas de origem e destino, o comprimento do datagrama e um checksum opcional para detecção de erros.

2. Portas de Origem e Destino: As portas são números de identificação atribuídos a aplicativos específicos em um dispositivo. O cabeçalho UDP contém informações sobre a porta de origem do remetente e a porta de destino do destinatário. As portas permitem que os dispositivos identifiquem qual aplicativo está enviando ou recebendo os dados.

3. Comunicação Sem Conexão: O UDP é um protocolo sem conexão, o que significa que não é necessário estabelecer uma conexão antes de enviar dados. Os datagramas UDP são enviados individualmente e de forma independente uns dos outros. Isso torna o UDP ideal para aplicativos que exigem uma comunicação de baixa latência, como jogos online e transmissões de áudio e vídeo em tempo real.

4. Comunicação Não Confiável: Ao contrário do TCP, que oferece garantias de entrega confiável de dados, o UDP não oferece confiabilidade. Os datagramas UDP podem ser perdidos, duplicados ou entregues fora de ordem. Não há mecanismos embutidos no UDP para lidar com esses problemas. No entanto, isso resulta em uma menor sobrecarga de cabeçalho e maior eficiência em termos de largura de banda.

5. Checksum Opcional: O cabeçalho UDP pode incluir um campo de checksum opcional para detecção de erros nos dados. O checksum é calculado com base nos dados e é usado pelo destinatário para verificar a integridade dos dados recebidos. No entanto, como o checksum é opcional, sua utilização pode variar de acordo com a implementação do protocolo.

6.Sem Controle de Fluxo ou Congestionamento: O UDP não inclui mecanismos de controle de fluxo ou controle de congestionamento. Isso significa que não há restrições na taxa de envio de dados e nenhum mecanismo para evitar congestionamento na rede. Aplicativos que usam UDP devem implementar seus próprios mecanismos para lidar com esses problemas, se necessário.

Alguns exemplos de usos do UDP incluem:
Jogos online: Para comunicação rápida entre servidores e clientes em jogos online.
Transmissão de vídeo e áudio em tempo real: Para transmissão de streaming de vídeo e áudio, como em serviços de streaming de mídia e videoconferências.
DNS (Domain Name System): Para consultas de resolução de nome de domínio, onde a baixa latência é essencial.
VoIP (Voice over Internet Protocol): Para chamadas de voz pela Internet, onde a latência deve ser minimizada para uma comunicação clara e em tempo real.

## TCP vs UDP

1. Confiabilidade da Transmissão:
* TCP: Oferece uma comunicação confiável, garantindo a entrega ordenada e sem erros dos dados. Ele inclui mecanismos como retransmissão de pacotes, controle de fluxo e verificação de integridade para garantir a entrega confiável.
* UDP: Não oferece garantias de entrega confiável. Os dados podem ser perdidos, duplicados ou entregues fora de ordem. Não há mecanismos embutidos para recuperação de erros ou retransmissão de pacotes.

2. Tipo de Conexão:
* TCP: Estabelece uma conexão antes da transmissão de dados, seguindo um processo de handshaking de três vias (SYN, SYN-ACK, ACK). Ele mantém um estado de conexão durante toda a sessão de comunicação e garante uma entrega ordenada dos dados.
* UDP: É um protocolo sem conexão, o que significa que não há necessidade de estabelecer uma conexão antes de enviar os dados. Os datagramas UDP são enviados individualmente e de forma independente uns dos outros.

3. Overhead e Eficiência:
* TCP: Tem um maior overhead devido aos mecanismos de controle de fluxo, controle de congestionamento e garantias de entrega confiável. Isso pode resultar em uma menor eficiência em termos de largura de banda, especialmente para transferências de dados de curta duração.
* UDP: Possui um overhead menor, pois não inclui mecanismos de controle de fluxo, controle de congestionamento ou retransmissão de pacotes. Isso resulta em uma comunicação mais rápida e eficiente em termos de largura de banda, especialmente para transferências de dados em tempo real.

4. Aplicações Típicas:
* TCP: É amplamente utilizado em aplicativos que exigem comunicação confiável e entrega ordenada de dados, como transferência de arquivos (FTP), navegação na web (HTTP), e-mails (SMTP), entre outros.
* UDP: É comumente usado em aplicativos que priorizam a velocidade e a eficiência em termos de largura de banda, como jogos online, streaming de vídeo e áudio, transmissões ao vivo e consultas de DNS.

5. Exemplos de Uso:
* TCP: Navegação na web, envio de e-mails, transferência de arquivos, acesso remoto, chamadas VoIP.
* UDP: Jogos online, transmissão de vídeo e áudio em tempo real, streaming de mídia, comunicações de IoT (Internet das Coisas), consultas de DNS.

## Números de porta

O s números de porta na camada de transporte são identificadores numéricos utilizados para direcionar o tráfego de dados para aplicativos específicos em um dispositivo de rede. Eles são parte integrante dos protocolos TCP e UDP e desempenham um papel importante na comunicação entre dispositivos na Internet.

Tanto o TCP quanto o UDP utilizam números de porta para identificar os aplicativos aos quais os dados devem ser entregues em um dispositivo de destino. Cada protocolo tem seu próprio conjunto de números de porta, totalizando 65.536 portas disponíveis para cada protocolo.

Os números de porta são de 16 bits e variam de 0 a 65.535. Algumas portas são reservadas para usos específicos e não podem ser atribuídas aleatoriamente.
Portas Bem Conhecidas:

* As portas de número 0 a 1023 são conhecidas como portas bem conhecidas ou portas do sistema. Elas são reservadas para serviços comumente usados e atribuídas a aplicativos padrão. Por exemplo, a porta 80 é usada para tráfego HTTP (Hypertext Transfer Protocol), a porta 443 é usada para tráfego HTTPS (HTTP Secure) e a porta 25 é usada para tráfego SMTP (Simple Mail Transfer Protocol).
Portas Registradas:

* As portas de número 1024 a 49.151 são designadas como portas registradas. Elas são atribuídas a aplicativos específicos por organizações de registro, como a Internet Assigned Numbers Authority (IANA). Essas portas são usadas por uma variedade de serviços e aplicativos personalizados.
Portas Dinâmicas ou Privadas:

* As portas de número 49.152 a 65.535 são conhecidas como portas dinâmicas ou privadas. Elas são utilizadas por aplicativos cliente para estabelecer conexões com servidores em portas bem conhecidas ou registradas. Por exemplo, quando um navegador da web solicita uma página da web a um servidor web, ele geralmente usa uma porta dinâmica como a porta de origem.

**Atribuição de Portas:**
As portas são atribuídas dinamicamente pelos sistemas operacionais aos aplicativos que as solicitam. Quando um aplicativo inicia uma comunicação de rede, o sistema operacional geralmente seleciona uma porta disponível na faixa de portas dinâmicas e a associa ao aplicativo.
As portas são essenciais para a multiplexação de dados, permitindo que múltiplos aplicativos se comuniquem por meio de uma única conexão de rede. Cada pacote de dados inclui informações sobre a porta de origem e a porta de destino, garantindo que os dados sejam entregues ao aplicativo correto no dispositivo de destino.

Cada serviço ou aplicativo que deseja se comunicar através da rede é atribuído a uma porta específica no dispositivo de rede. Por exemplo, um servidor web geralmente usa a porta 80 para tráfego HTTP e a porta 443 para tráfego HTTPS. Os desenvolvedores de software especificam as portas que seus aplicativos usarão para se comunicar. Essas portas podem ser portas bem conhecidas, registradas ou portas dinâmicas, dependendo dos requisitos do aplicativo e das convenções de atribuição de portas.

* Multiplexação de Portas:
Um dispositivo de rede, como um servidor, pode ter vários serviços em execução simultaneamente, cada um utilizando uma porta diferente. Isso é possível devido ao conceito de multiplexação de portas.
A multiplexação de portas permite que o dispositivo receba dados de várias fontes (ou seja, aplicativos em execução em diferentes portas) e os direcione para os aplicativos corretos com base nas portas de destino.

Funcionamento: 

1. Comunicação entre Serviços: Quando um serviço em um dispositivo de rede deseja se comunicar com outro serviço em um dispositivo remoto, ele cria um pacote de dados contendo o endereço IP de destino e o número de porta de destino do serviço remoto.
2. O pacote de dados é então transmitido pela rede até o dispositivo de destino. O roteador encaminha o pacote para o dispositivo correto com base no endereço IP de destino.
3. No dispositivo de destino, o sistema operacional recebe o pacote e encaminha os dados para o serviço apropriado com base no número de porta de destino.
4. O serviço receptor processa os dados e pode enviar uma resposta de volta ao serviço de origem usando sua própria porta como porta de destino.

Protocolos como TCP e UDP facilitam a comunicação entre serviços em diferentes portas. O TCP oferece comunicação orientada à conexão, garantindo a entrega ordenada e confiável dos dados. O UDP, por outro lado, oferece comunicação sem conexão, sendo mais rápido, mas menos confiável.
Ambos os protocolos usam números de porta para direcionar os dados para os aplicativos corretos e garantir que os pacotes sejam entregues aos destinatários adequados.

## Números de porta TCP e UDP

Os serviços disponíveis na Internet, como DNS, Web, E-mail, FTP, Mensagem instantânea e VoIP, são acessados por meio de sistemas cliente/servidor. Cada serviço é identificado por um número de porta quando enviado usando TCP ou UDP. As portas são usadas para rastrear conversas entre cliente e servidor, com cada mensagem contendo uma porta de origem e destino. Por exemplo, HTTP usa a porta 80 com TCP, SMTP usa a porta 25 com TCP, e DNS usa a porta 53 com UDP.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/ec5f8ed2-f2ea-492d-890e-8a4015a7e971)

Quando um servidor recebe uma mensagem, ele precisa determinar qual serviço está sendo solicitado pelo cliente. Os clientes são configurados para usar portas de destino específicas para cada serviço. Por exemplo, navegadores da Web são configurados para enviar solicitações para servidores da Web na porta 80, usada para serviços da Web em HTTP.

As portas são gerenciadas pela ICANN (Internet Corporation for Assigned Names and Numbers) e são divididas em três categorias:

* Portas Bem Conhecidas: Variam de 1 a 1.023 e são associadas a aplicativos comuns de rede, como HTTP (porta 80) e FTP (porta 21).
* Portas Registradas: Variam de 1.024 a 49.151 e podem ser usadas por empresas para aplicativos específicos, como mensagens instantâneas.
* Portas Privadas: Variam de 49.152 a 65.535 e podem ser usadas por qualquer aplicativo como portas de origem.

A tabela abaixo mostra alguns números de porta comuns e os aplicativos associados a eles:

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/58d9b0f5-afd9-4513-9bae-8a72ca3ee201)

Algumas aplicações podem usar tanto TCP quanto UDP. Por exemplo, o DNS usa o protocolo UDP quando os clientes enviam requisições a um servidor DNS. Contudo, a comunicação entre dois servidores DNS sempre usa TCP.

Pesquise no site da IANA o registro de portas para visualizar a lista completa de números de portas e aplicativos associados.

### Pares de soquetes

As portas de origem e destino são inseridas no segmento, que por sua vez é encapsulado em um pacote IP. Este pacote IP contém os endereços IP de origem e destino. Quando combinados com o número de porta correspondente, seja de origem ou destino, formam um "socket".

Na figura fornecida, o PC está simultaneamente solicitando serviços FTP e Web do servidor de destino:

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/20e7c9c7-8150-4136-8715-bc343039a92d)

No exemplo dado, quando o PC gera uma solicitação FTP, inclui os endereços MAC da Camada 2 e os endereços IP da Camada 3. Essa solicitação também identifica o número da porta de origem 1305 (gerado dinamicamente pelo host) e a porta de destino, que representa o serviço FTP na porta 21. Da mesma forma, ao solicitar uma página da web do servidor, utiliza os mesmos endereços de Camada 2 e Camada 3, mas com o número da porta de origem 1099 (também gerado dinamicamente pelo host) e a porta de destino representando o serviço da Web na porta 80.

Os sockets são usados para identificar o servidor e o serviço sendo solicitado pelo cliente. Por exemplo, um socket de cliente pode ser representado como "192.168.1.5:1099", enquanto um socket de servidor da Web pode ser "192.168.1.7:80". Quando combinados, esses dois sockets formam um par de sockets, como "192.168.1.5:1099, 192.168.1.7:80".

Os sockets permitem que vários processos em execução em um cliente se diferenciem uns dos outros e que várias conexões com um processo no servidor sejam distintas entre si.

Esses números de porta atuam como endereços de retorno para a aplicação que faz a solicitação. A camada de transporte acompanha essa porta e a aplicação que iniciou a solicitação, garantindo que quando uma resposta é retornada, ela seja encaminhada para a aplicação correta.

### O Comando netstat


Para listar as conexões TCP ativas em um host de rede usando o comando netstat, você pode digitar o seguinte comando no prompt de comando:
'''
netstat -an
'''

Este comando irá listar todos os sockets de rede e suas respectivas conexões ativas. Aqui está o que cada coluna representa:

* Proto: O protocolo usado pela conexão (por exemplo, TCP).
* Endereço Local: O endereço IP local e a porta.
* Endereço Externo: O endereço IP externo e a porta (se aplicável).
* Estado: O estado atual da conexão (por exemplo, ESTABLISHED, LISTENING, etc.).

Isso pode ajudar a identificar quais conexões estão sendo feitas e se há alguma atividade suspeita ou não autorizada.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/586e631a-4c64-411f-91b5-8d7d7778f0f2)

