# Especificação de Requisitos

**Versão:** 1.1

**Data:** 01/08/2026

**Status:** Elaborado

**Participantes:**

- Cliente
- Analista de Sistemas

---

## Objetivo

Desenvolver uma aplicação web que permita aos usuários gerenciar sua coleção pessoal de filmes de forma simples, intuitiva e segura.

---

## Usuários do Sistema

- Usuário

---

## Problemas Identificados

- Não existe uma forma centralizada para organizar e gerenciar uma coleção pessoal de filmes.
- À medida que a quantidade de filmes aumenta, torna-se mais difícil localizar um filme específico.
- Não há mecanismos de busca e filtros que facilitem a localização de filmes.
- Não existe um controle sobre filmes com lançamento futuro.
- O usuário não recebe lembretes sobre a estreia dos filmes cadastrados.
- Não há controle de acesso que garanta que cada usuário visualize e gerencie apenas os próprios filmes.

---

## Requisitos Funcionais

- **RF01** - Permitir o cadastro de usuários.
- **RF02** - Permitir a autenticação de usuários.
- **RF03** - Permitir o cadastro de filmes.
- **RF04** - Permitir a edição de filmes.
- **RF05** - Permitir a exclusão de filmes.
- **RF06** - Permitir a listagem de filmes.
- **RF07** - Permitir a pesquisa de filmes.
- **RF08** - Permitir a filtragem de filmes.
- **RF09** - Permitir a visualização dos detalhes de um filme.
- **RF10** - Enviar e-mail de lembrete para filmes com data de lançamento futura.
- **RF11** - Permitir a alternância entre os temas claro e escuro.
- **RF12** - Permitir o upload da imagem do filme.

---

## Requisitos Não Funcionais

- **RNF01** - A aplicação deve ser desenvolvida em TypeScript.
- **RNF02** - O banco de dados deve ser PostgreSQL.
- **RNF03** - As imagens dos filmes devem ser armazenadas em um serviço de armazenamento em nuvem.
- **RNF04** - A interface deve ser responsiva.
- **RNF05** - A aplicação deve oferecer suporte aos temas claro e escuro.
- **RNF06** - A listagem de filmes deve ser paginada, exibindo até 10 itens por página.

---

## Regras de Negócio

- **RN01** - O e-mail do usuário deve ser único.
- **RN02** - Cada filme pertence a um único usuário.
- **RN03** - Um usuário pode visualizar, editar e excluir apenas os filmes cadastrados por ele.
- **RN04** - O status do filme deve ser calculado automaticamente com base na data de lançamento.
- **RN05** - Filmes com data de lançamento futura devem gerar um lembrete por e-mail na data da estreia.
- **RN06** - O slug do filme deve ser único.
- **RN07** - A pesquisa de filmes deve considerar, no mínimo, o título do filme.
- **RN08** - Os filtros obrigatórios são duração e período de lançamento.
- **RN09** - Deve existir pelo menos um filtro adicional.
- **RN10** - Apenas usuários autenticados podem acessar a área de gerenciamento de filmes.
- **RN11** - A imagem enviada deve estar associada a um único filme.

---

## Dúvidas para o Cliente

No momento, não existem dúvidas bloqueantes para o detalhamento dos casos de uso.

Novas dúvidas poderão ser registradas durante o refinamento dos requisitos ou da implementação.

---

Status

☑ Elaborado

☑ Validado pelo Cliente

☐ Aprovado para Detalhamento

---

## Histórico de Versões

| Versão | Data       | Alteração                                    | Responsável |
| ------ | ---------- | -------------------------------------------- | ----------- |
| 1.0    | 01/08/2026 | Criação da Especificação de Requisitos.      | Raphael     |
| 1.1    | 01/08/2026 | Ajustes após revisão e validação do cliente. | Raphael     |
