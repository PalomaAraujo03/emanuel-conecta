# 👥 Casos de Uso

## Projeto

**Emanuel Conecta**

---

# Objetivo

Este documento descreve como os usuários interagem com o aplicativo Emanuel Conecta.

---

# Atores do Sistema

| Ator | Descrição |
|------|-----------|
| Visitante | Pessoa cadastrada que ainda não foi aprovada pela igreja. |
| Membro | Usuário aprovado pela igreja. |
| Diácono | Usuário com permissões adicionais para auxiliar na administração. |
| Administrador | Responsável pelo gerenciamento completo do sistema. |

---

# UC-01 – Cadastro de Usuário

## Objetivo

Permitir que uma pessoa crie uma conta para acessar o aplicativo.

## Ator Principal

Visitante

## Pré-condições

- O usuário não pode possuir cadastro com o mesmo e-mail.
- Deve possuir um endereço de e-mail válido.

## Fluxo Principal

1. O visitante acessa a tela de cadastro.
2. O sistema solicita:
   - Nome completo;
   - E-mail;
   - Telefone;
   - Data de nascimento;
   - Senha;
   - Confirmar senha.
3. O visitante preenche os dados.
4. O sistema valida as informações.
5. O sistema cria a conta com o perfil **Visitante**.
6. O sistema informa que o cadastro foi realizado com sucesso.
7. O usuário poderá fazer login.

## Fluxos Alternativos

### FA-01 – E-mail já cadastrado

1. O sistema identifica que o e-mail já existe.
2. Exibe uma mensagem informando que já existe uma conta cadastrada.

### FA-02 – Senhas diferentes

1. O sistema identifica que as senhas não coincidem.
2. Solicita a correção.

### FA-03 – Campos obrigatórios

1. O sistema identifica campos vazios.
2. Solicita o preenchimento.

## Pós-condições

- O usuário fica cadastrado como **Visitante**.

## Regras de Negócio

- RN01 – Todo novo usuário será cadastrado como Visitante.
- RN02 – Apenas um Administrador poderá alterar o perfil do usuário.
- RN03 – O e-mail deverá ser único no sistema.

---

# UC-02 – Login

## Objetivo

Permitir que usuários autenticados acessem o aplicativo.

## Atores

- Visitante
- Membro
- Diácono
- Administrador

## Pré-condições

- Possuir cadastro.
- Possuir senha válida.

## Fluxo Principal

1. O usuário acessa a tela de login.
2. Informa e-mail e senha.
3. O sistema valida as credenciais.
4. O sistema identifica o perfil do usuário.
5. O usuário é direcionado para a tela inicial.

## Fluxos Alternativos

### FA-01 – Senha incorreta

O sistema informa que a senha está incorreta.

### FA-02 – Usuário inexistente

O sistema informa que não existe cadastro para o e-mail informado.

### FA-03 – Conta desativada

O sistema informa que a conta está desativada e orienta o usuário a entrar em contato com a administração.

## Pós-condições

O usuário acessa o aplicativo conforme as permissões do seu perfil.

## Regras de Negócio

- RN04 – Apenas usuários cadastrados poderão acessar o sistema.
- RN05 – As senhas serão armazenadas de forma criptografada.
- RN06 – O sistema registrará a data e o horário do último acesso do usuário.
