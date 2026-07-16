# CLAUDE.md

Instruções de projeto que o Claude lê no início de cada sessão.

## Sobre o projeto

<!-- Descreva aqui o objetivo do projeto HabilitacaoSdd, stack utilizada e contexto de negócio. -->

## Convenções

<!-- Padrões de código, nomenclatura, estrutura de pastas, etc. -->

## Comandos comuns

<!-- Build, testes, lint, execução local, etc. -->

## Arquitetura

<!-- Decisões arquiteturais relevantes que o Claude deve conhecer. -->

---

## Spec-Driven Development (Spec Kit)

Este projeto usa o [GitHub Spec Kit](https://github.com/github/spec-kit) para Spec-Driven Development. A fonte de verdade sobre princípios do projeto é `.specify/memory/constitution.md` — **não** este arquivo.

**Regra geral**: nenhuma alteração de comportamento deve ser implementada sem uma spec correspondente em `specs/`. Se a feature não tem spec, criar uma antes de codar.

Fluxo obrigatório para qualquer alteração de código não trivial:

1. `/speckit-specify` — cria a especificação da funcionalidade em `specs/<nome>/spec.md`.
2. `/speckit-clarify` (opcional, recomendado quando houver ambiguidade) — resolve pontos em aberto antes de planejar.
3. `/speckit-plan` — gera o plano técnico.
4. `/speckit-tasks` — gera a lista de tarefas acionáveis.
5. `/speckit-implement` — executa a implementação.
6. `/speckit-converge` — confere o código contra spec/plan/tasks e lista pendências.

Para mudanças puramente mecânicas (typo, formatação, renomeação interna sem mudança de comportamento observável), o fluxo completo não é necessário — mas o comportamento preservado deve ser demonstrável pelos testes existentes.

**Pendência**: `.specify/memory/constitution.md` ainda está com os placeholders do template padrão. Rodar `/speckit-constitution` antes da primeira feature para definir os princípios reais do projeto.
