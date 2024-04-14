# Conceitos de uma Rede Doméstica

## Componentes de uma Rede Doméstica

Numa rede doméstica, exitem diversos tipos de dispositivos que podem ser conectados:

- Computador desktop
- Sistemas de jogos
- Sistemas de smart TV
- Impressoras
- Scanners
- Câmeras de segurança
- Telefones
- Dispositivos de controle climático

![image](https://github.com/micvet/quality-assurance/assets/86981990/977a90c2-6868-4513-a5ce-c289395484fb)
Imagem 

### Roteadores de rede doméstica:

**Características:**

* Portas Ethernet: conectam dispositivos à rede local, permitindo a comunicação entre eles. Essas portas são encontradas no switch do roteador e são rotuladas 
como "Ethernet" ou "LAN". Todos os dispositivos conectados às portas do switch fazem parte da mesma rede local, facilitando a transferência de dados e o 
compartilhamento de recursos.

* Portas Internet: também conhecida como porta WAN (Wide Area Network), tem a finalidade de conectar o roteador a uma rede externa, que é diferente da rede local 
conectada às portas Ethernet. Normalmente, essa porta é utilizada para conectar o modem DSL ou a cabo, permitindo o acesso à Internet.

Os roteadores residenciais geralmente possuem portas com fio, antenas e pontos de acesso sem fio. Dispositivos com fio e sem fio estão na mesma rede local, 
exceto a porta de Internet, que está em uma rede diferente por padrão.

![image](https://github.com/micvet/quality-assurance/assets/86981990/b0609d3b-b6c0-4d56-ad14-f68d6e97638d)

## Tecnologias de rede residenciais

### Frequência de LAN sem fio

As redes sem fio em ambientes residenciais geralmente operam nas frequências de 2,4 GHz e 5 GHz. O Bluetooth é uma tecnologia que opera na banda de 2,4 GHz, 
permitindo comunicações de curto alcance e baixa velocidade, mas oferecendo a capacidade de conectar vários dispositivos simultaneamente. Essa capacidade tornou o 
Bluetooth popular para periféricos de computador, como mouses, teclados e impressoras sem fio, além de ser utilizado para transmissão de áudio para alto-falantes 
ou fones de ouvido.

Outras tecnologias de LAN sem fio, conformes com os padrões IEEE 802.11, também operam nas bandas de 2,4 GHz e 5 GHz. Estas tecnologias transmitem em níveis de potência mais altos, o que resulta em maior alcance e melhor desempenho em comparação com o Bluetooth. Algumas áreas do espectro eletromagnético podem ser utilizadas sem licenciamento para essas comunicações.

### Tecnologias de Redes com fio

Embora muitos dispositivos domésticos usem comunicações sem fio, ainda há algumas aplicações em que os dispositivos utilizam uma conexão com fio por meio de 
switches. O protocolo Ethernet é frequentemente utilizado para comunicações com fio em LANs, permitindo que dispositivos se comuniquem através de uma conexão LAN 
com fio.
Os dispositivos conectados diretamente utilizam cabos de ligação Ethernet, geralmente feitos de par trançado não blindado. Para residências sem cabeamento UTP, 
há alternativas, como o uso da rede elétrica para distribuir conectividade com fio.

**CAtegorias de cabos:** 

* Cabo Categoria 5e: é comumente usado em LANs, composto por 4 pares de fios trançados para reduzir interferências elétricas.

* Cabo Coaxial:é constituído por um fio interno cercado por uma camada isolante tubular e uma blindagem condutora tubular, frequentemente usado em redes locais.

* Cabo de fibra óptica:  feito de vidro ou plástico com diâmetro semelhante ao de um cabelo humano, é capaz de transportar informações digitais em velocidades 
extremamente altas ao longo de longas distâncias. Sua largura de banda muito alta permite o transporte de grandes quantidades de dados.

## Padrões de rede sem fio

### Redes Wi-Fi

Vários padrões foram desenvolvidos para garantir a comunicação entre dispositivos sem fio, especificando o espectro de RF, as taxas de dados e outros aspectos. 
O IEEE (Instituto dos Engenheiros Eletricistas e Eletrônicos) é o principal organismo responsável por criar esses padrões técnicos. O padrão IEEE 802.11 
controla o ambiente WLAN e descreve as características dos diferentes padrões de comunicação sem fio, que operam nas bandas de frequência de 2,4 GHz e 5 GHz, 
conhecidas como Wi-Fi.

A Wi-Fi Alliance, outro organismo, é responsável por testar dispositivos de LAN sem fio de diferentes fabricantes. O logotipo de Wi-Fi em um dispositivo indica 
que ele atende aos padrões e deve funcionar com outros dispositivos que usam o mesmo padrão.

Os padrões sem fio estão continuamente melhorando a conectividade e a velocidade das redes Wi-Fi. É importante acompanhar a introdução de novos padrões, pois os 
fabricantes implementarão rapidamente essas atualizações em novos produtos.

Os roteadores sem fio que usam os padrões 802.11 têm várias configurações, que incluem:

* Modo de Rede: determina o tipo de tecnologia que deve ser suportada pela rede sem fio. Isso pode incluir os padrões 802.11b, 802.11g, 802.11n ou "Mixed Mode" 
(Modo Misto), que suporta múltiplos padrões para garantir compatibilidade com uma variedade de dispositivos sem fio. Escolher o modo adequado é importante para 
garantir a melhor velocidade e compatibilidade com os dispositivos conectados à rede sem fio.
* Nome da Rede (SSID): SSID (Service Set Identifier) é utilizado para identificar a WLAN (Wireless Local Area Network). Todos os dispositivos que desejam 
participar na WLAN devem ter o mesmo SSID configurado. Isso permite que os dispositivos se reconheçam e se conectem à mesma rede sem fio. O SSID é semelhante 
a um nome de rede e é essencial para garantir a comunicação adequada entre os dispositivos sem fio em uma WLAN.
* Canal Padrão: O canal especifica a frequência na qual a comunicação sem fio ocorrerá. Por padrão, o canal é configurado como "Automático" para permitir que o 
ponto de acesso (AP) determine o melhor canal a ser utilizado. Isso permite uma configuração mais eficiente da rede sem fio, garantindo que ela opere na frequência mais adequada para evitar interferências e maximizar o desempenho da rede. 
* Broadcast de SSID: determina se o SSID será transmitido para todos os dispositivos dentro do intervalo da rede sem fio. Por padrão, essa opção está configurada 
como "Ativado", o que significa que o SSID será anunciado para que os dispositivos próximos possam identificar e se conectar à rede. Essa configuração pode ser 
desativada para tornar a rede menos visível para dispositivos que não estão procurando explicitamente por ela, aumentando assim a segurança da rede.

### Modo de rede


O "Modo de Rede" refere-se à configuração do protocolo 802.11 em um ambiente de rede sem fio. Se todos os dispositivos conectados utilizam o mesmo padrão 
802.11, a rede pode atingir velocidades máximas compatíveis com esse padrão. No entanto, se o ponto de acesso estiver configurado para aceitar apenas um 
padrão específico, dispositivos incompatíveis não poderão se conectar a ele.

Um ambiente de "modo misto" permite que dispositivos que utilizam diferentes padrões Wi-Fi se conectem à rede. Isso é útil para dispositivos mais antigos 
que não suportam os padrões mais recentes.

O SSID (Service Set Identifier) é uma string alfanumérica de até 32 caracteres que identifica uma rede sem fio. Ele é transmitido nos cabeçalhos dos quadros 
enviados pela WLAN, permitindo que dispositivos sem fio saibam a qual rede pertencem e com quais outros dispositivos podem se comunicar.

O "broadcast de SSID" determina se o SSID será transmitido para todos os dispositivos dentro do alcance da rede. Desativá-lo pode dificultar a detecção da rede, 
mas não é suficiente para evitar acessos não autorizados. É essencial utilizar criptografia forte para restringir o acesso não autorizado à rede sem fio.

## Configuração inicial

A configuração inicial de um roteador sem fio geralmente envolve conectar um computador à porta com fio do roteador e ajustar as configurações básicas usando um utilitário de configuração automática. Se não houver um dispositivo com conexão com fio disponível, pode ser necessário configurar primeiro o software de cliente sem fio em um notebook ou tablet.

Para conectar o computador ao roteador com fio, um cabo Ethernet é usado, conectando uma extremidade à porta de rede do computador e a outra a uma porta LAN no roteador, evitando a porta "Internet". Em seguida, é importante confirmar a conexão ativa observando as luzes de link na placa de interface de rede (NIC). Se o computador não receber automaticamente um endereço IP do servidor DHCP do roteador, é necessário configurá-lo manualmente com um endereço IP, máscara de sub-rede, gateway padrão e informações de DNS conforme especificado na documentação do roteador.

### Considerações

* Nome da rede: Ativar a transmissão do SSID faz com que o nome da rede seja visível para todos os clientes sem fio dentro do alcance do sinal. No entanto, revelar informações detalhadas demais, como o modelo ou a marca do dispositivo, pode expor a rede a possíveis vulnerabilidades de segurança. Isso ocorre porque os dispositivos sem fio possuem configurações padrão que são amplamente conhecidas e podem ser exploradas por invasores em potencial. Portanto, é recomendável evitar incluir informações excessivas no SSID para proteger a segurança da rede.

* Conexões

Os dispositivos sem fio operam em faixas de frequência específicas, mas a compatibilidade entre dispositivos e roteadores depende dos padrões de rede suportados. Dispositivos mais antigos, por exemplo, podem não se conectar a roteadores configurados apenas para padrões mais recentes, como 802.11n ou 802.11ac. Para garantir a compatibilidade, é necessário configurar o roteador no modo legado, que pode incluir suporte para padrões como 802.11a, 802.11b, 802.11g, 802.11n e 802.11ac. Isso permite que dispositivos mais antigos se conectem à rede sem fio, garantindo uma cobertura ampla de dispositivos compatíveis.

As redes sem fio padrões 802.11 são um conjunto de especificações desenvolvidas pelo IEEE (Institute of Electrical and Electronics Engineers) para comunicação sem fio. Aqui está uma visão geral de cada padrão:

**-802.11a:**
Lançamento: 1999
Velocidade máxima teórica: Até 54 Mbps
Faixa de frequência: 5 GHz
Principais características: O padrão 802.11a foi um dos primeiros padrões Wi-Fi e operava na faixa de frequência de 5 GHz. Ele oferecia maior largura de banda e menos interferência em comparação com o padrão 802.11b, mas tinha um alcance mais curto devido às propriedades de propagação de rádio na faixa de 5 GHz.

**-802.11b:**
Lançamento: 1999
Velocidade máxima teórica: Até 11 Mbps
Faixa de frequência: 2,4 GHz
Principais características: O padrão 802.11b foi amplamente adotado devido à sua compatibilidade com equipamentos mais antigos e seu custo mais baixo em comparação com o 802.11a. Operava na faixa de frequência de 2,4 GHz e oferecia uma velocidade máxima teórica de até 11 Mbps.

**-802.11g:**
Lançamento: 2003
Velocidade máxima teórica: Até 54 Mbps
Faixa de frequência: 2,4 GHz
Principais características: O padrão 802.11g foi uma evolução do 802.11b, oferecendo uma velocidade máxima teórica mais rápida de até 54 Mbps enquanto mantinha compatibilidade com dispositivos 802.11b. Operava na mesma faixa de frequência de 2,4 GHz que o 802.11b.

**-802.11n:**
Lançamento: 2009
Velocidade máxima teórica: Até 600 Mbps
Faixa de frequência: 2,4 GHz e 5 GHz
Principais características: O padrão 802.11n introduziu MIMO (Multiple Input Multiple Output) e canais de 40 MHz para aumentar a largura de banda e melhorar o desempenho em comparação com os padrões anteriores. Ele operava nas faixas de frequência de 2,4 GHz e 5 GHz e oferecia velocidades de até 600 Mbps.

**-802.11ac:**
Lançamento: 2013
Velocidade máxima teórica: Até 1,3 Gbps (Wave 1), Até 7 Gbps (Wave 2)
Faixa de frequência: 5 GHz
Principais características: O padrão 802.11ac, também conhecido como Wi-Fi 5, introduziu uma série de melhorias em relação ao 802.11n, incluindo suporte a canais de 80 MHz e 160 MHz, bem como modulação mais avançada. Ele opera exclusivamente na faixa de frequência de 5 GHz e oferece velocidades de até 1,3 Gbps (Wave 1) e até 7 Gbps (Wave 2).


O modo de uso da rede determina quem pode acessá-la, com opções como acesso para convidados em alguns roteadores sem fio. Essa área de cobertura do SSID permite acesso aberto restrito apenas à Internet. Em alguns roteadores, o modo legado pode ser rotulado como modo misto.

















