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
  

# Módulo da EC2 da Seção 5 a 8 + as atividades da plataforma

## Task 1: Criar a função Lambda

Criar uma função chamada myStopinator no AWS Lambda
Usar Python 3.11
Selecionar uma role existente (myStopinatorRole)

## Task 2: Configurar o gatilho

Adicionar um trigger com EventBridge
Criar uma regra chamada everyMinute
Definir execução a cada 1 minuto

## Task 3: Configurar a função

Substituir o código da função
Inserir a região da AWS
Inserir o ID da instância EC2
O código faz a instância parar automaticamente

## Task 4: Verificar funcionamento

Conferir no EC2 se a instância foi parada
Se ligar novamente, ela será parada de novo automaticamente

## Finalização

Enviar a atividade
Encerrar o laboratório

Faça o módulo 5 e seu laboratório , e documente em um readme no github
Tarefa 1 – Criar a VPC
Você cria uma VPC completa usando o assistente “VPC e mais”, incluindo:

1 VPC (10.0.0.0/16)
1 sub-rede pública (10.0.0.0/24) e 1 privada (10.0.1.0/24)
1 Gateway da Internet (para acesso público)
1 Gateway NAT (para dar internet à sub-rede privada)
Tabelas de roteamento para cada sub-rede

A sub-rede pública acessa a internet diretamente via Gateway da Internet, enquanto a privada acessa via NAT (sem exposição direta).

## Tarefa 2 – Criar sub-redes adicionais
Você adiciona mais duas sub-redes em outra Zona de Disponibilidade:

1 pública (10.0.2.0/24)
1 privada (10.0.3.0/24)

Depois, associa:

Sub-redes privadas → tabela de rotas com NAT
Sub-redes públicas → tabela de rotas com Internet Gateway

Isso melhora a alta disponibilidade.

## Tarefa 3 – Criar Grupo de Segurança
Cria um grupo de segurança (firewall) chamado Web Security Group, permitindo:

Entrada HTTP (porta 80) de qualquer lugar

## Tarefa 4 – Criar instância EC2 (servidor web)
Você lança uma instância EC2 com:

Amazon Linux 2023
Tipo t2.micro
Sub-rede pública
IP público ativado
Grupo de segurança criado

Adiciona um script que instala Apache, PHP e um app web automaticamente.

Depois, acessa o servidor pelo DNS público e vê a página funcionando.



# S3  AWS

## 🚀 LABORATÓRIO AWS: GERENCIAMENTO DE VOLUMES COM Amazon EC2 E Amazon EBS

## 🎯 OBJETIVO

* Aprender a criar, anexar, configurar e restaurar volumes na AWS, garantindo armazenamento persistente e recuperação de dados.


## 🧱 CRIAÇÃO DO VOLUME EBS
Volume de 1 GiB (gp2) criado
Mesma Zona de Disponibilidade da instância
Tag adicionada: Name = My Volume


## 🔗 ANEXANDO À INSTÂNCIA
Volume conectado à instância Lab
Dispositivo definido como /dev/sdb
Estado: em uso


## 💻 ACESSO À INSTÂNCIA
Conexão via Session Manager
Login como ec2-user


## ⚙️ CONFIGURAÇÃO DO SISTEMA DE ARQUIVOS
Sistema de arquivos ext3 criado
Montagem em /mnt/data-store
Configuração automática no /etc/fstab
Arquivo de teste (file.txt) criado e verificado


## 📸 CRIAÇÃO DE SNAPSHOT (BACKUP)
Snapshot criado: My Snapshot
Armazena apenas dados utilizados
Arquivo original removido para teste


## ♻️ RESTAURAÇÃO DO SNAPSHOT
Novo volume criado (Restored Volume)
Anexado como /dev/sdc
Montado em /mnt/data-store2
Arquivo restaurado com sucesso ✅


## 🏁 CONCLUSÃO
Volume EBS criado e configurado
Snapshot realizado
Dados restaurados com sucesso


## 💡 RESUMO FINAL

* CRIAR → ANEXAR → CONFIGURAR → SALVAR → RESTAURAR
---
