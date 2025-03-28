# Capítulo 3: Internet Gateway e NAT Gateway

## Objetivo

Compreender como uma subnet se torna pública ou privada dentro de uma VPC, e qual o papel dos gateways (Internet Gateway e NAT Gateway) nesse processo. Este capítulo é totalmente teórico e serve como base conceitual para a prática que será abordada nos capítulos seguintes.

---

## Conceitos Fundamentais

### O que define uma subnet como pública ou privada?

Em uma VPC da AWS, uma subnet é considerada **pública** quando:
1. Está associada a uma route table que tem uma rota para um **Internet Gateway**;
2. E as instâncias dentro dessa subnet possuem **endereços IP públicos**.

Caso qualquer um desses dois elementos esteja ausente, a subnet é considerada **privada**.

---

### Internet Gateway (IGW)

Um **Internet Gateway** é um componente da VPC que permite comunicação entre instâncias na VPC e a internet. Ele é essencial para que instâncias com IP público possam:
- Serem acessadas via SSH
- Fazer updates
- Enviar e receber tráfego pela internet

Para funcionar corretamente:
- O IGW deve estar **associado à VPC**.
- A **route table da subnet** deve ter uma rota para o IGW com destino `0.0.0.0/0`.

---

### NAT Gateway (NGW)

Um **NAT Gateway** permite que instâncias em subnets privadas **acessem a internet** para realizar atualizações ou chamadas de API, **sem estarem acessíveis de fora** (sem receber conexões externas).

Requisitos:
- O NAT Gateway deve estar em uma **subnet pública**.
- A **route table da subnet privada** deve ter uma rota para o NAT Gateway.

---

### Diferença entre IGW e NAT Gateway

| Característica       | Internet Gateway (IGW)       | NAT Gateway (NGW)            |
|----------------------|-------------------------------|-------------------------------|
| Tráfego de entrada   | Permitido da internet         | **Não permitido**             |
| Tráfego de saída     | Permitido para internet       | Permitido para internet       |
| Posicionamento       | Qualquer subnet               | Deve estar em subnet pública  |
| Uso comum            | Web servers                   | Servidores internos, bancos   |

---

## Resumo

- Subnets **públicas** têm rota para um **Internet Gateway** e IPs públicos.
- Subnets **privadas** não têm rota para IGW.
- **NAT Gateway** permite que instâncias em subnets privadas acessem a internet com segurança.
- Sem um IGW ou NGW configurado corretamente, não existe comunicação com a internet.

---

## Próximos Passos

No Capítulo 4, vamos entender os elementos essenciais para acessar uma instância: EC2, chave de acesso, security groups e como isso se relaciona com a topologia da VPC.

---

📘 Parte da série [Cloudificando](https://www.linkedin.com/in/joccastroneves/) – aprenda AWS do zero com conteúdo direto ao ponto.

