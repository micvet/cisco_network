# Princípios da comunicação

## Protocolos de comunicação

Comunicação em nosso dia a dia ocorre em diferentes cenários, com diferentes expectativas e normas. Cada situação da nossa rotina exige comportamentos e estilos específicos. E antes de nos comunicarmos, 
estabelecemos acordos sobre como proceder na conversa. São eles: O método de comunicação a ser utilizado, o idioma a ser empregado, a necessidade de confirmar a recepção das mensagens.


Essas diretrizes, ou protocolos, são fundamentais para uma comunicação clara e eficaz. Incluem identificação do emissor e receptor, método de comunicação acordado, linguagem comum e confirmação de 
recebimento. Esses princípios básicos também são aplicados nas comunicações de rede, como no envio de mensagens de texto.

Assim como os seres humanos, os computadores usam protocolos para se comunicarem. Esses protocolos são essenciais para garantir uma comunicação adequada na rede. Em uma rede local, todos os dispositivos devem 
compartilhar um protocolo em comum para se comunicarem efetivamente, assim como as pessoas em uma sala precisam falar a mesma língua para se entenderem. Os protocolos de rede estabelecem as regras de comunicação, 
incluindo formato, tamanho, tempo, codificação, encapsulamento e padrões de mensagem.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/1be75427-8554-4271-b2ca-b63b7c5588e6)

## Padrões de comunicação

Com o aumento constante de novos dispositivos e tecnologias online, manter a confiabilidade dos serviços, como o e-mail, requer uma gestão eficiente das mudanças. Os padrões da Internet desempenham um papel fundamental nesse processo.

Um padrão é um conjunto de regras que define como algo deve ser feito. Os padrões de rede e Internet garantem que todos os dispositivos conectados à rede sigam os mesmos protocolos. Isso possibilita a interoperabilidade entre diferentes dispositivos, permitindo que eles troquem informações entre si de forma consistente.

Por exemplo, o formato, encaminhamento e recebimento de e-mails seguem um padrão. Isso significa que um e-mail enviado por um computador pode ser recebido e lido em um celular, desde que ambos sigam os mesmos padrões. Essa conformidade aos padrões facilita a comunicação entre diferentes tipos de dispositivos na Internet.

Um padrão da Internet é resultado de um ciclo de discussão, testes e solução de problemas. Diversas organizações desenvolvem, publicam e mantêm esses padrões. Cada etapa do processo é registrada em um documento Request for Comments(**RFC**), gerenciado pelo IETF. Essas **RFCs** são usadas para monitor a evolução dos padrões da Internet.

### Protocolos:

Na comunicação entre um dispositivo e um servidor web, diversos protocolos são utilizados para garantir uma conexão confiável e eficiente. Exemplos:

DHCP/ICMPv6: O protocolo DHCP (Dynamic Host Configuration Protocol) ou ICMPv6 (Internet Control Message Protocol versão 6) são responsáveis por atribuir endereços IP aos dispositivos na rede e verificar a conectividade entre eles, respectivamente.

Ethernet/WLAN: Os protocolos Ethernet e WLAN (Wireless Local Area Network) são utilizados para a transmissão dos dados em redes com fio e sem fio, respectivamente. Eles definem como os dados são encapsulados e transmitidos entre os dispositivos e o roteador da rede.

DNS: O protocolo DNS (Domain Name System) é responsável por traduzir nomes de domínio, como "www.exemplo.com", em endereços IP, permitindo que os dispositivos localizem os servidores web na Internet.

IP: O protocolo IP (Internet Protocol) é responsável pelo roteamento dos pacotes de dados entre os dispositivos na Internet, garantindo que eles cheguem ao destino correto.

TCP: O protocolo TCP (Transmission Control Protocol) é utilizado para estabelecer e manter conexões confiáveis entre o dispositivo e o servidor web. Ele divide os dados em pacotes, os reorganiza na ordem correta e verifica se foram recebidos corretamente.

**Aqui temos um exemplo de utilização dos protocolos**:

* Solicitação de Conexão do Dispositivo:

O dispositivo inicia o processo de comunicação enviando uma solicitação de conexão para a rede local.
O protocolo **DHCP** (ou **ICMPv6**, se estiver usando **IPv6**) é utilizado para atribuir um endereço IP ao dispositivo, permitindo que ele se comunique na rede.

*Encapsulamento e Transmissão dos Dados:

O dispositivo encapsula os dados a serem transmitidos em pacotes **Ethernet** (se estiver conectado por cabo) ou **WLAN** (se estiver usando uma conexão sem fio).
Os pacotes são então transmitidos pela rede local até alcançarem o roteador.

*Resolução de Nomes de Domínio:

Antes de enviar uma solicitação para um servidor web, o dispositivo precisa determinar o endereço IP do servidor com base no nome de domínio fornecido.
Ele envia uma consulta **DNS** para um servidor **DNS**, solicitando o endereço IP associado ao nome de domínio.

* Roteamento dos Pacotes na Internet:

Uma vez que o dispositivo tenha o endereço IP do servidor web, ele encapsula os dados em pacotes **IP** e os transmite pela Internet.
Os pacotes **IP** são roteados pelos dispositivos de rede intermediários (roteadores) até alcançarem o servidor web desejado.

* Estabelecimento da Conexão TCP:

Quando os pacotes **IP** chegam ao servidor web, o protocolo **TCP** é utilizado para estabelecer uma conexão confiável entre o dispositivo e o servidor.
O dispositivo e o servidor web trocam mensagens de controle (handshakes) para estabelecer a conexão **TCP**.

* Transmissão e Confirmação dos Dados:

Uma vez estabelecida a conexão **TCP**, o dispositivo envia os dados da solicitação **HTTP** para o servidor web.
O servidor web recebe os dados, confirma a recepção e processa a solicitação, enviando uma resposta de volta ao dispositivo.

* Encerramento da Conexão **TCP**:

Após a conclusão da transmissão dos dados, o dispositivo e o servidor web encerram a conexão **TCP**, liberando os recursos de rede.

### Pilha de protocolos

A pilha de protocolos é um conceito fundamental em redes de computadores e se refere à hierarquia de camadas de protocolos de comunicação que são usadas para transmitir dados em uma rede. O modelo mais comum é o modelo TCP/IP, que possui quatro camadas:

1. Camada de Aplicação: Esta camada lida com a interação entre o aplicativo e a rede. Inclui protocolos como **HTTP**, **SMTP (Simple Mail Transfer Protocol)** e **FTP (File Transfer Protocol)**.

2. Camada de Transporte: Responsável por garantir a entrega confiável dos dados. O protocolo **TCP (Transmission Control Protocol)** opera nesta camada, fornecendo controle de fluxo, sequenciamento e confiabilidade.

3. Camada de Internet/Rede: Gerencia a comunicação entre dispositivos em redes diferentes. O protocolo **IP (Internet Protocol)** é o principal protocolo nesta camada, roteando os pacotes de dados de origem para destino através da rede.

4. Camada de Link de Dados/Network Access: Responsável pela transmissão de dados entre dispositivos adjacentes na mesma rede local. Inclui protocolos como **Ethernet** e **PPP (Point-to-Point Protocol)**.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/82248b95-a892-46f5-b6e2-458d9fb559e1)

## Modelo TCP/IP

O modelo TCP/IP é baseado em camadas e facilita a compreensão do funcionamento dos protocolos de rede. Ele proporciona várias vantagens, incluindo a simplificação do projeto de protocolos, estímulo à competição entre fornecedores, flexibilidade para mudanças tecnológicas e estabelecimento de uma linguagem comum para descrever funções de rede. O modelo de Internet, criado na década de 1970, define quatro categorias de funções para uma comunicação bem-sucedida. A suite de protocolos TCP/IP, usada na Internet, segue a estrutura deste modelo, sendo comumente chamada de modelo TCP/IP.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/01c10e07-2d83-41c0-976e-7b6a9c9756d2)

## Modelo OSI

O modelo de referência OSI é outra estrutura fundamental para compreender as comunicações em rede. Ele descreve as funções necessárias para uma comunicação bem-sucedida em uma rede de forma mais abstrata, diferenciando-se dos modelos de protocolo, que são mais específicos para conjuntos de protocolos particulares, como o TCP/IP. O modelo OSI, desenvolvido pelo projeto Open Systems Interconnection (OSI) da ISO, é usado para projetar redes, especificar operações e solucionar problemas. Ele define sete camadas: física, enlace de dados, rede, transporte, sessão, apresentação e aplicação, oferecendo uma estrutura ampla para entender as comunicações em rede. Podemos dizer que o OSI é um modelo de referência, enquanto o TCP, um modelo de protocolo.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/3232ac86-f76a-4cae-b064-e82ec7037856)

## Comparação entre os modelos

O modelo OSI e o TCP/IP são estruturas fundamentais para compreender as comunicações em rede. Enquanto o TCP/IP visualiza as interações específicas dos protocolos usados na Internet, o modelo OSI descreve funções gerais necessárias para todas as comunicações em rede. Por exemplo, o TCP/IP não especifica os protocolos usados na transmissão ou a codificação de sinais, enquanto as camadas 1 e 2 do modelo OSI discutem esses procedimentos. No entanto, os protocolos do TCP/IP podem ser descritos em termos do modelo OSI, facilitando a compreensão de suas funções em relação ao modelo mais abrangente.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/69720514-1da7-41fa-b017-80c3f1154df0)


Tanto o modelo OSI quanto o TCP/IP compartilham semelhanças nas camadas de transporte e rede. No entanto, eles diferem na forma como se relacionam com as camadas adjacentes:

* A Camada 3 do modelo OSI, de rede, mapeia diretamente para a camada de Internet TCP/IP, responsável pelo endereçamento e encaminhamento de mensagens na rede.
* A Camada 4 do OSI, de transporte, mapeia diretamente para a camada de transporte TCP/IP, garantindo uma entrega ordenada e confiável de dados entre os hosts origem e destino.
* A camada de aplicação TCP/IP engloba diversos protocolos para funcionalidades específicas, enquanto as camadas 5, 6 e 7 do OSI são referências para desenvolvedores de software de aplicação.
Ambos os modelos são usados para referenciar protocolos em várias camadas, com o modelo OSI frequentemente utilizado para as camadas inferiores devido à sua separação entre enlace de dados e camada física.








