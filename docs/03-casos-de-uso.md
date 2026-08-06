# 👥 Casos de Uso

## Projeto

**Emanuel Conecta**

---

# UC-01 – Cadastro de Usuário

## Objetivo

Permitir que uma pessoa crie uma conta para acessar o aplicativo da Igreja Batista Emanuel.

## Atores

- Visitante

## Pré-condições

- O usuário não pode possuir um cadastro com o mesmo e-mail.
- O usuário deve possuir um endereço de e-mail válido.

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
7. O administrador poderá alterar posteriormente o perfil para Membro, Diácono ou Administrador.

## Fluxos Alternativos

### FA-01 – E-mail já cadastrado

1. O sistema identifica que o e-mail já existe.
2. Exibe uma mensagem informando que o usuário já possui cadastro.

### FA-02 – Senhas diferentes

1. O sistema identifica que as senhas não coincidem.
2. Solicita que o usuário corrija os campos.

### FA-03 – Campos obrigatórios não preenchidos

1. O sistema informa quais campos precisam ser preenchidos.

## Pós-condições

- O usuário passa a existir no banco de dados.
- Seu perfil inicial será **Visitante**.

## Regras de Negócio

- RN01 – Todo novo usuário será cadastrado como **Visitante**.
- RN02 – Apenas um Administrador poderá alterar o perfil do usuário.
- RN03 – O e-mail deverá ser único no sistema.
