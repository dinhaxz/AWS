# AWS
Introdução à AWS (Amazon Web Services)
📌 O que é a AWS?
A Amazon Web Services (AWS) é uma plataforma de computação em nuvem criada pela Amazon que oferece uma ampla variedade de serviços, como:
Armazenamento de dados Computação (servidores virtuais) Bancos de dados Redes Inteligência artificial Segurança

Esses serviços são disponibilizados pela internet, permitindo que empresas e desenvolvedores utilizem infraestrutura de TI sem precisar investir em hardware físico.

🌍 Infraestrutura Global da AWS

A AWS possui uma infraestrutura global altamente distribuída, composta por:

🗺️ Regiões (Regions)

As Regiões são áreas geográficas separadas onde a AWS mantém seus data centers.

Exemplos:

América do Sul (São Paulo) América do Norte (Virgínia) Europa (Irlanda)

Cada região é isolada das outras, garantindo maior segurança e estabilidade.

🏢 Zonas de Disponibilidade (Availability Zones - AZs)

Cada região contém várias Zonas de Disponibilidade, que são:

Data centers fisicamente separados Conectados por redes de alta velocidade Projetados para alta disponibilidade e tolerância a falhas

💡 Isso significa que, se uma zona falhar, outras podem continuar operando normalmente.

💰 Economia da Nuvem ⚙️ Modelo Pay-as-you-go

A AWS utiliza o modelo “pague pelo uso” (pay-as-you-go), onde você:

Paga apenas pelos recursos utilizados Não precisa de investimento inicial Pode escalar recursos conforme a demanda

Exemplo:

Usou um servidor por 2 horas → paga apenas por 2 horas Armazenou 10 GB → paga apenas por esse espaço 📈 Economia de Escala

A AWS consegue oferecer preços competitivos graças à economia de escala, que funciona assim:

A Amazon opera data centers gigantescos ao redor do mundo Quanto mais clientes utilizam a plataforma, menor o custo por unidade de recurso Parte dessa redução de custo é repassada aos clientes

👉 Mesmo com preços reduzidos, a empresa gera lucro devido ao alto volume de usuários e uso contínuo dos serviços.

IAM - AWS

# ☁️ Laboratório 3: Introdução ao Amazon EC2

## 🎯 Visão geral e objetivos do laboratório

**🧩 Diagrama de arquitetura**



Este laboratório oferece uma visão geral básica sobre como iniciar, redimensionar, gerenciar e monitorar uma instância do Amazon EC2.

O Amazon Elastic Compute Cloud (Amazon EC2) é um serviço da web que fornece capacidade computacional redimensionável na nuvem. Ele foi projetado para facilitar a computação em nuvem na escala da web para os desenvolvedores.

A interface simples do Amazon EC2 permite configurar recursos com pouco esforço, oferecendo controle total da infraestrutura e rápida escalabilidade ⚡.



---

## 🎓 Objetivos

Após concluir o laboratório, você será capaz de:

* 🚀 Iniciar um servidor web com proteção contra encerramento
* 📊 Monitorar sua instância EC2
* 🔓 Liberar acesso HTTP no grupo de segurança
* 🔄 Redimensionar a instância conforme necessário
* 📏 Explorar limites do EC2
* 🛑 Testar proteção contra interrupção
* ⏹️ Interromper a instância

---

## ⏱️ Duração

Aproximadamente **35 minutos**.

---

## ⚠️ Restrições

O ambiente pode limitar ações fora do escopo do laboratório.

---

## 🔐 Acessar o Console AWS

1. ▶️ Clique em **Iniciar laboratório**
2. ⏳ Aguarde o indicador ficar verde
3. 🔗 Clique no link da AWS
4. 🚫➡️ Permita pop-ups se necessário
5. 🖥️ Organize sua tela

---

## 📝 Crédito do laboratório

* ✔️ Use nomes exatamente como instruído
* 🔤 Atenção a maiúsculas/minúsculas
* 📌 Siga os formatos corretamente

---

# 🧪 Tarefa 1: Iniciar instância EC2

### ⚙️ Configurações principais:

* 🏷️ Nome: **Web Server**
* 💿 AMI: Amazon Linux 2023
* 🖥️ Tipo: t2.micro
* 🔑 Chave: vockey
* 🌐 VPC: Lab VPC



### 🔥 Script:


```bash id="ec2script"


#!/bin/bash
dnf install -y httpd
systemctl enable httpd
systemctl start httpd
echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html
```

### 🛡️ Ativar:

* Proteção contra encerramento

### ✅ Resultado:

* Estado: Em execução
* Status: 2/2 checks OK

---

# 📊 Tarefa 2: Monitoramento

* ✔️ Status checks
* 📈 CloudWatch
* 📜 Logs do sistema
* 🖼️ Screenshot da instância

---

# 🌍 Tarefa 3: Acessar servidor web

### ❌ Problema:

Porta 80 bloqueada

### ✅ Solução:

Adicionar regra:

* Tipo: HTTP
* Origem: Anywhere IPv4

### 🎉 Resultado:

```id="webmsg"


Hello From Your Web Server!
```

---

# 🔄 Tarefa 4: Redimensionamento





### Passos:

1. ⏹️ Interromper instância
2. 🔁 Alterar tipo → t2.small
3. 🛡️ Ativar proteção contra interrupção
4. 💾 Aumentar disco (8 → 10 GiB)
5. ▶️ Reiniciar







---

# 📏 Tarefa 5: Limites do EC2

* 🔍 Acessar Service Quotas
* 📊 Ver limites de instâncias
* 📈 Solicitar aumento (se necessário)




---

# 🛑 Tarefa 6: Proteção contra interrupção

### Teste:

* ❌ Falha ao parar instância

### Correção:

* 🔓 Desativar proteção
* ⏹️ Interromper novamente

---

# 📤 Envio

1. 📨 Clique em **Enviar**
2. ✔️ Confirme
3. ⏳ Aguarde pontuação

💡 Pode reenviar quantas vezes quiser.

---

# 🏁 Conclusão



🎉 Parabéns! Laboratório concluído.

* 🔚 Clique em **Encerrar laboratório**
* ✔️ Confirme

---

# 📚 Recursos adicionais

* 🖥️ Instâncias EC2
* 📦 AMIs
* 💾 EBS
* 🔐 Segurança
* 📊 Monitoramento
* 🔄 Escalabilidade







---
