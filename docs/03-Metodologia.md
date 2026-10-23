
# Metodologia

<span style="color:red">Pré-requisitos: <a href="02-Especificacao.md"> Especificação do projeto</a></span>

Esta seção descreve como o grupo se organiza para desenvolver o Acompanha: o controle de versão, a divisão de papéis e tarefas em cada sprint, o processo de trabalho e as ferramentas usadas.

## Controle de versão

A ferramenta de controle de versão adotada no projeto foi o [Git](https://git-scm.com/), sendo que o [GitHub](https://github.com) foi utilizado para hospedagem do repositório.

O projeto segue a seguinte convenção para o nome de branches:

- `main`: versão estável já testada do software
- `unstable`: versão já testada do software, porém instável
- `testing`: versão em testes do software
- `dev`: versão de desenvolvimento do software

Quanto à gerência de issues, o projeto adota a seguinte convenção para etiquetas:

- `documentation`: melhorias ou acréscimos à documentação
- `bug`: uma funcionalidade encontra-se com problemas
- `enhancement`: uma funcionalidade precisa ser melhorada
- `feature`: uma nova funcionalidade precisa ser introduzida

Discuta como a configuração do projeto foi feita na ferramenta de versionamento escolhida. Exponha como a gestão de tags, merges, commits e branches é realizada. Discuta também como a gestão de issues foi feita.

> **Links úteis**:
> - [Tutorial GitHub](https://guides.github.com/activities/hello-world/)
> - [Git e GitHub](https://www.youtube.com/playlist?list=PLHz_AreHm4dm7ZULPAmadvNhH6vk9oNZA)
> - [Comparando fluxos de trabalho](https://www.atlassian.com/br/git/tutorials/comparing-workflows)
> - [Understanding the GitHub flow](https://guides.github.com/introduction/flow/)
> - [The gitflow workflow - in less than 5 mins](https://www.youtube.com/watch?v=1SXpE08hvGs)

## Planejamento do projeto

### Divisão de papéis

#### Sprint 1
- _Scrum master_ e revisão final: Sandro Renzzo Silva Rocha
- Entrevistas e personas: Janio Junio de Freitas Cardoso
- Histórias de usuário e requisitos funcionais: Lucas Henrique Pereira Silva
- Regras de negócio, requisitos não funcionais e restrições: Tiago Calazans Cruz
- Justificativa: Heitor Habaeb Moreira
- Público-alvo: Gustavo Victor de Paula

#### Sprint 2
- _Scrum master_, apresentação e revisão final: Sandro Renzzo Silva Rocha
- Modelagem do processo de provas e trabalhos: Heitor Habaeb Moreira
- Modelagem do processo de consulta do progresso: Gustavo Victor de Paula
- Entrevistas e personas: Janio Junio de Freitas Cardoso
- Histórias de usuário e requisitos funcionais: Lucas Henrique Pereira Silva
- Regras de negócio, requisitos não funcionais e dados pessoais: Tiago Calazans Cruz

### Quadro de tarefas

#### Sprint 1

Atualizado em: 23/10/2026

| Responsável | Tarefa/Requisito | Status |
| :---- | :---- | :----: |
| Sandro | Cliente, problema e objetivos | ✔️ |
| Sandro | Coordenação e revisão final | ✔️ |
| Janio | Entrevistas com as professoras e as mães | ✔️ |
| Janio | Personas | ✔️ |
| Lucas | Histórias de usuário | ✔️ |
| Lucas | Requisitos funcionais | ✔️ |
| Tiago | Regras de negócio, requisitos não funcionais e restrições | ✔️ |
| Heitor | Justificativa | ✔️ |
| Gustavo | Público-alvo | ✔️ |

#### Sprint 2

Atualizado em: 23/10/2026

| Responsável | Tarefa/Requisito | Status |
| :---- | :---- | :----: |
| Sandro | Apresentação do projeto | ✔️ |
| Sandro | Tabela dos processos de negócio da escolinha | ✔️ |
| Sandro | Coordenação da revisão final | ✔️ |
| Heitor | Diagramas de provas e trabalhos do colégio (AS-IS e TO-BE) e seção correspondente | ✔️ |
| Gustavo | Diagramas da consulta do progresso pelo responsável (AS-IS e TO-BE) | ✔️ |
| Gustavo | Convenções de notação | ✔️ |
| Janio | Condução das entrevistas | ✔️ |
| Janio | Personas das professoras e das mães | ✔️ |
| Lucas | Histórias de usuário e requisitos funcionais | ✔️ |
| Tiago | Regras de negócio e requisitos não funcionais | ✔️ |
| Tiago | Restrições de escopo e tratamento de dados pessoais | ✔️ |

Legenda:
- ✔️: terminado
- 📝: em execução
- ⌛: atrasado
- ❌: não iniciado

### Processo

O grupo segue as sprints definidas pela disciplina. No início de cada sprint, as seções da documentação são divididas entre os integrantes, e cada um fica responsável por escrever e revisar a própria parte. Antes da entrega, o _Scrum master_ faz a revisão final de todos os documentos para manter a coerência entre eles e envia a versão revisada ao repositório.

As regras de negócio e as personas são validadas com a parceira, Ieronides Gonçalves da Silva Santos, *Product Owner* da Divertindo a Mente.

## Ferramentas

| Ambiente | Plataforma | Link de acesso |
| --- | --- | --- |
| Repositório de código-fonte e documentação | GitHub (organização da PUC Minas) | A definir |
| Projeto de interface | Figma | [Acompanha – Protótipo](https://www.figma.com/design/KjtSsah133BDvt0Nvc8JpL/Acompanha---Prot%C3%B3tipo?node-id=11-709) |
| Modelagem de processos (BPMN) | bpmn.io | [demo.bpmn.io](https://demo.bpmn.io) |
| Diagrama entidade-relacionamento | draw.io | [app.diagrams.net](https://app.diagrams.net) |
| Hospedagem | A definir | — |

Tecnologias previstas para a aplicação, conforme a <a href="07-Arquitetura-solucao.md">Arquitetura da solução</a>:

| Camada | Tecnologia |
| --- | --- |
| Front-end | React |
| Back-end (API REST) | C# com ASP.NET Core |
| Banco de dados | PostgreSQL |
