
# Cloudificando – Fundamentos Cloud | Capítulo 2

## 🧱 VPC, Subnets e CIDRs

Este repositório acompanha o **Capítulo 2** da série **Cloudificando – Fundamentos Cloud** (*Build Smart, Scale Fast*), com foco em entender como criar uma base de rede sólida e escalável na AWS usando **Terraform**.

---

### 🎯 Objetivo
Criar uma **VPC** com subnets públicas e privadas distribuídas entre duas **Availability Zones**, utilizando **CIDR blocks bem planejados**, com um código 100% versionável e reutilizável.

---

## 📐 Arquitetura Proposta

```
VPC: 10.0.0.0/16
├── us-east-1a
│   ├── Subnet Pública: 10.0.1.0/24
│   └── Subnet Privada: 10.0.3.0/24
├── us-east-1b
    ├── Subnet Pública: 10.0.2.0/24
    └── Subnet Privada: 10.0.4.0/24
```

---

## 🚀 Como usar

### 🧰 Pré-requisitos
- Conta AWS válida (acesse: https://aws.amazon.com/)
- Instale e configure o [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
  ```bash
  aws configure
  ```
  Insira as chaves de acesso da sua conta AWS (Access Key ID e Secret Access Key) e escolha a região (`us-east-1` sugerida).

- Instale o [Terraform](https://developer.hashicorp.com/terraform/downloads)
- Instale o [Git](https://git-scm.com/downloads)

---

### 📥 Clonando o repositório

```bash
git clone https://github.com/seu-usuario/cloudificando.git
cd cloudificando/2-vpc-subnets-cidrs
```

---

### 📦 Iniciando o Terraform

```bash
terraform init
```

Este comando prepara o diretório e baixa os plugins necessários.

---

### 🧱 Criando a infraestrutura

```bash
terraform apply
```

Confirme com `yes` quando for solicitado. O Terraform criará a VPC e subnets automaticamente na sua conta AWS.

---

### 💣 Destruindo os recursos (evitar cobranças)

```bash
terraform destroy
```

Sempre que terminar seus testes, destrua os recursos para não gerar custos na sua conta AWS.

---

## 📚 Conteúdo relacionado

✅ Leia o artigo completo no LinkedIn:  
[Cloudificando – Capítulo 2: VPC, Subnets e CIDRs](https://www.linkedin.com/pulse/cap%25C3%25ADtulo-2-vpc-subnets-e-cidrs-cloudificando-de-castro-neves-jr-st45f)

🖼️ Veja a imagem explicativa e outros capítulos em:  
[cloudificando.com.br](https://cloudificando.com.br) *(futuro)*

---

## ✉️ Feedback

Gostou do conteúdo?  
Ficou com dúvidas?  
Entre em contato.
[Jose Octavio de Castro Neves Jr](https://linkedin.com/in/joccastroneves)

---

**Série: Cloudificando – Fundamentos Cloud**  
*Build Smart, Scale Fast 🚀*
