# 🚀 Estudo de Automação: n8n + PostgreSQL + Landing Page

Este projeto nasceu da curiosidade de entender como conectar as peças de um sistema real. Decidi usar meu **Homelab** para criar uma estrutura de automação de vendas para uma escola fictícia de design e motion.

A ideia central aqui não foi apenas criar um site, mas dominar o fluxo dos dados: desde o clique do usuário até a persistência no banco de dados e a tomada de decisão lógica.

O estudo no geral foi bem simples, no futuro pretendo aplicar um projeto semelhante visando a realidade, onde terá desafios maior.

---

## 🧠 O foco do estudo: n8n

O **n8n** foi o coração deste projeto. Em vez de codar um backend inteiro do zero, usei o n8n para gerenciar:

* **Recebimento de dados:** Via Webhook conectado ao formulário da Landing Page.
* **Persistência:** Inserção automática no **PostgreSQL** após o recebimento.
* **Lógica de Negócio:** Uso do nó *Switch* para separar os alunos por interesse (Design ou Motion) e preparar o envio de e-mails específicos.



---

## 🏠 Homelab & Docker: O poder do Self-Hosting

Uma das maiores lições deste projeto foi usar o **Umbrel OS** no meu notebook para gerenciar tudo via **Docker**. 

* **Facilidade:** O Docker facilitou subir o banco de dados e o pgAdmin sem conflitos com o sistema principal.
* **Portainer:** Usei para gerenciar os containers e entender a rede interna (já tinha o docker a tempos, mas não havia pensando até então em usar ele para criar o banco de dados).
* **Custo Zero:** Tudo rodou localmente, sem depender de serviços de nuvem pagos para validar a ideia.

---

## 🛠️ Tecnologias Utilizadas

* **Frontend:** HTML5 e Tailwind CSS (Landing Page).
* **Automação:** n8n (Self-hosted via Docker).
* **Banco de Dados:** PostgreSQL 16.
* **Gestão de Banco:** pgAdmin 4.
* **Infra:** Docker & Portainer rodando em Umbrel OS.

---

## 📂 Como reproduzir (ou para o meu "eu" do futuro)

1.  **Banco de Dados:** Criar o database `escola_design` e a tabela `alunos` usando o script SQL disponível na pasta `/infra`.
2.  **n8n:** Importar o arquivo `.json` da pasta `/n8n` para o seu painel.
3.  **Frontend:** Ajustar a URL do `fetch` no `index.html` para o IP do seu Webhook local.

---

### 📝 Notas de aprendizado
Neste projeto, enfrentei e resolvi desafios reais:
* Configuração de volumes e permissões no Docker.
* Autenticação e conexão entre serviços na mesma rede Docker.
* Mapeamento de colunas e tratamento de erros de inserção (Upsert vs Insert) no PostgreSQL.
