---

# 🛠️ Auditoria de Recebimentos de Cargas - Monitoramento de Produtos PAR de Alto Risco
Este repositório contém um processo de auditoria que foi desenvolvido para monitorar o recebimento de cargas no depósito, com foco especial nos produtos classificados como **P.A.R de Alto Risco**. A solução foi criada como um **widget** para um portal interno da **Central de Segurança**, com o objetivo de destacar e detalhar os produtos críticos recebidos.
![image](https://github.com/user-attachments/assets/be1c1f2c-eea7-4570-9ea4-a9b30cf2397f)

---

## 🎯 Objetivo
* **Monitorar produtos PAR de alto risco** que entraram via recebimento no depósito.
* **Exibir alertas visuais** no portal interno quando produtos de risco elevado forem identificados, destacando informações como **placa do veículo, horário, e outros detalhes da carga**.
* **Exibir detalhes da carga** ao clicar na linha correspondente, incluindo informações sobre os itens e quantidades relacionadas.

---

## ⚙️ Funcionamento
1. O **widget** é integrado ao **portal interno** e realiza consultas nas tabelas do **TOTVS RMS**, especificamente relacionadas ao recebimento de pedidos via **WMS Mobile PDA**.
2. Para cada **recebimento de carga**, o sistema verifica se algum dos produtos é classificado como **PAR de alto risco**.
3. Se um produto de alto risco for identificado, a linha da atividade é destacada com uma cor **vermelha** para fácil visualização.
4. Ao clicar na linha, os detalhes da carga são exibidos, mostrando os **itens recebidos** e suas **quantidades**.

---

## 📊 Consultas de Banco de Dados

O processo faz consultas nas seguintes tabelas do **TOTVS RMS**:

* **Tabela de Recebimentos**: Contém os registros de pedidos recebidos via **WMS Mobile PDA**.
* **Tabela de Produtos PAR**: Contém os produtos que foram classificados como **PAR de alto risco** é uma tabela personalizada na base do Fluig.

---

## 🔴 Exemplo de Exibição
1. **Linhas destacadas em vermelho**: As atividades que envolvem produtos de alto risco são exibidas em vermelho no portal.
![image](https://github.com/user-attachments/assets/b6381762-7165-4ae5-b1b5-a6f73f3797f5)

2. Ao **clicar na linha**, é exibido um painel com informações detalhadas sobre a carga, como:
![image](https://github.com/user-attachments/assets/3fc52ff6-ae49-4391-be13-572eafa93464)

   * Placa do veículo
   * Hora do recebimento
   * Itens recebidos
   * Quantidades de itens
   * Produto PAR de alto risco identificado

---

## 🛠️ Tecnologias Utilizadas
* **TOTVS RMS** (consultas em banco de dados)
* **WMS Mobile PDA** (integração de dados de recebimento)
* **Portal Interno** (widget para exibição)
* **JavaScript** (para o widget no portal interno)
* **SQL** (para consultas no banco de dados)

---

## 📝 Exemplo de Log (simulação)
```txt
[INFO] Iniciando auditoria de recebimentos de cargas
[INFO] Verificando pedidos recebidos via WMS Mobile PDA
[INFO] Produto PAR de alto risco identificado no pedido ID 2535 - Carga destacada
[INFO] Detalhes da carga: Placa: ABC-1234, Hora: 14:30, Itens: Produto X (10 un.), Produto Y (5 un.)
[ALERTA] Linha destacada em vermelho no portal
```

---

## 📡 Fluxo de Dados (Exemplo de Estrutura de Tabelas)

### Tabela de Recebimentos:

| Pedido ID | CodFilial | Placa Veículo | Hora Recebimento | Produto   | Quantidade |
| --------- | --------- | ------------- | ---------------- | --------- | ---------- |
| 2535      | 7         | ABC-1234      | 14:30            | Produto X | 10         |
| 2535      | 7         | ABC-1234      | 14:30            | Produto Y | 5          |

### Tabela de Produtos PAR (alto risco):

| CodProduto | Descrição             | Categoria |
| ---------- | --------------------- | --------- |
| Produto X  | Produto de alto risco | PAR       |

---

## 📌 Observações
* Este processo foi projetado para ser utilizado exclusivamente pela **Central de Segurança** para monitoramento de produtos de risco no recebimento.
* **Recomenda-se** que o widget seja testado e ajustado conforme as necessidades específicas do cliente antes de ser aplicado em produção.

---

## 👨‍💻 Autor
Desenvolvido por [Raphael Bezerra](https://github.com/devraphaelbezerra)
Especialista em segurança e auditoria de processos no ecossistema TOTVS RMS.

---

### Estrutura Sugerida do Repositório

* **src/**: Scripts e código fonte do widget.
* **docs/**: Documentação e instruções de uso.
* **logs/**: Logs gerados pelo processo (se aplicável).

---
