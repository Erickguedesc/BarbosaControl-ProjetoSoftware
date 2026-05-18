# 🏷️ Barbosa Control 👨‍💻

> Sistema de gestão projetado para a loja **Barbosa Confecções**, com foco no controle de vendas, clientes, estoque, pagamentos fiados, contas vencidas e integração conceitual com o sistema Asaas.

<table>
  <tr>
    <td width="800px">
      <div align="justify">
        O <b>Barbosa Control</b> é um projeto de software desenvolvido para propor uma solução digital para a loja <b>Barbosa Confecções</b>, que atualmente realiza grande parte do controle de vendas, clientes e contas fiadas por meio de anotações em cadernos. 
        O sistema tem como objetivo melhorar o controle financeiro da loja, permitindo o registro de vendas à vista, no débito, no crédito, no fiado e por boleto, além do acompanhamento de contas em aberto, pagamentos parciais, contas vencidas e histórico de clientes.
      </div>
    </td>
    <td>
      <div align="center">
        <img src="https://cdn-icons-png.flaticon.com/512/3081/3081559.png" alt="Logo do Projeto" width="120px"/>
      </div>
    </td>
  </tr> 
</table>

---

## 🚧 Status do Projeto

![Status](https://img.shields.io/badge/status-em%20projeto-blue?style=for-the-badge)
![UML](https://img.shields.io/badge/UML-PlantUML-orange?style=for-the-badge)
![Projeto](https://img.shields.io/badge/Projeto%20de%20Software-Documentação-green?style=for-the-badge)
![Versão](https://img.shields.io/badge/Versão-1.0.0-blue?style=for-the-badge)

> Este projeto não possui implementação de código-fonte. O objetivo é apresentar a documentação, arquitetura e modelagem UML de um sistema proposto.

---

## 📚 Índice

- [Links Úteis](#-links-úteis)
- [Sobre o Projeto](#-sobre-o-projeto)
- [Problema Identificado](#-problema-identificado)
- [Objetivos](#-objetivos)
- [Regras de Negócio](#-regras-de-negócio)
- [Funcionalidades Principais](#-funcionalidades-principais)
- [Atores do Sistema](#-atores-do-sistema)
- [Casos de Uso](#-casos-de-uso)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Arquitetura](#-arquitetura)
- [Diagramas UML](#-diagramas-uml)
- [Estrutura de Pastas](#-estrutura-de-pastas)
- [Testes](#-testes)
- [Documentações Utilizadas](#-documentações-utilizadas)
- [Autores](#-autores)
- [Licença](#-licença)

---

## 🔗 Links Úteis

* 📖 **PlantUML:** [https://plantuml.com/](https://plantuml.com/)
* 📄 **Documentação do Projeto:** [`docs/documentacao-projeto.md`](docs/documentacao-projeto.md)
* 🧩 **Diagramas UML:** [`docs/`](docs/)

---

## 📝 Sobre o Projeto

O **Barbosa Control** é uma proposta de sistema web para a loja **Barbosa Confecções**, uma loja de roupas que realiza vendas em diferentes formas de pagamento, incluindo dinheiro, débito, crédito, fiado e boleto.

Atualmente, o controle da loja é feito principalmente por meio de anotações em cadernos. Esse processo manual dificulta a consulta de informações importantes, como clientes com contas vencidas, pagamentos parciais, histórico de compras, controle de estoque e valores ainda pendentes.

A proposta do sistema é centralizar essas informações em uma aplicação digital, permitindo que o dono e os vendedores tenham mais controle sobre as vendas e sobre os clientes que compram fiado.

---

## ❗ Problema Identificado

A loja Barbosa Confecções possui um processo manual para controlar vendas e contas de clientes. Esse controle em cadernos pode gerar problemas como:

- dificuldade para consultar contas vencidas;
- risco de perda de informações;
- falta de histórico detalhado dos clientes;
- dificuldade para controlar pagamentos parciais;
- falta de controle automático sobre clientes inadimplentes;
- dificuldade para acompanhar o estoque;
- pouca visibilidade sobre o faturamento da loja.

---

## 🎯 Objetivos

### Objetivo Geral

Projetar um sistema para informatizar o controle de vendas, clientes, produtos, pagamentos e contas fiadas da loja Barbosa Confecções.

### Objetivos Específicos

- Registrar clientes da loja;
- Registrar produtos e controlar estoque;
- Registrar vendas realizadas;
- Controlar vendas fiadas com prazo de até 30 dias;
- Registrar pagamentos parciais, chamados internamente de AV;
- Identificar contas em aberto, pagas, pagas parcialmente e vencidas;
- Bloquear novas compras fiadas para clientes inadimplentes;
- Registrar cobranças vinculadas ao sistema Asaas;
- Gerar relatórios financeiros e operacionais.

---

## 📌 Regras de Negócio

| ID | Regra de Negócio |
|---|---|
| RN-01 | Somente clientes cadastrados podem realizar compras fiadas ou por boleto. |
| RN-02 | Vendas em dinheiro, débito ou crédito são consideradas pagas no momento da venda. |
| RN-03 | Toda venda fiada deve gerar uma conta a receber com prazo máximo de 30 dias. |
| RN-04 | O cliente pode realizar pagamento parcial da conta, chamado de AV. |
| RN-05 | Quando houver pagamento parcial, o saldo restante continuará em aberto. |
| RN-06 | Após um pagamento parcial, o saldo restante pode receber novo prazo de até 30 dias. |
| RN-07 | Cliente com conta vencida não pode realizar nova compra fiada até regularizar a dívida. |
| RN-08 | O sistema deve permitir registrar cobranças realizadas via Asaas. |
| RN-09 | A negativação do cliente não pertence ao sistema Barbosa Control, pois é uma regra externa do Asaas. |
| RN-10 | Toda venda registrada deve reduzir automaticamente a quantidade dos produtos no estoque. |
| RN-11 | Uma conta será considerada vencida quando passar da data de vencimento e ainda houver saldo pendente. |
| RN-12 | O sistema deve permitir consultar contas vencidas, contas em aberto e histórico de pagamentos. |

---

## ✨ Funcionalidades Principais

- 🔐 **Autenticação de Usuários:** acesso ao sistema por administrador e vendedor.
- 👤 **Cadastro de Clientes:** registro de nome, CPF, telefone, endereço e observações.
- 👕 **Cadastro de Produtos:** controle de roupas, categorias, tamanhos, cores, preços e estoque.
- 🛒 **Registro de Vendas:** vendas em dinheiro, débito, crédito, fiado ou boleto.
- 📆 **Controle de Fiado:** geração de conta com prazo de até 30 dias.
- 💰 **Pagamento Parcial / AV:** registro de valores pagos parcialmente pelo cliente.
- ⚠️ **Controle de Contas Vencidas:** identificação de clientes inadimplentes.
- 🚫 **Bloqueio de Novo Fiado:** impedimento de nova compra fiada para clientes com dívida vencida.
- 🧾 **Registro de Cobrança Asaas:** controle interno de cobranças feitas por boleto.
- 📦 **Controle de Estoque:** baixa automática de produtos vendidos.
- 📊 **Relatórios:** consulta de vendas, contas vencidas, clientes devedores e produtos com baixo estoque.

---

## 👥 Atores do Sistema

| Ator | Descrição |
|---|---|
| Administrador / Dono | Usuário principal do sistema. Pode gerenciar clientes, produtos, vendas, pagamentos, contas e relatórios. |
| Vendedor | Usuário responsável por registrar vendas, cadastrar clientes e consultar situação de pagamento. |
| Cliente | Pessoa que compra na loja. Não acessa diretamente o sistema, mas possui seus dados cadastrados. |
| Sistema Asaas | Sistema externo utilizado para geração de boletos e possibilidade de negativação de clientes inadimplentes. |

---

## 📍 Casos de Uso

| ID | Caso de Uso | Ator Principal |
|---|---|---|
| UC-01 | Cadastrar Cliente | Administrador / Vendedor |
| UC-02 | Cadastrar Produto | Administrador |
| UC-03 | Registrar Venda à Vista | Administrador / Vendedor |
| UC-04 | Registrar Venda Fiada | Administrador / Vendedor |
| UC-05 | Registrar Pagamento Parcial | Administrador / Vendedor |
| UC-06 | Registrar Quitação da Conta | Administrador / Vendedor |
| UC-07 | Consultar Contas Vencidas | Administrador |
| UC-08 | Bloquear Cliente para Fiado | Sistema |
| UC-09 | Registrar Cobrança via Asaas | Administrador |
| UC-10 | Gerar Relatório Financeiro | Administrador |
| UC-11 | Consultar Estoque | Administrador / Vendedor |

---

## 🛠 Tecnologias Utilizadas

As tecnologias abaixo são propostas para a arquitetura do sistema, considerando uma aplicação web moderna.

### 💻 Front-end

* **Framework/Biblioteca:** React
* **Linguagem:** JavaScript
* **Build Tool:** Vite
* **Estilização:** Tailwind CSS
* **Gerenciamento de Rotas:** React Router

### 🖥️ Back-end

* **Linguagem:** Java 17
* **Framework:** Spring Boot
* **Banco de Dados:** PostgreSQL
* **ORM:** Spring Data JPA / Hibernate
* **Autenticação:** Spring Security com JWT

### ⚙️ Infraestrutura & DevOps

* **Versionamento:** Git e GitHub
* **Containerização:** Docker e Docker Compose
* **Deploy Front-end:** Vercel
* **Deploy Back-end:** Render
* **Banco em Produção:** PostgreSQL Cloud

### 📐 Modelagem e Documentação

* **Diagramas UML:** PlantUML
* **Documentação:** Markdown
* **Arquitetura:** UML / C4 Model

---

## 🏗 Arquitetura

O sistema foi projetado com uma arquitetura em camadas, separando as responsabilidades da aplicação em front-end, back-end, banco de dados e integração externa.

### Camadas Propostas

- **Camada de Apresentação:** interface web acessada pelo dono da loja e vendedores.
- **Camada de Aplicação:** regras de negócio relacionadas a vendas, pagamentos, contas e estoque.
- **Camada de Persistência:** armazenamento dos dados em banco PostgreSQL.
- **Sistema Externo:** integração conceitual com o Asaas para emissão de boletos e controle externo de cobrança.

### Visão Geral

```text
Usuário
  ↓
Front-end React
  ↓
API REST Spring Boot
  ↓
Banco de Dados PostgreSQL
  ↓
Sistema Externo Asaas

