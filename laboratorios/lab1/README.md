# Laboratório de Redes com Packet Tracer

## Descrição
Este laboratório foi criado para demonstrar a configuração de uma rede, usando o Cisco Packet Tracer. O lab inclui a criaçao de VLANs, configuração do roteamento inter-VLAN, trunking, SSH para acesso seguro e configuração de servidor DHCPv4.

## Objetivos
- Configurar VLANs e trunking em switches.
- Configurar roteamento inter-VLAN em switches de camada 3.
- Configurar roteamento inter-VLAN com Router-on-a-Stick.
- Configurar acesso SSH seguro para os dispositivos.
- Configurar DHCP em roteador para fornecer endereços IP dinâmicos.
- Demonstrar o uso de EtherChannel para aumentar a largura de banda e redundância entre switches.
- Demonstrar o SPT em ação, evitando o loop de pacotes na camada de acesso.

## Topologia

<div align='left'>
   <img src='https://github.com/user-attachments/assets/e2dcdeb5-4d1e-4c87-afea-929406a1ae89' height='550'/>
<div/><br> 

## Equipamentos e Configurações

São duas redes se comunicando por meio de dois roteadores: **RT-Campus01** e **RT-Campus02**.

### Roteadores
Dois roteadores foram configurados para fornecer roteamento entre as redes VLANs e acesso à internet fictício:

- **RT-Campus01**: Configura DHCP para várias VLANs, roteamento entre as VLANs e conexão com o roteador RT-Campus02.
- **RT-Campus02**: Configura gateways padrão para as VLANs 30 e 40, além de roteamento entre as VLANs e conexão com o RT-Campus01.

### Switches sob **RT-Campus01**
Foram configurados quatro switches: SW-101, SW-102, SW-103 e SWM-101. Cada switch tem configurações específicas para VLANs, EtherChannel, e trunks. As configurações de cada switch podem ser encontradas na pasta `config/`.

- **SW-101**: Configuração das VLANs, trunks, e EtherChannel.
- **SW-102**: Configuração de VLANs, trunks, e EtherChannel com conexão ao SWM-101.
- **SW-103**: Configuração de VLANs, trunks, e EtherChannel com conexão ao SWM-101.
- **SWM-101**: Switch principal com roteamento inter-VLAN e interface de roteamento para conexão com o roteador RT-Campus01.

### Switch sob **RT-Campus02**

- **SW-201**: Configuração das VLANs e interface para conexão com o roteador RT-Campus02.

As configurações completas dos equipamentos estão disponíveis na pasta `config/`.

## Configurações de Dispositivos

As configurações para cada dispositivo estão organizadas na pasta `config/`:

- [SW-101 Config](config/SW-101.txt)
- [SW-102 Config](config/SW-102.txt)
- [SW-103 Config](config/SW-103.txt)
- [SWM-101 Config](config/SWM-101.txt)
- [RT-Campus01 Config](config/RT-Campus01.txt)
- [RT-Campus02 Config](config/RT-Campus02.txt)
- [SW-201 Config](config/SW-201.txt)

## Notas

- O laboratório foi testado e foi possível a conexão via SSH de um PC sob a rede do RT-Campus02 com um SW da rede do RT-Campus01, indicando que as configurações de roteamento e de VLANs estão corretas, permitindo a comunicação segura entre as redes através do protocolo SSH.
- O ping entre todos os dispositivos se mostrou totalmente funcional, indicando que a conectividade de rede está estabelecida corretamente e que não há problemas de roteamento ou bloqueios de comunicação entre os dispositivos.
- Todos os dispositivos finais receberam IP dinamicamente de acordo com sua VLAN, indicando o correto funcionamento do servidor DHCPv4.

### Ping com sucesso:
<div align='left'>
   <img src='https://github.com/user-attachments/assets/713b1c15-39d4-46d2-abbe-9376dda1438d' height='550'/>
<div/><br> 

### Acesso remoto via SSH ao Switch da rede vizinha:

<div align='left'>
   <img src='https://github.com/user-attachments/assets/43bd139e-9b63-4d48-bef5-3947a59329d1' height='550'/>
<div/><br> 

### IPv4 atribuido dinaimcamente de forma correta aos endpoints:

<div align='left'>
   <img src='https://github.com/user-attachments/assets/934c63c4-3006-4ca7-b26a-891cdb212417' height='250'/>
<div/><br> 

Sinta-se à vontade para contribuir com sugestões de melhorias.
