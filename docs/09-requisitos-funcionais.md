# 09 — Requisitos funcionais

> Projeto Acompanha (TIAPN, PUC Minas Contagem). O que o sistema deve fazer, com prioridade e origem de cada requisito. Índice geral: [README](../README.md).

| ID | Descrição | Prioridade | Origem |
|---|---|---|---|
| RF01 | Cadastrar, editar e consultar alunos (nome, data de nascimento, ano escolar, matérias acompanhadas). | Alta | P1 |
| RF02 | Cadastrar responsáveis e vinculá-los a alunos: um aluno pode ter um ou mais responsáveis, e um responsável pode ter um ou mais alunos. | Alta | P1, P4, P5 |
| RF03 | Registrar o consentimento do responsável (data, forma de coleta e versão do termo). O aluno só fica ativo com consentimento registrado (RN08). | Alta | P6, LGPD |
| RF04 | Cadastrar as matérias acompanhadas pela escolinha. | Alta | P1 |
| RF05 | Registrar aula: data, aluno, professora, presença (presente/falta), matérias e conteúdos trabalhados e observação. | Alta | P2, HU03 |
| RF06 | Criar tarefa de casa vinculada a aluno e matéria, com descrição, data de atribuição e prazo. | Alta | P2, HU05 |
| RF07 | Atualizar o status da tarefa (Pendente, Entregue no prazo, Entregue com atraso, Não entregue), exclusivamente pela professora (RN06). | Alta | P2 |
| RF08 | Permitir ao responsável sinalizar "meu filho fez a tarefa"; o aviso aparece no painel da professora e não altera o status. | Baixa | P3, HU13 |
| RF09 | Registrar avaliação: aluno, matéria, data, descrição e nota de 0 a 10 (RN01). | Alta | P2, HU06 |
| RF10 | Sinalizar necessidade de reforço por matéria de forma automática (RN04) e manual (com motivo), permitindo que a professora desmarque (RN05). | Alta | P1, P2, HU07 |
| RF11 | Exibir painel de pendências: tarefas atrasadas, tarefas que vencem em até 3 dias, alunos sinalizados para reforço e avisos de responsáveis. | Alta | P1, HU01 |
| RF12 | Exibir histórico por aluno em ordem cronológica (aulas, presença, tarefas, avaliações e sinalizações), com filtro por matéria e período. | Alta | P1, P2, HU02, HU04 |
| RF13 | Exibir relatório de progresso somente leitura com o conteúdo definido em "Conteúdo do relatório de progresso", abaixo. | Alta | P3, P4, P5, HU08 |
| RF14 | Autenticar usuários por e-mail ou telefone e senha; a professora pode redefinir a senha de um responsável. | Alta | Todos |
| RF15 | Autorizar o acesso por papel (professora ou responsável) e por vínculo: o responsável só acessa alunos vinculados a ele (RN07). | Alta | P4, P6, LGPD |
| RF16 | Encerrar matrícula: bloqueia na hora o acesso dos responsáveis ao aluno e agenda a eliminação dos dados (RN09). | Alta | P1, LGPD |
| RF17 | Eliminar ou anonimizar os dados de um aluno ao fim do prazo de guarda ou a pedido do responsável (RN10). | Média | P6, LGPD |
| RF18 | Exibir página de privacidade em linguagem simples: dados coletados, finalidade, quem acessa, prazo de guarda e como pedir exclusão. | Média | P6, LGPD |
| RF19 | Desvincular um responsável de um aluno (ex.: mudança de guarda), com registro de data e motivo. | Média | P4 |

## Conteúdo do relatório de progresso (RF13)

- **Identificação:** nome do aluno, ano escolar e período do relatório (mês ou bimestre, escolhido pela professora).
- **Frequência:** aulas com presença sobre aulas registradas no período, em número e porcentagem.
- **Desempenho por matéria:** notas das avaliações do período, média da matéria (RN02) e situação ("Em dia" ou "Precisa de atenção", conforme RN04).
- **Conteúdos trabalhados:** lista resumida dos conteúdos registrados nas aulas, por matéria.
- **Tarefas:** quantidade atribuída, entregues no prazo, entregues com atraso, não entregues e pendentes, além da taxa de entrega no prazo.
- **Observação da professora:** texto livre, de caráter pedagógico, visível para o responsável.
