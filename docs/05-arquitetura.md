# 🏗️ Arquitetura do Sistema

## Emanuel Conecta

### 1. Visão geral

O Emanuel Conecta será um aplicativo mobile desenvolvido para a Igreja Batista Emanuel.

O sistema terá como objetivo facilitar a comunicação entre a igreja e sua comunidade, disponibilizando informações como avisos, eventos, aniversariantes, pedidos de oração e acesso ao grupo de jovens.

A aplicação será desenvolvida pensando principalmente em facilidade de uso, acessibilidade e segurança.

---

## 2. Arquitetura do sistema

O sistema será dividido em três camadas principais:

```text
┌───────────────────────────────┐
│       📱 APLICATIVO           │
│                               │
│       Flutter + Dart          │
└───────────────┬───────────────┘
                │
                │ HTTPS / REST API
                ▼
┌───────────────────────────────┐
│       ☕ BACKEND               │
│                               │
│       Java + Spring Boot      │
│                               │
│  • Autenticação               │
│  • Regras de negócio          │
│  • Usuários                   │
│  • Eventos                    │
│  • Avisos                     │
│  • Pedidos de oração          │
└───────────────┬───────────────┘
                │
                │ SQL
                ▼
┌───────────────────────────────┐
│       🗄️ BANCO DE DADOS       │
│                               │
│          PostgreSQL           │
└───────────────────────────────┘
