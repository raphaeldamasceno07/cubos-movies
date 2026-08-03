# Entendimento do Problema

**Versão:** 1.2

**Data da reunião:** 01/08/2026

**Status:** Aprovado para Detalhamento

**Participantes:**

- Cliente
- Analista de Sistemas

## Objetivo do Sistema

Desenvolver uma aplicação web que permita aos usuários gerenciar sua coleção pessoal de filmes de forma simples, intuitiva e segura.

O sistema deve possibilitar o cadastro, consulta, atualização e remoção de filmes, além de oferecer mecanismos de busca, filtragem e visualização detalhada das informações cadastradas.

Também deve notificar o usuário quando um filme com data de lançamento futura atingir sua data de estreia.

## Problema de Negócio

Atualmente, os usuários não possuem uma forma centralizada para organizar e gerenciar sua coleção pessoal de filmes.

À medida que a quantidade de filmes cadastrados aumenta, torna-se mais difícil localizar informações específicas e acompanhar lançamentos futuros.

Dessa forma, surge a necessidade de uma aplicação que permita armazenar, pesquisar, filtrar e gerenciar filmes de maneira organizada, além de notificar o usuário quando um filme ainda não lançado atingir sua data de estreia, garantindo que cada usuário tenha acesso apenas aos próprios filmes.

## Atores

### Usuário

Pessoa responsável por utilizar o sistema para gerenciar sua coleção pessoal de filmes.

Suas responsabilidades incluem:

- Criar uma conta.
- Autenticar-se no sistema.
- Cadastrar filmes.
- Consultar sua lista de filmes.
- Pesquisar e filtrar filmes.
- Visualizar detalhes de um filme.
- Editar filmes cadastrados por ele.
- Excluir filmes cadastrados por ele.

## Escopo

O sistema tem como objetivo permitir que usuários autenticados gerenciem sua própria coleção de filmes.

O escopo contempla:

- Cadastro de usuários.
- Autenticação de usuários.
- Logout.
- Cadastro de filmes.
- Edição de filmes.
- Exclusão de filmes.
- Listagem de filmes.
- Busca de filmes.
- Filtragem de filmes.
- Paginação da listagem.
- Visualização dos detalhes de um filme.
- Armazenamento da imagem do filme em serviço de armazenamento em nuvem.
- Envio de e-mail para filmes com lançamento futuro.
- Alternância entre tema claro e escuro.

Não fazem parte do escopo:

- Compartilhamento de filmes entre usuários.
- Avaliações e comentários.
- Favoritos.
- Perfis de administrador.
- Integração com APIs externas de filmes.

## Funcionalidades Identificadas

### Autenticação

- Permitir cadastro de novos usuários.
- Permitir autenticação de usuários.
- Redirecionar usuários autenticados para a listagem de filmes.
- Restringir acesso de usuários não autenticados.

### Gerenciamento de Filmes

- Cadastrar um filme.
- Editar um filme.
- Excluir um filme.
- Listar filmes cadastrados.
- Visualizar detalhes de um filme.

### Pesquisa e Filtros

- Pesquisar filmes por texto.
- Filtrar filmes por duração.
- Filtrar filmes por período de lançamento.
- Filtrar filmes por um critério adicional (ex.: gênero).

### Notificações

- Enviar um e-mail ao usuário quando um filme com lançamento futuro atingir sua data de estreia.

## Premissas

- Cada usuário gerencia apenas os filmes cadastrados por ele.
- Apenas usuários autenticados podem acessar o sistema.
- Um filme pertence a um único usuário.
- O sistema determina automaticamente se um filme já foi lançado com base na data de lançamento.
- Caso a data de lançamento seja futura, um e-mail deverá ser enviado ao usuário na data da estreia.
- A busca e os filtros devem facilitar a localização de filmes na coleção do usuário.
- O usuário não informa manualmente o status do filme.

## Dúvidas em Aberto

No momento, não existem dúvidas bloqueantes para o início da modelagem do sistema.

Novas dúvidas poderão surgir durante o refinamento dos casos de uso ou da implementação e serão registradas conforme necessário.

---

## Aprovações

☑ Elaborado

☑ Validado pelo Cliente

☑ Aprovado para Detalhamento

# Histórico de versões

| Versão | Data       | Alteração                             | Responsável |
| ------ | ---------- | ------------------------------------- | ----------- |
| 1.0    | 01/08/2026 | Criação do documento.                 | Raphael     |
| 1.1    | 01/08/2026 | Ajustes após revisão do cliente.      | Raphael     |
| 1.2    | 01/08/2026 | Documento aprovado para detalhamento. | Raphael     |
