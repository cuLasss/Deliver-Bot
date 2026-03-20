<div align="center">

# 🤖 Deliver Bot

### Plataforma SaaS de Automação de Mensagens via WhatsApp para Empresas

[![Status](https://img.shields.io/badge/Status-Em%20Desenvolvimento%20(MVP%20Ativo)-brightgreen?style=for-the-badge)](https://github.com/cuLasss/Deliver-Bot)
[![Versão](https://img.shields.io/badge/Versão-3.0.0-blue?style=for-the-badge)](https://github.com/cuLasss/Deliver-Bot)
[![Licença](https://img.shields.io/badge/Licença-Proprietária-red?style=for-the-badge)](https://github.com/cuLasss/Deliver-Bot)

</div>

---

## 📌 Sobre o Projeto

O **Deliver Bot** é uma plataforma SaaS (Software as a Service) desenvolvida para otimizar a comunicação entre empresas e seus clientes por meio do **envio automatizado e em lote de mensagens via WhatsApp**.

O sistema nasceu de uma dor real observada no dia a dia de empresas de entrega, comércio e serviços: **o enorme esforço manual de notificar clientes um por um**, seja por ligação ou mensagem individual — um processo lento, trabalhoso e ineficiente.

> 🚀 **O MVP já está em operação**, sendo validado com empresas reais. A plataforma é multifilial, multi-usuário e opera de forma totalmente autônoma após a configuração inicial.

---

## ❗ O Problema

Empresas que precisam comunicar informações a muitos clientes (confirmações de entrega, agendamentos, promoções, avisos de chegada de pedido etc.) enfrentam diariamente os seguintes desafios:

| Problema | Impacto |
|---|---|
| 📞 Ligar para cada cliente individualmente | Alto custo de tempo e recursos humanos |
| 📋 Mensagens manuais uma por uma no WhatsApp | Operador gasta horas para atingir dezenas de contatos |
| 🤖 Telemarketing invasivo e mal recebido | Clientes bloqueiam, ignoram ou ficam insatisfeitos |
| 📊 Sem rastreamento de confirmações | Empresa não sabe quem recebeu, leu ou respondeu |
| 🏢 Múltiplas filiais sem gestão centralizada | Falta de controle e padronização nas comunicações |

**Resultado:** Processos lentos, clientes mal informados, operadores sobrecarregados e perda de eficiência operacional.

---

## ✅ A Solução

O **Deliver Bot** resolve esses problemas entregando uma plataforma completa e intuitiva que permite:

- 📤 **Envio em lote de mensagens via WhatsApp** para dezenas de contatos em poucos minutos
  > Com a ferramenta, é possível enviar mensagens para **30 pessoas em até 4 minutos**, de forma automatizada e sem esforço manual
- 🤖 **Bots por filial** com conexão WhatsApp dedicada via QR Code
- 📊 **Dashboard com métricas em tempo real** de envios, confirmações e campanhas
- 🗂️ **Gestão de clientes, entregas e pré-entregas** com controle de status
- 📣 **Campanhas de mensagem** configuráveis com delay humanizado entre envios (para evitar bloqueios)
- 👥 **Multi-usuário e multifilial** com hierarquia de papéis (Super Admin, Admin, Operador)
- 🔐 **Sessões seguras** com logout automático por inatividade e controle de acesso por JWT

---

## 🧩 Arquitetura do Sistema

O Deliver Bot é composto por três camadas principais integradas entre si:

```
┌─────────────────────────────────────────────────────────┐
│                     FRONTEND (SaaS)                      │
│          React 19 + Vite + TailwindCSS + Zustand         │
│   Dashboard │ Bots │ Clientes │ Campanhas │ Mensagens     │
└──────────────────────┬──────────────────────────────────┘
                       │ REST API + WebSocket
┌──────────────────────▼──────────────────────────────────┐
│                   BACKEND (API REST)                      │
│         FastAPI (Python) + SQLAlchemy + SQLite            │
│  Auth │ Bots │ Filiais │ Mensagens │ Campanhas │ Entregas │
└──────────────────────┬──────────────────────────────────┘
                       │ HTTP Interno
┌──────────────────────▼──────────────────────────────────┐
│               SERVIÇO WHATSAPP (Node.js)                  │
│         Baileys (WhatsApp Web API não-oficial)            │
│     Uma instância por filial │ QR Code │ Envio em lote   │
└─────────────────────────────────────────────────────────┘
```

---

## 🛠️ Stack Tecnológica

### Backend
- **Python** com **FastAPI** — API REST de alta performance
- **SQLAlchemy** — ORM para mapeamento do banco de dados
- **SQLite** — Banco de dados relacional leve e eficiente
- **JWT (JSON Web Tokens)** — Autenticação segura e stateless
- **Python-SocketIO** — Comunicação em tempo real via WebSocket
- **Passlib + Bcrypt** — Hashing seguro de senhas

### Frontend
- **React 19** — Interface reativa e moderna
- **Vite 7** — Build tool ultrarrápido
- **TailwindCSS 4** — Estilização utilitária
- **Zustand** — Gerenciamento de estado global
- **React Router DOM 7** — Roteamento de páginas
- **Lucide React** — Ícones modernos

### Serviço WhatsApp
- **Node.js** com **Express** — Servidor de integração
- **Baileys (@whiskeysockets/baileys)** — Biblioteca de integração com o WhatsApp Web
- **QRCode** — Geração de QR Code para autenticação do número
- **Pino** — Logging estruturado de alto desempenho

---

## 🗃️ Módulos do Sistema

| Módulo | Descrição |
|---|---|
| 🔐 **Autenticação** | Login, logout, controle de sessão e permissões por papel |
| 🏢 **Filiais** | Gestão de múltiplas filiais com bots independentes |
| 👤 **Usuários** | Cadastro e controle de operadores por filial |
| 📱 **Bots WhatsApp** | Conexão, desconexão e monitoramento de instâncias por filial |
| 👥 **Clientes** | Cadastro e gestão da base de contatos |
| 📦 **Pré-Entregas** | Registro e confirmação via WhatsApp de entregas pendentes |
| 🚚 **Entregas** | Controle de status de entregas realizadas |
| 💬 **Mensagens** | Envio manual e em lote para contatos selecionados |
| 📣 **Campanhas** | Criação de campanhas com envio automatizado e métricas |
| 📊 **Dashboard** | Visão geral com indicadores em tempo real |
| ⚙️ **Configurações** | Gerenciamento de conta, número conectado e preferências |

---

## 📈 Resultados (MVP em Validação)

- ✅ **30 mensagens enviadas em até 4 minutos**, sem intervenção manual
- ✅ Eliminação do processo manual de ligações um a um
- ✅ Confirmações de entrega automatizadas com resposta do cliente
- ✅ Painel de controle com visibilidade total das operações por filial
- ✅ Sistema em uso por empresas reais durante a fase de MVP

---

## 🗺️ Roadmap

O sistema está em desenvolvimento ativo. As próximas etapas incluem:

- [ ] 🌐 Deploy em nuvem com infraestrutura escalável
- [ ] 📊 Relatórios avançados com exportação em PDF/Excel
- [ ] 🔔 Notificações push para operadores em tempo real
- [ ] 🤖 Respostas automáticas com fluxos de conversa configuráveis (chatbot)
- [ ] 📱 Aplicativo mobile para operadores
- [ ] 💳 Sistema de assinaturas e planos (Billing SaaS)
- [ ] 🔗 Integrações com ERPs e sistemas de gestão externos
- [ ] 🌍 Suporte a múltiplas plataformas de mensageria (além do WhatsApp)

---

## ⚠️ Aviso Legal

> Este repositório contém **apenas a documentação pública** do projeto.  
> O código-fonte é **proprietário e privado**.  
> O uso da API do WhatsApp por meio de bibliotecas não-oficiais (como Baileys) é de responsabilidade do operador, seguindo os [Termos de Serviço do WhatsApp](https://www.whatsapp.com/legal/terms-of-service).  
> Este projeto **não é afiliado, patrocinado ou endossado pelo WhatsApp Inc. ou Meta Platforms, Inc.**

---

## 📬 Contato

Interessado na plataforma ou quer saber mais sobre o projeto?

**Desenvolvedor:** Lucas  
**GitHub:** [@cuLasss](https://github.com/cuLasss)

---

<div align="center">

**⭐ Se este projeto te inspirou, deixe uma estrela no repositório!**

*Deliver Bot — Automatizando comunicações, humanizando resultados.*

</div>
