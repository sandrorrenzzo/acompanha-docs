# Modelagem dos processos de negócio

<span style="color:red">Pré-requisitos: <a href="02-Especificacao.md"> Especificação do projeto</a></span>

Modelagem AS-IS (como é feito hoje) e TO-BE (como será com o Acompanha) dos dois processos com os problemas mais evidentes da escolinha.

Os diagramas estão na pasta [bpmn](bpmn/), em BPMN 2.0 no formato do bpmn.io. Para abrir ou editar, arraste o arquivo `.bpmn` para o [demo.bpmn.io](https://demo.bpmn.io) ou abra no Camunda Modeler.

### Convenções

- Cada processo é uma piscina, com raias para Professora, Responsável, Aluno (só no AS-IS) e Sistema Acompanha.
- Tarefa de usuário (ícone de pessoa): feita no sistema. Tarefa manual (ícone de mão): feita fora do sistema. Tarefa de serviço (engrenagem): feita automaticamente pelo sistema.
- Evento de timer: momento previsto (dia da prova, fim da aula ou do dia, fim do mês ou do bimestre).
- Desvio (losango com X): decisão com critério escrito no rótulo.
- Os diagramas mostram o processo de negócio; detalhes de tela (login, escolha do aluno) e casos de exceção (prova fora do cronograma, nota que não chega) ficam só no detalhamento de cada processo.

## Modelagem da situação atual (Modelagem AS IS)

O AS-IS foi montado a partir das entrevistas com as duas professoras e da conversa com a proprietária. Hoje não existe acompanhamento pedagógico registrado: a planilha no Drive é usada só para o controle financeiro, e a tentativa de anotar aulas, tarefas e notas nela foi abandonada por falta de tempo. Por isso não há como medir quanto tempo o sistema economiza; o ganho está em passar a ter um registro que hoje não existe. Na aula, que tem demanda bastante corrida, o foco é ajudar nas atividades, trabalhos e estudos do colégio. Quando a professora percebe uma dificuldade, avisa o responsável de boca.

- **Provas e trabalhos do colégio:** o cronograma de provas fica impresso na parede da escolinha, e o que está fora dele depende de aviso; se ninguém avisa, o aluno faz a prova ou o trabalho sem a ajuda do reforço; a nota não é registrada, e quando a nota é ruim a professora conversa com os pais, sem critério nem histórico.
- **Consulta do progresso pelo responsável:** os pedidos de notícias são diários, e a professora responde de memória, muitas vezes só no fim da aula ou do dia.

## Descrição geral da proposta (Modelagem TO BE)

Com o Acompanha, o cronograma de provas é cadastrado no sistema em vez de pregado na parede, e aparece no painel da professora e na semana do responsável. A nota é lançada e comparada com o que a escola do aluno considera suficiente (por pontos ou por conceito); abaixo do esperado, o sistema sinaliza reforço, e a professora conversa com os pais e passa atividades de reforço registradas. O responsável passa a consultar sozinho, a qualquer hora, a semana e o relatório de progresso dos próprios filhos, sem depender da memória da professora.

A proposta cobre os processos de negócio abaixo:

| Processo | Quem executa | Observação |
|---|---|---|
| Cadastro do aluno e coleta do consentimento | Professora + responsável | O aluno só fica ativo depois que o consentimento do responsável é registrado. |
| Cadastro e vinculação do responsável | Professora | Cada aluno tem um único responsável com acesso, e um responsável com mais de um filho usa um único login. |
| Registro de aula e presença | Professora | Base para frequência e para a continuidade do conteúdo entre as aulas. |
| Gestão de tarefas (do colégio e do reforço) | Professora (responsável pode avisar que foi feita) | Só a professora registra tarefas e muda o status delas. |
| Registro de provas e trabalhos (do colégio e do reforço) | Professora | Cadastrados antes da data para aparecer no painel; depois da data ficam como nota pendente; nota em pontos sobre o valor da prova ou em conceito, conforme a escola do aluno, ou "sem nota" após 30 dias. |
| Identificação e acompanhamento de reforço | Sistema + professora | Avaliação diagnóstica, regra automática de reforço (prova abaixo do esperado pela escola do aluno) e marcação manual; com a sinalização, a professora passa atividades de reforço registradas como tarefas. |
| Consulta do progresso | Responsável | Visão da semana e relatório do período, somente leitura e só dos alunos vinculados a ele. |
| Encerramento de matrícula e eliminação de dados | Professora + sistema | No encerramento, bloqueio imediato e eliminação dos dados após 6 meses; a pedido do responsável, bloqueio no mesmo dia e eliminação em até 15 dias. |

O que fica fora da solução está listado em [fora do escopo](02-Especificacao.md#fora-do-escopo).

## Modelagem dos processos

[PROCESSO 1 AS IS - Provas e trabalhos do colégio](./processes/processo-1-as-is.md "Detalhamento do processo 1 AS IS.")

[PROCESSO 1 TO BE - Provas e trabalhos do colégio](./processes/processo-1-to-be.md "Detalhamento do processo 1 TO BE.")

[PROCESSO 2 AS IS - Consulta do progresso pelo responsável](./processes/processo-2-as-is.md "Detalhamento do processo 2 AS IS.")

[PROCESSO 2 TO BE - Consulta do progresso pelo responsável](./processes/processo-2-to-be.md "Detalhamento do processo 2 TO BE.")

## Indicadores de desempenho

Os indicadores usam apenas dados que o sistema já registra nos dois processos e no relatório de progresso. Todas as informações necessárias para gerá-los devem estar no diagrama de classes.

| **Indicador** | **Objetivos** | **Descrição** | **Fonte de dados** | **Fórmula de cálculo** |
| --- | --- | --- | --- | --- |
| Provas e trabalhos cadastrados com antecedência | Garantir que a professora saiba das provas e trabalhos a tempo de preparar o aluno (processo 1) | Percentual de provas e trabalhos cadastrados antes da data, no período | Provas e trabalhos; registro de alterações | (provas e trabalhos cadastrados antes da data / total de provas e trabalhos do período) * 100 |
| Provas e trabalhos com nota lançada | Garantir que o resultado fique registrado (processo 1) | Percentual de provas e trabalhos já realizados que têm nota | Provas e trabalhos | (provas e trabalhos com data passada e com nota / provas e trabalhos com data passada) * 100 |
| Matérias sinalizadas para reforço | Acompanhar quantos alunos precisam de reforço (processo 1) | Percentual de matérias acompanhadas com sinalização de reforço ativa, automática ou manual | Matérias do aluno; sinalizações de reforço | (matérias com sinalização ativa / total de matérias acompanhadas) * 100 |
| Taxa de entrega de tarefas no prazo | Medir o cumprimento das tarefas, como no relatório de progresso | Percentual de tarefas entregues no prazo, no período | Tarefas | (tarefas com status Entregue no prazo / tarefas com prazo no período) * 100 |
| Frequência do aluno | Medir a presença nas aulas, como no relatório de progresso | Percentual de aulas com presença, no período | Aulas e presenças | (aulas com presença / aulas registradas no período) * 100 |
| Responsáveis que consultaram o sistema | Verificar se os responsáveis passaram a consultar sozinhos (processo 2) | Percentual de responsáveis com vínculo ativo que acessaram o sistema na semana | Responsáveis e vínculos; registro de acessos | (responsáveis que acessaram na semana / responsáveis com vínculo ativo) * 100 |
