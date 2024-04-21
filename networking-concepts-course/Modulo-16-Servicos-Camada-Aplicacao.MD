# Serviços da Camada de Aplicação

## Relação cliente servidor

Os serviços online que usamos diariamente, como e-mails, redes sociais e compras online, dependem de uma complexa rede de servidores, clientes e dispositivos de rede. Os servidores são hosts que executam aplicativos para fornecer informações ou serviços a outros dispositivos conectados à rede, como sites e e-mails. Essas interações são possíveis graças ao uso de padrões e protocolos que permitem a comunicação entre diferentes clientes e servidores.

Um exemplo de software cliente é um navegador da web, como Chrome ou Firefox. Um único computador pode executar vários tipos de software cliente simultaneamente, como verificar e-mails, visualizar páginas da web, trocar mensagens instantâneas e reproduzir áudio. Abaixo estão listados três tipos comuns de software de servidor.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/33282856-f21c-42c8-b8fc-e671cfe297d1)


A comunicação cliente-servidor é um modelo de comunicação em rede no qual um dispositivo, chamado cliente, solicita serviços ou recursos a outro dispositivo, chamado servidor. Esse modelo é amplamente utilizado na internet e em redes locais para permitir a troca de informações e serviços entre diferentes computadores.

A comunicação cliente-servidor é frequentemente descrita em termos de camadas, que representam diferentes níveis de abstração e funcionalidade.

O processo de comunicação entre cliente e servidor geralmente segue os seguintes passos:

* Resolução de DNS (Domain Name System): Quando um cliente precisa se comunicar com um servidor através de um nome de domínio, ele primeiro realiza uma consulta DNS para traduzir o nome de domínio em um endereço IP correspondente.
  * DNS lookup é o processo pelo qual um dispositivo realiza uma consulta ao sistema de nomes de domínio (DNS) para traduzir um nome de domínio legível por humanos em um endereço IP correspondente, que é necessário para localizar o servidor associado a esse domínio na internet.
  * Quando um usuário digita um nome de domínio (por exemplo, www.exemplo.com) em um navegador da web ou em qualquer aplicativo que precise se comunicar com um servidor remoto, o dispositivo precisa descobrir o endereço IP associado a esse nome de domínio. Esse processo ocorre em várias etapas:
  * Consulta Local: Primeiro, o dispositivo verifica se o nome de domínio está armazenado em cache localmente. Se uma consulta recente foi feita para o mesmo nome de domínio, o endereço IP pode ser recuperado do cache local, economizando tempo e recursos de rede.
  * Consulta ao Servidor DNS Local: Se o nome de domínio não estiver em cache localmente, o dispositivo consultará um servidor DNS local configurado em suas configurações de rede. Esse servidor DNS pode ser fornecido pelo provedor de serviços de Internet (ISP) ou configurado manualmente pelo usuário.
  * Consulta aos Servidores DNS Raiz: Se o servidor DNS local não puder resolver o nome de domínio, ele fará uma consulta aos servidores DNS raiz da internet. Esses servidores mantêm informações sobre os servidores DNS autoritativos responsáveis pelos domínios de nível superior (como .com, .org, .net).
  * Consulta aos Servidores DNS Autoritativos: Com base nas informações fornecidas pelos servidores DNS raiz, o servidor DNS local consulta os servidores DNS autoritativos responsáveis pelo domínio específico (por exemplo, exemplo.com). Esses servidores têm registros que mapeiam nomes de domínio para endereços IP.
  * Resposta e Cache: O servidor DNS autoritativo retorna o endereço IP associado ao nome de domínio solicitado para o servidor DNS local, que por sua vez envia a informação de volta para o dispositivo solicitante. O endereço IP é então armazenado em cache localmente para consultas futuras.

* Estabelecimento da Conexão TCP: Se o protocolo utilizado for TCP, o cliente e o servidor estabelecem uma conexão TCP usando um handshake de três vias (SYN, SYN-ACK, ACK). Isso estabelece um canal de comunicação bidirecional entre os dois dispositivos.
* Troca de Dados: Após a conexão ser estabelecida, o cliente envia uma solicitação ao servidor, especificando o serviço desejado. O servidor processa a solicitação e envia uma resposta de volta ao cliente com os dados solicitados ou com uma confirmação da operação realizada.
* Fechamento da Conexão: Após a comunicação ser concluída, a conexão TCP é encerrada usando um handshake de quatro vias (FIN, ACK, FIN, ACK), liberando os recursos associados à conexão.

### URI, URN e URL

Recursos e serviços da Web, como APIs RESTful,  são identificados por meio de uma URI (Identificador de Recurso Uniforme), que é uma sequência de caracteres que aponta para um recurso específico na rede. Uma URI possui duas especializações:

* URN (Nome de Recurso Uniforme): Identifica o espaço do nome do recurso sem referenciar o protocolo.
* URL (Localizador de Recurso Uniforme): Define o local do recurso na rede e geralmente inclui o protocolo usado, como HTTP ou HTTPS. Outros protocolos como FTP, SFTP e SSH também podem ser usados.

**Partes de uma URI**:

* Protocolo/esquema: Indica o protocolo usado para acessar o recurso, como HTTPS, FTP, SFTP, etc.
* Nome do host: O nome do servidor onde o recurso está localizado.
* Caminho e nome do arquivo: O caminho para o recurso no servidor, incluindo o nome do arquivo, se aplicável.
* Fragmento: Uma parte opcional que indica uma seção específica dentro do recurso, precedido pelo símbolo "#".

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/5f40a286-c982-4f6d-b665-10be7dad8984)

## Serviços de Aplicações de Rede

Os serviços de internet mais comuns incluem pesquisas online, mídias sociais, streaming de áudio e vídeo, lojas online, e-mail e mensagens. Cada um desses serviços depende dos protocolos TCP/IP para comunicação confiável entre clientes e servidores. Os servidores que oferecem esses serviços variam de acordo com a função, como servidores web, de mídia, de e-mail e de mensagens.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/b8a08113-2678-4e94-8f7e-3e384011457e)

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/fcae9e5f-7cf9-4e51-bf96-623c39a5152e)

## Domain Name System Service (DNS)

### O Comando nslooup

O comando "nslookup" é uma ferramenta de linha de comando utilizada em sistemas operacionais como Windows e Unix-like (Linux, macOS) para realizar consultas DNS (Domain Name System). O DNS é o sistema que traduz nomes de domínio legíveis por humanos, como "example.com", em endereços IP numéricos, como "192.0.2.1", que os computadores usam para se comunicar na Internet.

O "nslookup" permite aos usuários consultar servidores DNS para obter informações sobre diversos tipos de registros DNS associados a um nome de domínio específico. Isso pode incluir, por exemplo, o endereço IP associado a um nome de domínio (consulta A), os registros de serviço de correio (consulta MX), registros de texto (consulta TXT), entre outros.

O uso básico do comando "nslookup" envolve fornecer o nome de domínio que se deseja consultar como argumento, seguido de uma opção que especifica o tipo de registro DNS que se deseja obter. Por exemplo:

'''
nslookup example.com
'''

Este comando retornará o endereço IP associado ao nome de domínio "example.com".

Além disso, o "nslookup" também pode ser usado interativamente, o que permite ao usuário executar várias consultas DNS sem sair do prompt de comando. Para entrar no modo interativo, basta digitar "nslookup" sem argumentos e pressionar Enter. A partir daí, o usuário pode inserir comandos de consulta, como:

'''
server 8.8.8.8
'''

Este comando instrui o "nslookup" a usar o servidor DNS com o endereço IP "8.8.8.8" para consultas subsequentes.

## Clientes e Servidores Web

Quando um cliente Web recebe o endereço IP de um servidor Web, ele utiliza esse endereço juntamente com a porta padrão 80 para solicitar serviços da Web. Essa solicitação é enviada ao servidor usando o protocolo HTTP (Hypertext Transfer Protocol).

Além disso, o conteúdo de uma página Web é codificado utilizando linguagens de marcação especializadas, sendo o HTML (HyperText Markup Language) a mais comum. O HTML define a estrutura e o formato da página, incluindo texto, gráficos e fontes a serem exibidos. Ele informa ao navegador como renderizar a página Web para o usuário final.

O protocolo HTTP não oferece segurança, tornando as informações vulneráveis a interceptação durante a transmissão pela rede. Para garantir a segurança dos dados, o HTTP pode ser usado em conjunto com protocolos de transporte seguros. As solicitações feitas com HTTP seguro são direcionadas para a porta 443 e usam "https" no endereço do site no navegador, em vez de "http".

Embora existam muitos servidores web e clientes web diferentes disponíveis, os padrões de HTML e do protocolo HTTP permitem que esses servidores e clientes de diversos fabricantes interajam sem dificuldades. Isso facilita a compatibilidade e a interoperabilidade entre diferentes sistemas na Internet.


## Clientes e servidores FTP


Além dos serviços da Web, outro serviço comum na Internet é o de transferência de arquivos.

O File Transfer Protocol (FTP) oferece uma maneira simples de transferir arquivos entre computadores. Um cliente FTP pode acessar um servidor FTP para realizar funções de gerenciamento de arquivos, como fazer uploads e downloads.

O servidor FTP permite que os clientes troquem arquivos entre dispositivos e realizem operações de gerenciamento de arquivos, como exclusão ou renomeação, enviando comandos específicos. Para isso, o serviço FTP utiliza duas portas diferentes para a comunicação entre cliente e servidor.

No exemplo mostrado na figura, para iniciar uma sessão de FTP, as solicitações de conexão de controle são enviadas para o servidor pela porta TCP 21. Uma vez estabelecida a sessão, o servidor utiliza a porta TCP 20 para transferir os dados dos arquivos.

O software de cliente FTP está integrado em sistemas operacionais de computador e na maioria dos navegadores Web. Além disso, existem clientes FTP independentes que oferecem uma interface fácil de usar, com muitas opções, baseada em GUI (Interface Gráfica do Usuário).
Com base nos comandos enviados pela conexão de controle, os dados podem ser baixados do servidor ou carregados do cliente.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/e8200c58-0ffe-46b8-a5f8-1e683d0c5687)

## Terminais Virtuais

### Telnet


Antes dos computadores desktop com interfaces gráficas, sistemas baseados em texto eram comuns, muitas vezes consistindo apenas de terminais de exibição conectados fisicamente a um computador central. Com a disponibilidade de redes, surgiu a necessidade de acessar remotamente esses sistemas de computador da mesma forma que os terminais conectados diretamente.

O Telnet foi desenvolvido para atender a essa necessidade no início da década de 70 e é um dos protocolos e serviços mais antigos da camada de Aplicação da suite TCP/IP. Ele oferece um método padrão para emular dispositivos terminais baseados em texto na rede de dados. Tanto o protocolo quanto o software cliente que o implementa são comumente chamados de Telnet. Os servidores Telnet aguardam solicitações de clientes na porta TCP 23.

Uma conexão Telnet, apropriadamente chamada de sessão ou conexão de terminal virtual (vty), cria um dispositivo virtual que oferece os mesmos recursos de uma sessão de terminal, incluindo acesso à interface de linha de comando (CLI) do servidor, sem a necessidade de um dispositivo físico para conexão direta.

Na figura, o cliente está conectado remotamente ao servidor via Telnet, permitindo que execute comandos como se estivesse conectado localmente ao servidor.

É importante observar que o Telnet não é considerado seguro devido à falta de criptografia, sendo recomendado o uso do SSH na maioria dos ambientes. No entanto, o Telnet é frequentemente utilizado em exemplos por sua simplicidade de configuração.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/bcf2b14f-7ba0-4478-94f1-2ea0ce868cc4)

### Problemas de segurança com Telnet

Quando uma conexão Telnet é estabelecida, os usuários podem executar qualquer função autorizada no servidor, semelhante a uma sessão de linha de comando no próprio servidor. Eles podem iniciar e parar processos, configurar dispositivos e até mesmo desligar o sistema.

No entanto, o Telnet não suporta o transporte de dados criptografados. Todos os dados trocados durante as sessões Telnet são transportados como texto simples pela rede, o que significa que podem ser facilmente interceptados e compreendidos.

Por outro lado, o protocolo Secure Shell (SSH) oferece uma alternativa segura para acesso ao servidor. Ele fornece uma estrutura para proteger o login remoto e outros serviços de rede, além de autenticação mais forte que o Telnet. O SSH também suporta o transporte de dados de sessão usando criptografia.

Como melhor prática, os profissionais de rede devem sempre usar o SSH em vez do Telnet, sempre que possível, para garantir a segurança da comunicação. Na figura ilustrada, é evidente como os dados capturados pelo hacker durante o uso do Telnet são claramente legíveis, enquanto os dados capturados durante o uso do SSH estão criptografados, tornando a comunicação mais segura.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/df51ddca-13f5-466e-a5ba-c019b61cdd7e)

## E-mail e Mensagens

O e-mail é um dos aplicativos cliente/servidor mais populares na Internet. Servidores de e-mail executam software que permite interagir com clientes e outros servidores de e-mail pela rede.

Cada servidor de e-mail recebe e armazena e-mails de usuários que têm caixas de correio configuradas nele. Os usuários acessam seus e-mails usando clientes de e-mail, muitas vezes através de clientes baseados na Web, como Microsoft 365, Yahoo e Gmail.

As caixas de correio são identificadas no formato usuário@empresa.domínio.

Vários protocolos são utilizados no processamento de e-mails, incluindo SMTP (envio de e-mails), POP3 e IMAP4 (recuperação de e-mails).

Na figura, mostra-se uma transação de e-mail em que um remetente envia um e-mail usando SMTP para um destinatário através do servidor de e-mail do ISP A. O e-mail chega ao servidor de e-mail do ISP B do destinatário, que o destinatário lê usando os protocolos IMAP ou POP.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/9a2c5425-0757-497c-89ac-75a6c81ded78)

### Protocolos de e-mail

* **SMTP**
O SMTP (Simple Mail Transfer Protocol) é utilizado por clientes de e-mail para enviar mensagens para o servidor de e-mail local. O servidor local determina se a mensagem é destinada a uma caixa de correio local ou a uma caixa de correio em outro servidor.

Se a mensagem precisar ser enviada para um servidor diferente, o SMTP também será utilizado entre esses dois servidores. As solicitações SMTP são enviadas para a porta 25.

No processo de envio de e-mail, o SMTP desempenha um papel fundamental, garantindo a entrega adequada da mensagem ao destino pretendido.

* **POP**

O protocolo POP (POP3) permite que um servidor compatível com clientes POP receba e armazene mensagens destinadas aos seus usuários. Quando o cliente se conecta ao servidor de e-mail, as mensagens são baixadas para o cliente. Por padrão, as mensagens não são mantidas no servidor após serem acessadas pelo cliente. Os clientes se conectam aos servidores POP3 na porta 110.

* **IMAP**
O protocolo IMAP (IMAP4) também permite que um servidor compatível com clientes IMAP receba e armazene mensagens destinadas aos seus usuários. No entanto, ao contrário do POP, o IMAP mantém as mensagens nas caixas de correio no servidor, a menos que sejam excluídas pelo usuário. O IMAP4, a versão mais recente, ouve solicitações do cliente na porta 143.

## Mensagens de texto

As mensagens de texto são uma das ferramentas de comunicação mais populares em uso atualmente. Além disso, o software de mensagens de texto está integrado a muitos aplicativos online, aplicativos de smartphones e sites de mídia social.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/d5d686ca-e9bb-4550-bb73-fe5f641f04c7)

Ambos os clientes podem enviar e receber mensagens simultaneamente.

As mensagens de texto, também conhecidas como mensagens instantâneas, mensagens diretas, mensagens privadas ou bate-papo, permitem que os usuários se comuniquem pela Internet em tempo real. Elas são frequentemente acessadas por meio de clientes baseados na Web integrados a mídias sociais ou sites de compartilhamento de informações, permitindo a conexão apenas com outros usuários do mesmo site.

Além disso, existem vários clientes de mensagens de texto autônomos, como Cisco Webex Teams, Microsoft Teams, WhatsApp, Facebook Messenger, entre outros, disponíveis para uma ampla variedade de sistemas operacionais e dispositivos, incluindo versões móveis. Esses aplicativos não apenas suportam mensagens de texto, mas também permitem a transferência de documentos, vídeos, músicas e arquivos de áudio.

## Chamadas telefônicas pela Internet


Fazer chamadas telefônicas pela Internet está se popularizando com a Telefonia de Internet, que usa tecnologia peer-to-peer similar às mensagens instantâneas. A tecnologia VoIP converte sinais de voz em dados digitais encapsulados em pacotes IP. Os usuários precisam de um software de telefone IP e um nome exclusivo para receber chamadas, utilizando alto-falantes e microfone, podendo conectar um headset ao computador. Chamadas são feitas para outros usuários do serviço selecionando o nome na lista. Chamadas para telefones convencionais exigem um gateway para acessar a PSTN, podendo haver taxas associadas. Portas e protocolos variam conforme o software utilizado.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/dd74645e-8858-4a00-a5ed-206cf04dcfad)





