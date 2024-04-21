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

'''' 
nslookup example.com
''''

Este comando retornará o endereço IP associado ao nome de domínio "example.com".

Além disso, o "nslookup" também pode ser usado interativamente, o que permite ao usuário executar várias consultas DNS sem sair do prompt de comando. Para entrar no modo interativo, basta digitar "nslookup" sem argumentos e pressionar Enter. A partir daí, o usuário pode inserir comandos de consulta, como:

''''
server 8.8.8.8
''''

Este comando instrui o "nslookup" a usar o servidor DNS com o endereço IP "8.8.8.8" para consultas subsequentes.

## Clientes e Servidores Web

Quando um cliente Web recebe o endereço IP de um servidor Web, ele utiliza esse endereço juntamente com a porta padrão 80 para solicitar serviços da Web. Essa solicitação é enviada ao servidor usando o protocolo HTTP (Hypertext Transfer Protocol).

Além disso, o conteúdo de uma página Web é codificado utilizando linguagens de marcação especializadas, sendo o HTML (HyperText Markup Language) a mais comum. O HTML define a estrutura e o formato da página, incluindo texto, gráficos e fontes a serem exibidos. Ele informa ao navegador como renderizar a página Web para o usuário final.

O protocolo HTTP não oferece segurança, tornando as informações vulneráveis a interceptação durante a transmissão pela rede. Para garantir a segurança dos dados, o HTTP pode ser usado em conjunto com protocolos de transporte seguros. As solicitações feitas com HTTP seguro são direcionadas para a porta 443 e usam "https" no endereço do site no navegador, em vez de "http".

Embora existam muitos servidores web e clientes web diferentes disponíveis, os padrões de HTML e do protocolo HTTP permitem que esses servidores e clientes de diversos fabricantes interajam sem dificuldades. Isso facilita a compatibilidade e a interoperabilidade entre diferentes sistemas na Internet.


## 





