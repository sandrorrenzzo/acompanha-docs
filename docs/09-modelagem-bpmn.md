# 09. Modelagem BPMN

Modelagem AS-IS (como é feito hoje) e TO-BE (como será com o Acompanha) dos dois processos com os problemas mais evidentes da escolinha.

Os diagramas estão na pasta [bpmn](bpmn/), em BPMN 2.0 no formato do bpmn.io. Para abrir ou editar, arraste o arquivo `.bpmn` para o [demo.bpmn.io](https://demo.bpmn.io) ou abra no Camunda Modeler.

O AS-IS foi montado a partir das entrevistas com as duas professoras e da conversa com a proprietária. Hoje não existe acompanhamento pedagógico registrado: a planilha no Drive é usada só para o controle financeiro, e a tentativa de anotar aulas, tarefas e notas nela foi abandonada por falta de tempo. Por isso não há como medir quanto tempo o sistema economiza; o ganho está em passar a ter um registro que hoje não existe. Na aula, que tem demanda bastante corrida, o foco é ajudar nas atividades, trabalhos e estudos do colégio. Quando a professora percebe uma dificuldade, avisa o responsável de boca.

## Convenções

- Cada processo é uma piscina, com raias para Professora, Responsável, Aluno (só no AS-IS) e Sistema Acompanha.
- Tarefa de usuário (ícone de pessoa): feita no sistema. Tarefa manual (ícone de mão): feita fora do sistema. Tarefa de serviço (engrenagem): feita automaticamente pelo sistema.
- Evento de timer: momento previsto (data da prova, fim do mês ou do bimestre).

## 1. Provas e trabalhos do colégio

- AS-IS: [01-provas-e-trabalhos-as-is.bpmn](bpmn/01-provas-e-trabalhos-as-is.bpmn)
- TO-BE: [01-provas-e-trabalhos-to-be.bpmn](bpmn/01-provas-e-trabalhos-to-be.bpmn)

Problemas hoje: se o aluno não avisa, a prova ou o trabalho passa sem preparação (já aconteceu com um trabalho de História de 10 pontos). A professora só sabe a nota se o aluno mostrar, não registra, e quando a nota é ruim apenas avisa o responsável de boca.

O que muda: a prova ou o trabalho é cadastrado com a data assim que a professora fica sabendo, ainda sem nota, e aparece no painel nos 7 dias anteriores e na visão da semana do responsável. Depois da data, a professora lança a nota, que entra na média das 3 notas mais recentes da matéria; se a média ficar abaixo de 6,0, o sistema sinaliza reforço na matéria.

## 2. Consulta do progresso pelo responsável

- AS-IS: [02-consulta-do-progresso-as-is.bpmn](bpmn/02-consulta-do-progresso-as-is.bpmn)
- TO-BE: [02-consulta-do-progresso-to-be.bpmn](bpmn/02-consulta-do-progresso-to-be.bpmn)

Problemas hoje: os responsáveis pedem notícias com frequência, a maioria todos os dias, e cada pedido toma tempo da professora, que responde de memória porque não há registro; o responsável só sabe o que perguntou, quando a professora consegue responder.

O que muda: o responsável consulta sozinho, a qualquer hora, apenas os alunos vinculados a ele. Primeiro aparece a visão da semana, com a última aula, as tarefas pendentes e as provas e trabalhos da semana. Se quiser, ele abre o relatório do mês ou do bimestre. A professora só escreve a observação pedagógica do período.
