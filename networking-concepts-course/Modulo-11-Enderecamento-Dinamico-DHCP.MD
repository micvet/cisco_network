# Endereçamento Dinâmico DHCP

## Endereçamento Estático e Dinâmico

### Atribuição de endereço IPv4 estático

Os endereços IPv4 podem ser atribuídos de forma estática ou dinâmica. Com atribuição estática, o administrador configura manualmente as informações da rede para um host, incluindo endereço IP, máscara de sub-rede e gateway padrão. Isso é útil para dispositivos como servidores e impressoras que precisam de acessibilidade consistente. No entanto, a configuração estática pode ser demorada e propensa a erros. Além disso, os endereços estáticos não são reutilizados com frequência.


![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/a1dd99e2-911c-4fd1-93f5-c71348950bd2)

O Dynamic Host Configuration Protocol (DHCP) é um protocolo que automatiza a atribuição de endereços IPv4 em redes locais. Em vez de configurar manualmente cada estação de trabalho, o DHCP atribui automaticamente endereços IPv4, máscaras de sub-rede, gateways padrão e outras configurações de rede. Isso reduz a carga sobre a equipe de suporte e minimiza erros. Além disso, os endereços são "alugados" por um período, retornando ao pool quando não estão mais em uso, o que é útil para usuários móveis e ambientes com muitos dispositivos.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/f71d3a77-eb03-49ea-9ae8-cd3cccf1897d)

O Dynamic Host Configuration Protocol (DHCP) facilita o acesso à Internet em locais como aeroportos ou lanchonetes com hotspots sem fio. Quando você entra na área, seu laptop entra em contato com o servidor DHCP local, que atribui um endereço IPv4 ao seu dispositivo. Os servidores DHCP podem ser diversos tipos de dispositivos, desde que executem o software DHCP. Em redes residenciais, é comum que o servidor DHCP esteja localizado no provedor de serviços de Internet (ISP), atribuindo configurações IPv4 diretamente aos hosts da rede residencial.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/f2890026-2456-4bfc-ab82-0e15a8bbcd8a)

Nas redes residenciais e pequenas empresas que usam um modem e um roteador sem fio, o roteador desempenha um papel duplo como servidor e cliente DHCP. Ele funciona como cliente para receber a configuração de IPv4 do ISP e como servidor DHCP para os dispositivos na rede local. O roteador obtém um endereço IPv4 público do ISP e, em seguida, distribui endereços privados para os dispositivos internos na rede. Embora os roteadores sem fio sejam comuns nesse papel, outros dispositivos de rede, como roteadores dedicados, também podem fornecer serviços DHCP, embora isso seja menos comum.

## Configuração DHCPv4

* Descoberta DHCP (DHCP Discovery):
Quando um dispositivo se conecta a uma rede, ele envia uma mensagem de descoberta DHCP (DHCP Discover) para localizar servidores DHCP disponíveis na rede.
Esta mensagem é enviada para o endereço de broadcast IP (255.255.255.255) ou para o endereço IP do servidor DHCP, se conhecido.
* Oferta DHCP (DHCP Offer):
Os servidores DHCP na rede respondem com mensagens de oferta DHCP (DHCP Offer), oferecendo configurações de rede ao dispositivo.
Cada servidor DHCP pode oferecer diferentes configurações, e o dispositivo escolhe entre as ofertas recebidas.
* Solicitação DHCP (DHCP Request):
O dispositivo seleciona uma oferta DHCP e envia uma mensagem de solicitação DHCP (DHCP Request) para aceitar a oferta.
Esta mensagem é novamente enviada para o endereço de broadcast IP ou diretamente ao servidor DHCP que fez a oferta.
* Aceitação DHCP (DHCP Acknowledgment):
O servidor DHCP selecionado recebe a solicitação e responde com uma mensagem de aceitação DHCP (DHCP Acknowledgment) confirmando as configurações oferecidas.
Esta mensagem contém o endereço IP atribuído ao dispositivo, juntamente com outras configurações de rede.
* Renovação de Locação DHCP (DHCP Lease Renewal):
Após um período de tempo definido chamado de "tempo de concessão" (lease time), o dispositivo precisa renovar sua locação DHCP.
O dispositivo envia uma solicitação de renovação DHCP (DHCP Renew) para o servidor DHCP original para estender o tempo de concessão.
* Liberar Locação DHCP (DHCP Lease Release):
Quando um dispositivo desconecta da rede ou não precisa mais de uma locação DHCP, ele pode enviar uma mensagem de liberação DHCP (DHCP Release) para informar ao servidor DHCP que está liberando o endereço IP.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/2cd9ffed-6703-4c4e-b89d-3bf952780b9f)


