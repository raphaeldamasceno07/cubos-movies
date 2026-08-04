# Modelo de Domínio

**Versão:** 1.2

**Data:** 04/08/2026

**Status:** Elaborado

**Participantes:**

- Cliente
- Analista de Sistemas

## Objetivo

Modelar o domínio da aplicação, definindo as principais entidades do negócio, seus atributos, responsabilidades e relacionamentos.

## Entidades

- Usuário
- Filme

### Usuário

#### Descrição

Representa uma pessoa autenticada que utiliza o sistema para gerenciar sua coleção pessoal de filmes.

#### Atributos

- id
- nome
- email
- senha
- criado_em
- atualizado_em

#### Responsabilidades

- Gerenciar sua coleção de filmes.
- Receber notificações sobre lançamentos.
- Possuir filmes cadastrados.

---

### Filme

##### Descrição

Representa um filme cadastrado por um usuário para compor sua coleção pessoal.

#### Atributos

- id
- titulo
- descricao
- imagem
- genero
- data_lancamento
- duracao
- status
- slug
- criado_em
- atualizado_em

#### Responsabilidades

- Armazenar as informações do filme.
- Atualizar suas informações.
- Calcular automaticamente seu status com base na data de lançamento.
- Pertencer a um único usuário.

## Relacionamentos

- Um usuário pode possuir vários filmes.
- Cada filme pertence a um único usuário.

## Regras do Domínio

- O e-mail do usuário deve ser único.
- Um usuário pode visualizar apenas os filmes cadastrados por ele.
- Um usuário pode editar apenas os filmes cadastrados por ele.
- Um usuário pode excluir apenas os filmes cadastrados por ele.
- Cada filme pertence a um único usuário.
- O status do filme deve ser calculado automaticamente com base na data de lançamento.
- O slug do filme deve ser único.

## Status

✅ Elaborado

⏹️ Validado pelo Cliente

⏹️ Aprovado para Detalhamento

# Histórico de versões

| Versão | Data       | Alteração                                        | Responsável |
| ------ | ---------- | ------------------------------------------------ | ----------- |
| 1.0    | 04/08/2026 | Criação do documento.                            | Raphael     |
| 1.1    | 04/08/2026 | Revisão textual e padronização do modelo.        | Raphael     |
| 1.2    | 04/08/2026 | Documento validado e aprovado para detalhamento. | Raphael     |
