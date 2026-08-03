# Casos de Uso

**Versão:** 1.2

**Data:** 03/08/2026

**Status:** Aprovado para Detalhamento

---

## Convenções

Este documento descreve os casos de uso do Sistema de Gerenciamento de Filmes.

Todos os casos de uso seguem a mesma estrutura:

- **Objetivo:** descreve a finalidade do caso de uso.
- **Atores:** identifica quem interage com o sistema.
- **Gatilho:** evento que inicia o caso de uso.
- **Pré-condições:** condições que devem ser satisfeitas antes da execução.
- **Fluxo Principal:** sequência esperada de interação entre usuário e sistema.
- **Fluxos Alternativos:** cenários que desviam do fluxo principal, mas continuam válidos.
- **Pós-condições:** estado esperado do sistema após a execução.
- **Requisitos Relacionados:** requisitos funcionais e regras de negócio associados ao caso de uso.

### Numeração

- **UC** — Caso de Uso
- **RF** — Requisito Funcional
- **RN** — Regra de Negócio
- **RNF** — Requisito Não Funcional

---

## Documentos Relacionados

- 01 - Entendimento do Problema
- 02 - Especificação de Requisitos
- Diagrama de Casos de Uso

---

## Escopo

Este documento descreve os casos de uso identificados durante o levantamento e a especificação dos requisitos do Sistema de Gerenciamento de Filmes.

Os casos de uso apresentados representam as principais interações entre o usuário e o sistema, servindo como base para a modelagem do domínio, definição da arquitetura e implementação da aplicação.

---

# UC-001 — Cadastrar Usuário

### Objetivo

Permitir que um visitante crie uma conta para acessar e utilizar o sistema.

### Atores

- Usuário

### Gatilho

O visitante seleciona a opção **"Criar Conta"**.

### Pré-condições

- O usuário não deve estar autenticado.

### Fluxo Principal

1. O usuário acessa a tela de cadastro.
2. O sistema apresenta o formulário de cadastro.
3. O usuário informa os dados obrigatórios.
4. O usuário solicita o cadastro.
5. O sistema valida os dados informados.
6. O sistema cria a conta.
7. O sistema confirma o cadastro ao usuário.

### Fluxos Alternativos

#### A1. E-mail já cadastrado

- O sistema informa que o e-mail já está em uso.
- O usuário informa outro endereço de e-mail.
- O fluxo retorna ao passo 3.

#### A2. Um ou mais campos obrigatórios não foram informados

- O sistema informa os erros de validação.
- O usuário corrige os dados.
- O fluxo retorna ao passo 3.

### Pós-condições

- A conta do usuário foi criada.
- O usuário poderá realizar autenticação no sistema.

### Requisitos Relacionados

- RF01
- RN01

---

# UC-002 — Fazer Login

### Objetivo

Permitir que um usuário realize autenticação para acessar o sistema.

### Atores

- Usuário

### Gatilho

O visitante seleciona a opção **"Entrar"**.

### Pré-condições

- O usuário deve possuir uma conta cadastrada.
- O usuário não deve estar autenticado.

### Fluxo Principal

1. O usuário acessa a tela de login.
2. O sistema apresenta o formulário de login.
3. O usuário informa e-mail e senha.
4. O usuário solicita a autenticação.
5. O sistema valida as credenciais informadas.
6. O sistema autentica o usuário.
7. O sistema inicia a sessão do usuário.

### Fluxos Alternativos

#### A1. E-mail não cadastrado

- Por motivos de segurança, o sistema informa que as credenciais são inválidas.

#### A2. Senha incorreta

- Por motivos de segurança, o sistema informa que as credenciais são inválidas.

#### A3. Um ou mais campos obrigatórios não foram informados

- O sistema informa os erros de validação.
- O usuário corrige os dados.
- O fluxo retorna ao passo 3.

### Pós-condições

- O usuário encontra-se autenticado.
- Uma sessão válida foi iniciada.

### Requisitos Relacionados

- RF02
- RN10

---

# UC-003 — Listar Filmes

### Objetivo

Permitir que um usuário autenticado visualize a lista de filmes cadastrados por ele.

### Atores

- Usuário

### Gatilho

O usuário acessa a página de filmes.

### Pré-condições

- O usuário deve estar autenticado.

### Fluxo Principal

1. O usuário acessa a página de filmes.
2. O sistema valida a sessão do usuário.
3. O sistema consulta os filmes cadastrados pelo usuário.
4. O sistema aplica a paginação.
5. O sistema apresenta a lista de filmes.

### Fluxos Alternativos

#### A1. O usuário não está autenticado

- O sistema redireciona o usuário para a tela de login.

#### A2. O usuário não possui filmes cadastrados

- O sistema informa que nenhum filme foi encontrado.

### Pós-condições

- A lista de filmes foi apresentada ao usuário.

### Requisitos Relacionados

- RF06
- RN03
- RN10

---

# UC-004 — Pesquisar Filmes

### Objetivo

Permitir que um usuário autenticado pesquise filmes pelo título informado.

### Atores

- Usuário

### Gatilho

O usuário informa um termo de pesquisa.

### Pré-condições

- O usuário deve estar autenticado.
- O usuário deve estar na página de listagem de filmes.

### Fluxo Principal

1. O usuário informa um termo de pesquisa.
2. O sistema consulta os filmes cadastrados pelo usuário.
3. O sistema filtra os filmes cujo título corresponde ao termo informado.
4. O sistema apresenta os resultados encontrados.

### Fluxos Alternativos

#### A1. Nenhum filme corresponde ao termo pesquisado

- O sistema informa que nenhum filme foi encontrado.
- O sistema mantém o campo de pesquisa disponível para uma nova busca.

### Pós-condições

- O sistema apresentou os resultados da pesquisa.

### Requisitos Relacionados

- RF07
- RN03
- RN07
- RN10

---

# UC-005 — Filtrar Filmes

### Objetivo

Permitir que um usuário autenticado filtre sua lista de filmes utilizando os critérios disponíveis.

### Atores

- Usuário

### Gatilho

O usuário seleciona a opção **"Filtrar"**.

### Pré-condições

- O usuário deve estar autenticado.
- O usuário deve estar na página de listagem de filmes.

### Fluxo Principal

1. O usuário seleciona a opção de filtros.
2. O sistema apresenta os filtros disponíveis.
3. O usuário informa um ou mais critérios de filtragem.
4. O usuário solicita a aplicação dos filtros.
5. O sistema filtra os filmes cadastrados pelo usuário.
6. O sistema apresenta os filmes que atendem aos critérios informados.

### Fluxos Alternativos

#### A1. Nenhum filme atende aos critérios informados

- O sistema informa que nenhum filme foi encontrado.
- O sistema mantém os filtros preenchidos para que o usuário possa alterá-los.

### Pós-condições

- A lista de filmes foi atualizada de acordo com os filtros aplicados.

### Requisitos Relacionados

- RF08
- RN03
- RN08
- RN09
- RN10

---

# UC-006 — Cadastrar Filme

### Objetivo

Permitir que um usuário autenticado cadastre um novo filme.

### Atores

- Usuário

### Gatilho

O usuário seleciona a opção **"Cadastrar Filme"**.

### Pré-condições

- O usuário deve estar autenticado.
- O usuário deve estar na página de listagem de filmes.

### Fluxo Principal

1. O usuário seleciona a opção **"Cadastrar Filme"**.
2. O sistema apresenta o formulário de cadastro.
3. O usuário informa os dados do filme.
4. O usuário confirma o cadastro.
5. O sistema valida os dados informados.
6. O sistema cadastra o filme.
7. O sistema calcula automaticamente o status do filme com base na data de lançamento.
8. O sistema apresenta uma mensagem de sucesso.
9. O sistema atualiza a listagem de filmes.

### Fluxos Alternativos

#### A1. Um ou mais campos obrigatórios não foram informados

- O sistema informa que os campos obrigatórios devem ser preenchidos.
- O usuário corrige os dados.
- O fluxo retorna ao passo 3.

#### A2. O filme já está cadastrado

- O sistema informa que o filme já existe.
- O usuário corrige os dados.
- O fluxo retorna ao passo 3.

### Pós-condições

- O filme foi cadastrado com sucesso.
- O filme está associado ao usuário autenticado.
- O status do filme foi definido automaticamente.

### Requisitos Relacionados

- RF03
- RN02
- RN05
- RN06
- RN10

---

# UC-007 — Visualizar Detalhes do Filme

### Objetivo

Permitir que um usuário autenticado visualize as informações detalhadas de um filme cadastrado por ele.

### Atores

- Usuário

### Gatilho

O usuário seleciona um filme na listagem.

### Pré-condições

- O usuário deve estar autenticado.
- O usuário deve estar na página de listagem de filmes.

### Fluxo Principal

1. O usuário seleciona um filme da listagem.
2. O sistema identifica o filme selecionado.
3. O sistema recupera as informações do filme.
4. O sistema apresenta os detalhes do filme ao usuário.

### Fluxos Alternativos

#### A1. O filme não foi encontrado

- O sistema informa que o filme não foi encontrado.
- O sistema retorna o usuário à listagem de filmes.

#### A2. O usuário tenta acessar um filme que não lhe pertence

- O sistema nega o acesso.
- O sistema informa que o filme não foi encontrado ou que o acesso é inválido.

### Pós-condições

- Os detalhes do filme foram apresentados ao usuário.

### Requisitos Relacionados

- RF09
- RN02
- RN03
- RN10

---# UC-008 — Editar Filme

### Objetivo

Permitir que um usuário autenticado edite um filme cadastrado por ele.

### Atores

- Usuário

### Gatilho

O usuário seleciona a opção **"Editar"**.

### Pré-condições

- O usuário deve estar autenticado.
- O usuário deve estar na página de detalhes do filme.

### Fluxo Principal

1. O usuário seleciona a opção **"Editar"**.
2. O sistema apresenta o formulário de edição preenchido com os dados atuais do filme.
3. O usuário altera as informações desejadas.
4. O usuário confirma a edição.
5. O sistema valida os dados informados.
6. O sistema atualiza os dados do filme.
7. O sistema confirma a edição ao usuário.
8. O sistema apresenta novamente os detalhes do filme atualizados.

### Fluxos Alternativos

#### A1. O usuário tenta editar um filme que não lhe pertence

- O sistema informa que o usuário não possui permissão para editar o filme.

#### A2. O usuário informa dados inválidos

- O sistema informa os erros de validação.
- O usuário corrige os dados.
- O fluxo retorna ao passo 3.

### Pós-condições

- Os dados do filme foram atualizados com sucesso.

### Requisitos Relacionados

- RF04
- RF09
- RN02
- RN03
- RN10

---

# UC-009 — Excluir Filme

### Objetivo

Permitir que um usuário autenticado exclua um filme cadastrado por ele.

### Atores

- Usuário

### Gatilho

O usuário seleciona a opção **"Excluir"**.

### Pré-condições

- O usuário deve estar autenticado.
- O usuário deve estar na página de detalhes do filme.

### Fluxo Principal

1. O usuário seleciona a opção **"Excluir"**.
2. O sistema solicita a confirmação da exclusão.
3. O usuário confirma a exclusão.
4. O sistema exclui o filme.
5. O sistema informa que o filme foi excluído com sucesso.
6. O sistema apresenta novamente a listagem de filmes.

### Fluxos Alternativos

#### A1. O usuário tenta excluir um filme que não lhe pertence

- O sistema informa que o usuário não possui permissão para excluir o filme.

#### A2. O usuário cancela a exclusão

- O sistema cancela a operação.
- O sistema retorna à página de detalhes do filme.

### Pós-condições

- O filme foi excluído com sucesso.
- O filme deixa de fazer parte da coleção do usuário.

### Requisitos Relacionados

- RF05
- RF09
- RN02
- RN03
- RN10

---

# UC-010 — Fazer Logout

## Objetivo

Permitir que um usuário autenticado encerre sua sessão no sistema.

## Atores

- Usuário

## Gatilho

O usuário seleciona a opção **"Logout"**.

## Pré-condições

- O usuário deve estar autenticado.

## Fluxo Principal

1. O usuário seleciona a opção **"Logout"**.
2. O sistema encerra a sessão do usuário.
3. O sistema remove as credenciais de autenticação.
4. O sistema redireciona o usuário para a tela de login.

## Fluxos Alternativos

Não existem fluxos alternativos para este caso de uso.

## Pós-condições

- A sessão do usuário foi encerrada.
- O usuário não possui mais acesso às funcionalidades protegidas até realizar um novo login.

## Requisitos Relacionados

- RF13

---

# Status

☑ Elaborado

☑ Validado pelo Cliente

☑ Aprovado para Detalhamento

---

## Histórico de Versões

| Versão | Data       | Alteração                                                                | Responsável |
| ------ | ---------- | ------------------------------------------------------------------------ | ----------- |
| 1.0    | 03/08/2026 | Criação do documento de Casos de Uso.                                    | Raphael     |
| 1.1    | 03/08/2026 | Revisão textual, padronização da estrutura e correções de consistência.  | Raphael     |
| 1.2    | 03/08/2026 | Documento validado e aprovado para detalhamento da modelagem do domínio. | Raphael     |
