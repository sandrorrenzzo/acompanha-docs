### Processo 1 TO BE – Provas e trabalhos do colégio

A prova ou o trabalho é cadastrado com a data assim que a professora fica sabendo, ainda sem nota, e aparece no painel nos 7 dias anteriores e na visão da semana do responsável. Depois da data, a professora lança a nota, que entra na média das 3 notas mais recentes da matéria; se a média ficar abaixo de 6,0, o sistema sinaliza reforço na matéria.

O modelo está em [01-provas-e-trabalhos-to-be.bpmn](../bpmn/01-provas-e-trabalhos-to-be.bpmn), em BPMN 2.0 no formato do bpmn.io. Para abrir ou editar, arraste o arquivo para o [demo.bpmn.io](https://demo.bpmn.io) ou abra no Camunda Modeler.

Participam do processo a professora e o Sistema Acompanha.

#### Fluxo

1. A professora fica sabendo de uma prova ou de um trabalho, pelo aluno ou pela família.
2. Cadastra a prova ou o trabalho com matéria, origem e data, sem nota.
3. O sistema mostra o item no painel de pendências da professora e na visão da semana do responsável.
4. A professora ajuda o aluno a se preparar.
5. Chega a data da prova ou da entrega.
6. A professora corrige ou recebe a nota do colégio e lança a nota no sistema.
7. O sistema salva a nota, recalcula a média da matéria e sinaliza reforço se a média ficar abaixo de 6,0. O processo termina com a **nota registrada**.

#### Detalhamento das atividades

**Cadastra com matéria, origem e data, sem nota** (tarefa de usuário, professora)

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Aluno | Seleção única | Obrigatório; só alunos ativos | |
| Tipo | Seleção única | Obrigatório; Prova ou Trabalho | |
| Matéria | Seleção única | Obrigatório; matérias acompanhadas pelo aluno | |
| Origem | Seleção única | Obrigatório; Colégio ou Reforço | |
| Data | Data | Obrigatório; data da prova ou da entrega | |
| Descrição | Caixa de texto | Obrigatório | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Salvar | Mostra no painel e na semana do responsável | default |
| Cancelar | Fim do processo, sem cadastro | cancel |

**Mostra no painel e na semana do responsável** (tarefa de serviço)

O item aparece no painel de pendências, na categoria de provas e trabalhos dos próximos 7 dias. Também aparece na visão da semana do responsável vinculado ao aluno quando a data cai na semana atual.

**Ajuda o aluno a se preparar** e **Corrige ou recebe a nota do colégio** (tarefas manuais)

Feitas fora do sistema, na aula.

**Lança a nota** (tarefa de usuário, professora)

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Nota | Número | Obrigatório; de 0,0 a 10,0, com uma casa decimal | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Salvar | Salva a nota e recalcula a média da matéria | default |
| Cancelar | O item continua sem nota | cancel |

**Salva a nota e recalcula a média da matéria** (tarefa de serviço)

A média da matéria é a média aritmética das notas das 3 provas ou trabalhos mais recentes do aluno naquela matéria, do colégio ou do reforço (ou de todas, se houver menos de 3). A avaliação diagnóstica não entra na média.

**Sinaliza reforço se a média ficar abaixo de 6,0** (tarefa de serviço)

Se a média da matéria ficar abaixo de 6,0, com pelo menos 2 notas, o aluno passa a ser sinalizado para reforço na matéria, e a sinalização aparece no painel de pendências. A sinalização automática sai sozinha quando a média volta a 6,0 ou mais. O limite de 6,0 é configurável.
