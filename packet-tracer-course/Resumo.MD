# **Curso Começando com o Cisco Packet Tracer**

## O que é Packet Tracer

Packet Tracer é uma ferramenta que permite simular redes reais. Ele fornece três menus principais que você pode usar para o seguinte:

* Adicionar dispositivos e conecta-los via cabo ou wireless
* Selecionar, remover, inspecionar, etiquetar e agrupar componentes na sua rede
* Gerenciar sua rede

O menu de gerenciamento de rede permite:

![image](https://github.com/micvet/cisco_network/assets/86981990/55416453-e3db-4235-b30e-45b8948f491e)


* Abrir uma rede atual / de exemplo
* Salve sua rede atual
* Modifique seu perfil de usuário ou suas preferências

## Configuração de GUI e CLI no Cisco Packet Tracer
O Packet Tracer também oferece uma variedade de guias para configuração de dispositivos, incluindo o seguinte:

* Físico
* Configuração
* CLI
* Desktop
* Serviços


As guias exibidas dependem do dispositivo que você está configurando no momento.

Guia Física

A guia Física fornece uma interface para interagir com o dispositivo, incluindo ligá-lo, desligá-lo ou instalar módulos diferentes, como uma placa de interface de rede sem fio (NIC).

* Guia Config

Para dispositivos intermediários, como roteadores e switches, há duas maneiras de acessar as configurações do dispositivo. As configurações podem ser acessadas ´pela guia Configuração, que é uma Interface gráfica do usuário (GUI). As configurações também podem ser acessadas usando uma interface de linha de comando (CLI).

A guia Config não simula a funcionalidade de um dispositivo. Essa guia é exclusiva do Packet Tracer. Se você não sabe como usar a interface de linha de comando, essa guia oferece uma maneira de usar somente uma GUI do Packet Tracer para definir as configurações básicas. Conforme as configurações são alteradas na GUI, os comandos CLI equivalentes aparecem na janela Comandos IOS equivalentes Isso ajuda você a aprender os comandos de CLI e o Cisco Internetwork Operating System (IOS) enquanto estiver usando a guia Config.


Além disso, os arquivos de configuração do dispositivo podem ser salvos, carregados, apagados e exportados.

* Guia CLI

A guia CLI fornece acesso à interface de linha de comando de um dispositivo Cisco. O uso da guia CLI requer conhecimento da configuração do dispositivo com o IOS. Aqui, você pode praticar a configuração de dispositivos da Cisco na linha de comando. A configuração de CLI é uma habilidade necessária para implementações de rede mais avançadas.

* Guia Desktop

Para alguns dispositivos finais, como PCs e laptops, o Packet Tracer fornece uma interface de desktop que oferece acesso à configuração de IP, configuração sem fio, prompt de comando, navegador da Web e outras aplicações.

* Guia Serviço

Um servidor tem todas as funções de um host com a adição de mais uma guia, a guia Serviços. Essa guia permite que um servidor seja configurado com processos comuns de servidor, como HTTP, DHCP, DNS ou outros serviços.

## Arquivos Packet Tracer

O Packet Tracer tem a capacidade de criar quatro tipos diferentes de arquivos, que podem ser usados para diferentes fins: .pka, .pkt, .pksz e .pkz.

* O arquivo .pka é um arquivo de atividade do Packet Tracer e é utilizado com maior frequência. Pense no “a” no .pka como o significado de “atividade”. Uma Atividade do Packet Tracer tem uma janela de instruções. Normalmente, a atividade também é pontuada. Esse tipo de arquivo contém duas redes: uma rede inicial e uma rede com as respostas. A rede inicial é aberta quando você inicia a atividade. A rede com as respostas funciona em segundo plano e pode ser usada para fornecer pontuação e feedback aos alunos à medida que eles concluem a atividade. Os alunos não têm acesso à rede com as respostas em um arquivo .pka.

A janela de instruções de Atividade do Packet Tracer fornece os procedimentos necessários para concluir a atividade, a atribuição ou a avaliação. A janela de instruções também pode exibir a porcentagem de conclusão para rastrear quanto da atividade foi concluída com êxito. O recurso Verificar Resultados pode ser ativado para fornecer feedback.

* O tipo de arquivo .pkt é criado quando uma rede simulada é criada no Packet Tracer e salva. O arquivo .pkt também pode ter imagens gráficas de fundo incorporadas. No entanto, os arquivos .pkt não têm janela de instruções ou pontuação de atividade.

* O tipo de arquivo .pksz é específico para atividades supervisionadas pelo Packet Tracer (PTTA). Esses arquivos incluem um arquivo .pka, recursos de mídia e um arquivo de script para o sistema de dicas. Essas atividades oferecem suporte, na forma de dicas contextualizadas, para os alunos que estão trabalhando para concluir a atividade.

* O arquivo.pkz foi usado anteriormente para incorporar imagens e outros arquivos em um arquivo do Packet Tracer. No entanto, as imagens agora são incorporadas diretamente em um arquivo regular.pkt ou.pka, por tanto o uso do arquivo .pkz é obsoleto.

## Tipos de itens de avaliação

Existem dois tipos de itens de avaliação no Packet Tracer: Packet Tracer Media Objetos (PTMO) e as avaliações de habilidades do Packet Tracer (PTSA). PTMOs podem ser um arquivo .pkt ou .pka. Um PTMO aparecerá em linha com uma pergunta no seu questionário, no exame do módulo ou em algum outro tipo de avaliação. Você inicia o arquivo .pkt ou .pka diretamente de dentro da avaliação. Normalmente, você configura a rede ou investiga a topologia e responde a uma ou mais perguntas de avaliação de múltipla escolha.

Já os PTSAs, são avaliações de habilidades somativas em que você demonstra sua habilidade ao implementar as tecnologias que aprendeu. Os PTSAs são avaliações independentes, têm seu próprio mecanismo de classificação e os resultados são registrados em um livro de notas do curso, se houver. Depois de concluir um PTSA, você recebe feedback no nível do item para cada componente classificado.



