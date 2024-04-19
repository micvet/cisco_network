# Formatos e Regras de Endereçamento IPv6

## Problemas do IPv4

O IPv6 foi projetado como sucessor do IPv4 devido à iminente escassez de endereços IPv4. Ele oferece um espaço de endereço muito maior, com 128 bits, proporcionando um número incrivelmente vasto de endereços possíveis. Além disso, o IPv6 traz melhorias significativas, como o ICMPv6, que inclui recursos como resolução de endereços e configuração automática de endereços, não presentes no ICMPv4. O esgotamento de endereços IPv4 tem impulsionado a migração para o IPv6, especialmente à medida que regiões como África e Ásia se tornam mais conectadas à Internet. A figura mostra que quatro dos cinco RIRs já esgotaram seus estoques de endereços IPv4.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/b9f7b436-e77a-4bc6-a491-223213caf533)


O IPv4 tem um limite teórico de 4,3 bilhões de endereços, mas os endereços privados e o NAT têm adiado o esgotamento desse espaço. No entanto, o NAT causa problemas para muitos aplicativos e comunicações ponto a ponto.

Com o aumento dos dispositivos móveis, os provedores móveis estão liderando a transição para o IPv6. Muitos ISPs e grandes provedores de conteúdo já migraram, e várias empresas estão adotando o IPv6 internamente. A transição para o IPv6 é impulsionada também pela evolução da Internet das Coisas e Redes Socias, onde uma variedade de dispositivos estará conectada à rede.

Diante do espaço limitado de endereços IPv4, problemas com NAT e a ascensão da Internet das Coisas, a transição para o IPv6 se torna crucial.

Não há uma data definida para a migração para o IPv6, e tanto o IPv4 quanto o IPv6 continuarão a coexistir no futuro próximo, sendo a transição um processo que levará vários anos. A IETF desenvolveu diversos protocolos e ferramentas para auxiliar os administradores de rede nessa migração. As técnicas de migração podem ser divididas em três categorias:

* Pilha dupla: permite que IPv4 e IPv6 coexistam no mesmo segmento de rede. Dispositivos de pilha dupla executam os protocolos IPv4 e IPv6 simultaneamente, habilitando o acesso ao conteúdo da Internet por meio de IPv6. Isso é conhecido como IPv6 nativo, onde a rede do cliente possui uma conexão IPv6 com seu ISP. A topologia física exibe três PCs e um roteador de pilha dupla.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/ecb96b53-d504-4920-b426-316a9ca0e4e6)

* Tunelamento: é um método de transporte de pacote IPv6 através de uma rede IPv4. O pacote IPv6 é encapsulado dentro de um pacote IPv4, de forma semelhante a outros tipos de dados.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/3dcdf04a-9a70-4186-8012-c33d51b79d79)

*Conversão: O NAT64 (Network Address Translation 64) permite a comunicação entre dispositivos IPv6 e IPv4 usando uma técnica de conversão semelhante ao NAT IPv4. Ele traduz pacotes IPv6 em pacotes IPv4 e vice-versa, facilitando a comunicação entre dispositivos habilitados para diferentes versões do protocolo.

Observação: O tunelamento e a conversão são para transição para IPv6 nativo e só devem ser usados quando necessário. O objetivo deve ser as comunicações IPv6 nativas da origem até o destino.

## Endereçamento IPv6

É importante saber que os endereços IPv6 são representados usando números hexadecimais, um sistema numérico de base dezesseis que inclui os dígitos de 0 a 9 e as letras de A a F. Esses dígitos são organizados em hextetos nos endereços IPv6, o que facilita a representação de endereços extremamente longos em um formato mais legível.

O primeiro passo para entender o IPv6 em redes é compreender como um endereço IPv6 é escrito e formatado. Compostos por 128 bits, os endereços IPv6 são representados por uma sequência de valores hexadecimais. Cada 4 bits são expressos por um dígito hexadecimal, totalizando 32 valores hexadecimais. Não há diferenciação entre maiúsculas e minúsculas na escrita dos endereços IPv6.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/9a5cb713-23e2-4836-aafe-70200217e5de)

O formato preferencial para um endereço IPv6 é x: x: x: x: x: x: x: x, com cada "x" representando quatro algarismos hexadecimais. Um hexteto, equivalente a um segmento de 16 bits ou quatro dígitos hexadecimais, é usado em cada "x". Apesar de gravar todos os 32 dígitos hexadecimais, existem regras que ajudam a reduzir esse número.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/096e43fb-e8ce-4ca5-b977-912ff12023ca)

## Regras de Formatação IPv6:

1. Omitir zeros à esquerda
Na notação de endereços IPv6, podemos omitir os zeros à esquerda de qualquer seção de 16 bits ou hexteto. Por exemplo, "01AB" pode ser escrito como "1AB". No entanto, essa regra não se aplica aos zeros à direita para evitar ambiguidades. Por exemplo, "abc0" não pode ser simplificado para "abc", pois isso alteraria seu valor.
**Exemplos:**
![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/1ad001eb-491c-46a9-9c8b-8582ce9c8189)

2. Dois pontos duplos

Na notação de endereços IPv6, os dois pontos duplos (::) podem substituir uma sequência de hextetos compostos por zeros. Por exemplo, 2001:db8:cafe:1:0:0:0:1 pode ser abreviado como 2001:db8:cafe:1::1. No entanto, os dois pontos duplos (::) só podem ser usados uma vez em um endereço para evitar ambiguidades. Se um endereço tiver mais de uma sequência de zeros, os dois pontos duplos devem ser colocados na sequência mais longa. Se houver mais de uma sequência de zeros de igual comprimento, o primeiro conjunto deve ser substituído pelos dois pontos duplos (::).
![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/1598dc3b-8dfb-4e19-8257-6e0313733e3e)

**Em resumo:**

Com o aumento constante do número de dispositivos conectados à internet, desde smartphones e tablets até eletrodomésticos inteligentes e carros, o IPv4 estava se aproximando de seus limites de endereçamento.
O IPv6 resolve esse problema fornecendo um espaço de endereço muito maior, com um número virtualmente ilimitado de endereços possíveis, pois possui 128 bits de espaço de endereço, enquanto o IPv4 tinha apenas 32 bits. Isso significa que o IPv6 pode acomodar um número muito maior de dispositivos conectados à internet.
Ele simplifica o roteamento de tráfego na internet, o que pode levar a uma comunicação mais rápida e eficiente entre dispositivos e inclui recursos de segurança aprimorados, como criptografia integrada e autenticação de pacotes, tornando as comunicações mais seguras.
Os administradores de rede precisam garantir que seus sistemas e dispositivos sejam compatíveis com o IPv6 para aproveitar seus benefícios, e as empresas precisam atualizar sua infraestrutura de rede e hardware para suportar o IPv6. Os provedores de serviços de internet (ISPs) precisam garantir que ofereçam suporte completo ao IPv6 para seus clientes.
Embora o IPv6 seja crucial para o futuro da internet, sua implementação completa enfrenta desafios significativos devido à complexidade da migração e à necessidade de coordenação entre várias partes interessadas. Muitas redes e sistemas ainda dependem fortemente do IPv4, e a transição para o IPv6 requer investimentos significativos em tempo e recursos.
