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






3. Aplicativo Mobile

O aplicativo será desenvolvido utilizando:

Flutter
Dart

O aplicativo será responsável pela interface utilizada pelos membros, visitantes, pastores, diáconos e administradores.

Principais funcionalidades
Cadastro de usuário
Login
Recuperação de senha
Atualização de perfil
Visualização de avisos
Visualização de eventos
Visualização de aniversariantes
Envio de pedidos de oração
Acesso ao grupo de jovens
Funcionalidades administrativas
4. Backend

O backend será desenvolvido utilizando:

Java
Spring Boot
Spring Security
JWT
Maven

O backend será responsável pelo processamento das informações e pelas regras de negócio do sistema.

Principais responsabilidades
Cadastro de usuários
Autenticação
Recuperação de senha
Controle de permissões
Gerenciamento de usuários
Gerenciamento de eventos
Gerenciamento de avisos
Gerenciamento de pedidos de oração
Consulta de aniversariantes
Comunicação com o banco de dados
Validação das informações
Segurança da aplicação
5. Banco de dados

O banco de dados utilizado será o PostgreSQL.

Inicialmente serão previstas entidades para:

Usuários
Eventos
Avisos
Pedidos de oração
Perfis e permissões

O modelo do banco de dados será detalhado em documentação específica posteriormente.

6. Autenticação e autorização

O sistema utilizará autenticação para controlar o acesso dos usuários.

A autenticação será realizada utilizando:

Login
Senha
JWT (JSON Web Token)

As senhas não serão armazenadas diretamente no banco de dados.

Perfis de usuário

O sistema terá diferentes níveis de acesso:

Perfil	Acesso
Visitante	Funcionalidades básicas
Membro	Funcionalidades de membro
Diácono	Funcionalidades de diácono
Pastor	Funcionalidades pastorais
Administrador	Gerenciamento do sistema

O controle de acesso será baseado no perfil do usuário.


7. Comunicação entre aplicativo e backend

O aplicativo Flutter se comunicará com o backend através de uma API REST.

Exemplo:


Aplicativo Flutter
       │
       │ Requisição HTTP
       ▼
Spring Boot API
       │
       │ Consulta
       ▼
PostgreSQL
       │
       │ Resultado
       ▼
Spring Boot API
       │
       │ Resposta JSON
       ▼
Aplicativo Flutter




8. Segurança

O sistema deverá possuir mecanismos de segurança para proteger os dados dos usuários.

Entre as medidas previstas estão:

Senhas armazenadas de forma segura
Autenticação por JWT
Controle de acesso por perfil
HTTPS
Validação dos dados recebidos
Proteção dos endpoints da API
Tratamento de erros
Controle de acesso às funcionalidades administrativas
9. Acessibilidade e usabilidade

Como o aplicativo será utilizado por pessoas de diferentes idades, incluindo idosos, a interface deverá priorizar simplicidade e facilidade de utilização.

Serão consideradas as seguintes características:

Botões grandes
Textos legíveis
Contraste adequado
Navegação simples
Poucas etapas para realizar uma ação
Ícones acompanhados de textos
Linguagem simples
Feedback visual para ações realizadas
Layout organizado
10. Integração com WhatsApp

O aplicativo terá uma funcionalidade para direcionar os jovens para o grupo de WhatsApp da igreja.

O aplicativo não será responsável por gerenciar as mensagens do grupo.

Ao selecionar a opção correspondente, o usuário será direcionado para o grupo através do WhatsApp.

11. Escalabilidade

A arquitetura será desenvolvida de forma que novas funcionalidades possam ser adicionadas futuramente sem a necessidade de reconstruir todo o sistema.

Possíveis funcionalidades futuras:

Agenda da igreja
Check-in e check-out
Notificações
Devocionais
Estudos bíblicos
Escalas de voluntários
Transmissões ao vivo
Comunicação entre departamentos
Painel administrativo web


12. Tecnologias
Camada	Tecnologia
Aplicativo Mobile	Flutter
Linguagem Mobile	Dart
Backend	Java
Framework Backend	Spring Boot
API	REST
Autenticação	Spring Security + JWT
Banco de Dados	PostgreSQL
Gerenciamento de dependências	Maven
Versionamento	Git + GitHub
Modelagem	UML / Draw.io


13. Estrutura simplificada

Emanuel Conecta
│
├── Aplicativo Mobile
│   └── Flutter
│
├── Backend
│   ├── Java
│   ├── Spring Boot
│   ├── Spring Security
│   └── REST API
│
├── Banco de Dados
│   └── PostgreSQL
│
└── Documentação
    ├── Visão Geral
    ├── Requisitos
    ├── Casos de Uso
    ├── Diagrama UML
    └── Arquitetura


    14. Objetivo da arquitetura

A arquitetura foi definida buscando equilíbrio entre:

Segurança
Facilidade de manutenção
Escalabilidade
Organização
Desempenho
Acessibilidade
Facilidade de evolução do sistema

A arquitetura poderá ser evoluída conforme novas necessidades da Igreja Batista Emanuel forem identificadas.


**`Adiciona documentação da arquitetura do sistema`**
