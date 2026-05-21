# CCNA STP Loop Prevention

## Visão Geral

Este projeto simula um cenário empresarial onde múltiplos switches foram adicionados à rede para aumentar redundância e disponibilidade.

Com a introdução de links redundantes, surgiram loops Layer 2 causando instabilidade na rede.

O laboratório demonstra como o Spanning Tree Protocol (STP) previne loops automaticamente e mantém a estabilidade da infraestrutura.

Além da implementação técnica, o projeto também segue boas práticas de configuração inicial em dispositivos de rede, aproximando o ambiente de um cenário corporativo real.

---

# Problema Real

Uma empresa expandiu sua infraestrutura adicionando:
- novos switches
- links redundantes
- novos caminhos de comunicação

Após a expansão:
- utilizadores perderam conectividade
- a rede ficou lenta
- broadcasts começaram a circular infinitamente
- switches apresentavam instabilidade

A causa identificada foi um loop Layer 2.

---

# Objetivos do Laboratório

- Compreender funcionamento do STP
- Verificar eleição do Root Bridge
- Identificar portas bloqueadas
- Simular loops Layer 2
- Entender impactos da desativação do STP
- Simular crescimento de uma rede enterprise
- Aplicar boas práticas de configuração inicial

---

# Tecnologias Utilizadas

- VLANs
- Trunking
- STP (PVST)
- Redundância Layer 2
- Switching Cisco

---

# Topologia Inicial

<img width="473" height="334" alt="topologia" src="https://github.com/user-attachments/assets/f5c69ee5-77f3-4b0d-9725-2adad9480ec5" />




# Funcionamento do STP

No Cisco Packet Tracer o STP já vem ativo por padrão:

```cisco
spanning-tree mode pvst
```

O protocolo:
- previne loops Layer 2
- bloqueia caminhos redundantes
- mantém redundância disponível
- estabiliza a rede automaticamente

---

# Root Bridge

O STP elege automaticamente um switch Root Bridge.

Neste laboratório foi realizada manipulação manual da prioridade para definir o S1 como Root Bridge.

Exemplo:

```cisco
spanning-tree vlan 1 priority 4096
```

---

# Simulação de Falha

O STP foi desativado temporariamente para demonstrar os impactos de loops Layer 2.

Sintomas observados:
- perda de conectividade
- broadcast storms
- tráfego duplicado
- instabilidade da rede

Após a reativação do STP:
- a rede voltou a estabilizar
- os loops foram prevenidos
- a redundância permaneceu operacional

---

# Boas Práticas Aplicadas

Todos os dispositivos receberam configuração inicial padrão incluindo:

- hostname
- descriptions
- shutdown em interfaces não utilizadas
- passwords
- banner MOTD
- line console e VTY
- service password-encryption
- no ip domain-lookup

# Observação Importante

Durante os testes foi possível observar que o PVST (Per VLAN Spanning Tree) cria uma instância STP independente para cada VLAN.

Isso significa que:
- diferentes VLANs podem possuir caminhos distintos
- uma interface pode estar em forwarding para uma VLAN e blocking para outra

No Cisco Packet Tracer, a representação visual pode mostrar a porta totalmente em verdes mesmo quando apenas uma VLAN está em estado blocking.

# Autor

Adão Francisco


# Notas

Este laboratório foi desenvolvido no Cisco Packet Tracer como parte dos estudos práticos de switching e redes enterprise.
