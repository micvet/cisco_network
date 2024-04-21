# Utilitários de teste de rede

## Comandos para solução de problemas


Existem diversas ferramentas de software que podem auxiliar na identificação e resolução de problemas de rede. Muitas dessas ferramentas são integradas aos sistemas operacionais e são acessadas por meio de comandos na linha de comando (CLI). A sintaxe desses comandos pode variar dependendo do sistema operacional utilizado.

Algumas delas são:

* ipconfig - Exibe informações da configuração IP.
* ping - Testa conexões com outros hosts IP.
* netstat - Exibe as conexões de rede.
* tracert - Exibe a rota percorrida até o destino.
* nslookup - consulta diretamente o servidor de nomes para obter informações sobre um domínio de destino.


Quando um dispositivo não possui um endereço IP ou tem uma configuração de IP incorreta, ele não consegue se comunicar na rede local nem acessar a Internet. No Windows, você pode visualizar informações de configuração de IP usando o comando ipconfig no prompt de comando. O comando ipconfig oferece várias opções úteis, incluindo /all, /release e /renew.

* ipconfig: O comando ipconfig é usado para exibir as informações de configuração de IP atuais de um host. A emissão deste comando a partir do prompt de comando exibirá as informações básicas de configuração, incluindo endereço IP, máscara de sub-rede e gateway padrão.

* ipconfig/all: O comando ipconfig /all exibe informações adicionais que incluem o endereço MAC, os endereços IP do gateway padrão e os servidores DNS. Ele também indica se o DHCP está ativado, o endereço do servidor DHCP e as informações da concessão.
Como esse utilitário ajuda no processo de solução de problemas? Sem uma configuração de IP apropriada, o host não pode participar da comunicação em uma rede. Se o host não souber o local dos servidores DNS, ele não poderá converter nomes em endereços IP.

* ipconfig /release e ipconfig /renew: Se as informações de endereçamento IP forem atribuídas dinamicamente, o comando ipconfig /release liberará as ligações DHCP atuais. ipconfig /renew solicitará novas informações de configuração ao servidor DHCP. Um host pode conter informações de configuração de IP desatualizadas ou com falhas. Com uma simples renovação dessas informações, a conectividade pode ser recuperada.
Se, após a liberação da configuração IP o host não puder obter informações atualizadas do servidor DHCP, talvez não haja conectividade de rede. Verifique se a NIC tem uma luz de link acesa, que indica uma conexão física com a rede. Se isso não resolver, talvez exista um problema no servidor DHCP ou nas conexões de rede com o servidor DHCP.


## O comando ping

O utilitário de rede mais comumente utilizado é o ping. A maioria dos dispositivos habilitados para IP suporta alguma forma do comando ping para testar a acessibilidade de dispositivos de rede através da rede IP.

Se a configuração IP estiver correta no host local, a conectividade de rede pode ser testada usando o comando ping. O comando ping pode ser seguido por um endereço IP ou pelo nome de um host de destino. Por exemplo, um usuário pode pingar o gateway padrão em 10.10.10.1 e, em seguida, pingar www.cisco.com.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/8ccbd558-6ef0-46db-96ef-5610a7bc9c0c)

Quando um ping é enviado para um endereço IP, um pacote chamado "echo request" é enviado pela rede para o endereço IP especificado. Se o host de destino receber o "echo request", ele responderá com um pacote conhecido como "echo reply". A conectividade é verificada pela resposta do endereço IP específico. Se a origem receber o "echo reply", a conectividade é confirmada. O ping não é bem-sucedido se uma mensagem como "request timed out" ou "general failure" for exibida.

Se um ping for enviado para um nome, como www.cisco.com, primeiro um pacote é enviado para um servidor DNS para resolver o nome para um endereço IP. Depois que o endereço IP é obtido, o "echo request" é encaminhado para o endereço IP e o processo continua. Se um ping for bem-sucedido para o endereço IP, mas não para o nome, pode haver um problema com o DNS.

Se os comandos ping para o nome e o endereço IP forem bem-sucedidos, mas o usuário ainda não conseguir acessar a aplicação, o problema provavelmente estará na aplicação no host de destino. Se nenhum ping tiver êxito, a conectividade de rede no caminho até o destino será o problema mais provável. Em alguns casos, o ping pode falhar, mas a conectividade de rede não é o problema. O comando ping geralmente envia quatro ecos e espera as respostas de cada um.

![image](https://github.com/micvet/bootcamp-qa-automacao-cypress/assets/86981990/ef57a760-e7ef-4a49-9a28-15c8029740c0)

