# Simulação de Rede Corporativa no GNS3

## 📌 Visão Geral
Este projeto demonstra a configuração de uma rede corporativa no **GNS3**, utilizando **roteadores Cisco**, **switches gerenciáveis** e **PCs simulados**. Implementamos **VLANs, roteamento OSPF, ACLs e NAT**, refletindo um ambiente realista de TI.

## 🛠️ Tecnologias Utilizadas
- 🏢 **GNS3** - Simulação de redes
- 🌍 **OSPF** - Roteamento dinâmico
- 🔀 **VLANs** - Segmentação de rede
- 🔒 **ACLs** - Controle de acesso
- 🌐 **NAT** - Tradução de endereços

## 🔧 Topologia da Rede
!(Topol.png)

## 🚀 Configuração Passo a Passo

### 1️⃣ Configuração das VLANs
```bash
vlan 10
name REDE_INTERNA
vlan 20
name REDE_FINANCEIRO
exit
```

### 2️⃣ Configuração do Roteamento OSPF
```bash
router ospf 1
network 192.168.1.0 0.0.0.255 area 0
network 192.168.2.0 0.0.0.255 area 0
exit
```

### 3️⃣ Configuração de ACLs para Segurança
```bash
access-list 100 permit tcp any any eq 80
access-list 100 deny ip 192.168.1.0 0.0.0.255 192.168.2.0 0.0.0.255
```

### 4️⃣ Configuração de NAT
```bash
ip nat inside source list 1 interface FastEthernet0/0 overload
access-list 1 permit 192.168.1.0 0.0.0.255
```

## 📜 Conclusão
Esta simulação permite testar conceitos avançados de redes e pode ser expandida com firewalls, VPNs e monitoramento. Teste as configurações e ajuste conforme sua necessidade!

🔗 **Conecte-se comigo:** [LinkedIn](https://www.linkedin.com/in/kaua7k/) 🚀
