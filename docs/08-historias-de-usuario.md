# 08 — Histórias de usuário

> Projeto Acompanha (TIAPN, PUC Minas Contagem). O que cada persona precisa fazer no sistema, com critério de aceitação. Índice geral: [README](../README.md).

| ID | História | Persona | RF | Critério de aceitação |
|---|---|---|---|---|
| HU01 | Como professora principal, quero ver ao abrir o sistema um painel com tarefas atrasadas, tarefas que vencem em até 3 dias e alunos sinalizados para reforço, para saber quem preciso olhar hoje. | P1 | RF11 | O painel lista as três categorias, com nome do aluno e matéria; cada item leva ao histórico do aluno. |
| HU02 | Como professora principal, quero consultar o histórico completo de um aluno (aulas, tarefas, notas e sinalizações) filtrando por matéria e período, para preparar a conversa com a família. | P1 | RF12 | O histórico aparece em ordem cronológica e o filtro por matéria/período funciona. |
| HU03 | Como professora, quero registrar a aula de um aluno com presença e matérias trabalhadas pelo celular, para manter o histórico do que foi ensinado. | P2 | RF05 | Registro concluído em até 2 minutos no celular, em teste com a professora. |
| HU04 | Como professora auxiliar, quero ver o que foi trabalhado na última aula do aluno antes de começar, para dar continuidade ao trabalho da outra professora. | P2 | RF12 | A última aula registrada aparece no topo do histórico, com professora e conteúdo. |
| HU05 | Como professora, quero atribuir uma tarefa de casa com matéria e prazo, para acompanhar se o aluno está cumprindo. | P2 | RF06 | Tarefa criada com status Pendente; passa a contar como atrasada no dia seguinte ao prazo (RN03). |
| HU06 | Como professora, quero registrar notas de 0 a 10 por matéria, para medir o desempenho do aluno. | P2 | RF09 | O sistema recusa notas fora de 0 a 10 e recalcula a média da matéria (RN02). |
| HU07 | Como professora, quero que o sistema sinalize automaticamente a necessidade de reforço e também poder marcar ou desmarcar manualmente, para não depender só da memória. | P1, P2 | RF10 | A sinalização segue a RN04; a marcação manual exige motivo e fica registrada no histórico. |
| HU08 | Como mãe, quero ver pelo celular um resumo do progresso do meu filho, para saber se preciso ajudar em casa. | P3 | RF13 | O resumo abre em tela de celular (360 px) sem rolagem horizontal e mostra tarefas pendentes no topo. |
| HU09 | Como pai com guarda compartilhada, quero ter meu próprio acesso ao progresso da minha filha, para não depender de outra pessoa. | P4 | RF02, RF15 | Dois responsáveis vinculados ao mesmo aluno veem o mesmo relatório, cada um com o seu login. |
| HU10 | Como avó responsável por dois netos, quero ver os dois com um único acesso e em linguagem simples, para acompanhar sem ajuda. | P5 | RF02, RF13 | Após o login aparece a lista dos alunos vinculados; a situação por matéria usa rótulos "Em dia" e "Precisa de atenção". |
| HU11 | Como mãe, quero saber quais dados do meu filho são coletados e para quê, e dar ou revogar meu consentimento, para decidir com segurança. | P6 | RF03, RF18 | O termo é exibido antes do primeiro acesso; o consentimento fica registrado com data e versão do termo. |
| HU12 | Como responsável, quero pedir a exclusão dos dados do meu filho quando ele sair da escolinha, para que não fiquem guardados sem necessidade. | P6 | RF16, RF17 | O pedido é atendido em até 15 dias (RN10) e o acesso é bloqueado no mesmo dia. |
| HU13 | Como responsável, quero avisar que meu filho fez a tarefa, para que a professora confira na próxima aula. | P3 | RF08 | O aviso aparece no painel da professora e não altera o status da tarefa (RN06). |
| HU14 | Como responsável, quero ver apenas os dados dos meus próprios filhos, para ter certeza de que ninguém vê os dados deles no meu lugar e vice-versa. | P4, P6 | RF15 | Tentar abrir o endereço de um aluno não vinculado resulta em acesso negado (teste automatizado). |
