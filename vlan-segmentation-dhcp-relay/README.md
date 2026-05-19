# CCNA Enterprise Network Segmentation

## Visão Geral

Este projeto simula uma pequena rede empresarial focada em:

- Segmentação de departamentos com VLANs
- DHCP centralizado
- DHCP Relay (ip helper-address)
- Inter-VLAN Routing

O laboratório reproduz um cenário comum em ambientes empresariais, onde diferentes departamentos precisam de comunicação entre redes e atribuição automática de endereços IP a partir de um servidor DHCP centralizado.

---

# Problema Real

Em muitas empresas, o servidor DHCP fica centralizado numa rede de gestão.

Como o DHCP utiliza broadcasts, dispositivos localizados em VLANs diferentes não conseguem obter endereços IP automaticamente sem o uso de DHCP Relay.

Este projeto demonstra como resolver esse problema utilizando o comando:

```cisco
ip helper-address
```

---

# Tecnologias Utilizadas

- VLANs
- 802.1Q Trunking
- Router-on-a-Stick
- DHCP Relay
- DHCP Centralizado
- Inter-VLAN Routing

---

# Estrutura da Rede

| VLAN | Departamento | Rede |
|------|--------------|------|
| 10 | RH | 192.168.10.0/24 |
| 20 | TI | 192.168.20.0/24 |
| 30 | GUEST | 192.168.30.0/24 |
| 40 | FINANCE | 192.168.40.0/24 |
| 99 | MANAGEMENT | 192.168.99.0/24 |

---

# Topologia

![Topology](topology.png)

---

# Comunicação entre Redes

A rede foi segmentada utilizando VLANs para separar os departamentos mantendo os serviços centralizados.

O Inter-VLAN Routing foi implementado utilizando Router-on-a-Stick, permitindo comunicação entre as redes.

Este modelo simula uma arquitetura comum em ambientes corporativos, onde departamentos permanecem logicamente separados, mas conectados através de roteamento centralizado.

---

# DHCP Relay

Foi configurado um servidor DHCP centralizado na VLAN 99.

Para permitir que dispositivos de outras VLANs obtenham endereços IP automaticamente, foi implementado DHCP Relay através do comando:

```cisco
ip helper-address
```

Mais detalhes disponíveis em:

- `docs/dhcp-relay.md`

---

# Estrutura do Repositório

```bash
ccna-enterprise-network-segmentation
│
├── README.md
├── topology.png
│
├── configs/
│   ├── R1.txt
│   ├── S1.txt
│
├── docs/
│   ├── dhcp-relay.md
│   └── tests.md
```

---

# Validação

- Comunicação entre VLANs validada
- DHCP Relay validado
- DHCP centralizado funcional
- Inter-VLAN Routing operacional

Mais detalhes disponíveis em:

- `docs/tests.md`

---

# Melhorias Futuras

- ACLs avançadas
- OSPF
- NAT
- STP
- Redundância
- Automação com Python

---

# Autor

Adão Francisco

---

# Notas

Este laboratório foi desenvolvido no Cisco Packet Tracer como parte dos estudos práticos de CCNA e redes empresariais.
