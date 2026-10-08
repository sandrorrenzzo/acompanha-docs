### Processo 1 TO BE – Provas e trabalhos do colégio

O processo segue o mesmo caminho de hoje, mas o que hoje fica na parede e na memória passa a ficar no sistema. O cronograma é cadastrado em vez de pregado na parede, e assim aparece no painel da professora e na visão da semana do responsável. A nota é lançada em vez de só vista, e o sistema compara a nota com o que a escola do aluno considera suficiente, em vez da percepção de cada momento. Como os alunos vêm de escolas diferentes (provas de valores diferentes, trimestre ou bimestre, pontos ou conceito), a comparação usa a regra de cada escola, e não um número fixo. Nos dois casos a professora fala com os pais como já faz hoje, mas agora fica registrado: o elogio, quando o aluno vai bem, e as atividades de reforço, quando vai mal.

O modelo está em [01-provas-e-trabalhos-to-be.bpmn](../bpmn/01-provas-e-trabalhos-to-be.bpmn), em BPMN 2.0 no formato do bpmn.io. Para abrir ou editar, arraste o arquivo para o [demo.bpmn.io](https://demo.bpmn.io) ou abra no Camunda Modeler.

Participam do processo a professora, o aluno, o responsável e o Sistema Acompanha.

#### O que muda em relação a hoje

| **Hoje** | **Com o Acompanha** |
| --- | --- |
| Imprime e prega o cronograma na parede | Cadastra as provas no sistema, que mostra no painel e ao responsável |
| O aluno mostra a nota e ela não é anotada | A professora lança a nota e o sistema compara com o esperado pela escola |
| "A nota foi boa?" decidido de cabeça | "Abaixo do esperado pela escola?" decidido pelo sistema |
| Nota boa: parabeniza e segue a rotina | Registra o elogio, parabeniza o aluno e avisa os pais |
| Nota ruim: conversa com os pais, sem registro | Conversa com os pais e passa atividades de reforço registradas |

#### Fluxo

1. O aluno entra na escolinha.
2. A professora pede o cronograma de provas aos pais, no WhatsApp, e eles mandam.
3. A professora cadastra as provas no sistema. O sistema mostra cada prova no painel da professora, nos 7 dias anteriores à data, e na visão da semana do responsável.
4. A professora estuda com o aluno para a prova.
5. No dia da prova, o aluno faz a prova.
6. Quando recebe a nota, o aluno mostra à professora, que lança a nota. O sistema compara a nota com o esperado pela escola do aluno.
7. **A nota ficou abaixo do esperado pela escola?**
   - Se não, a professora registra o elogio no sistema, parabeniza o aluno e avisa os pais. O processo termina com os **pais avisados, com registro**.
   - Se sim, o sistema sinaliza reforço na matéria. A professora procura entender por que o aluno foi mal, conversa com os pais e passa atividades de reforço. O processo termina com o **aluno em reforço, com registro**.

#### Como o sistema decide "abaixo do esperado"

Cada escola é cadastrada uma vez, com o jeito que ela avalia, e cada aluno é vinculado à sua escola.

| **Escola avalia por** | **O que a professora lança** | **Abaixo do esperado quando** |
| --- | --- | --- |
| Pontos (ex.: trimestre 30-35-35 ou bimestre 25-25-25-25) | Pontos obtidos e quanto a prova valia (ex.: 18 de 30) | O aproveitamento (18 de 30 = 60%) fica abaixo da média que a escola exige (ex.: 70%) |
| Conceito (ex.: A, B, C, D, E, F) | O conceito | O conceito fica abaixo do mínimo da escola (ex.: abaixo de C) |

A divisão do ano em trimestres ou bimestres não entra na conta: cada prova é comparada pelo que ela própria valia. Basta uma prova abaixo do esperado para sinalizar reforço na matéria, como hoje basta uma nota ruim para a professora conversar com os pais.

#### Regras que completam o fluxo

Estes casos são tratados pelo sistema e não aparecem no diagrama, para mantê-lo simples:

- **Prova ou trabalho fora do cronograma** (passado durante o período ou com data alterada): quando a professora fica sabendo, pelo aluno ou pela família, cadastra da mesma forma.
- **Nota que não chega:** a partir do dia seguinte à data, a prova sem nota aparece no painel como nota pendente, para a professora pedir ao aluno ou à família. Depois de 30 dias, ela pode marcá-la como sem nota.
- **Saída do reforço:** a sinalização automática sai quando a próxima prova da matéria fica dentro do esperado. A sinalização manual, feita pela professora, só sai quando ela desmarca.
- **Escola sem regra cadastrada:** o sistema usa 60% para pontos; a professora pode ajustar quando souber a regra da escola (pode perguntar aos pais junto com o cronograma).

#### Detalhamento das atividades

**Pede o cronograma de provas no WhatsApp** (tarefa manual, professora) e **Manda o cronograma** (tarefa manual, responsável)

Como hoje.

**Cadastra as provas no sistema** (tarefa de usuário, professora)

Uma prova ou um trabalho por cadastro. A mesma tela serve para o que vier fora do cronograma.

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Aluno | Seleção única | Obrigatório; só alunos ativos | |
| Tipo | Seleção única | Obrigatório; Prova ou Trabalho | Prova |
| Matéria | Seleção única | Obrigatório; matérias acompanhadas pelo aluno | |
| Origem | Seleção única | Obrigatório; Colégio ou Reforço | Colégio |
| Data | Data | Obrigatório; data da prova ou da entrega | |
| Descrição | Caixa de texto | Obrigatório; o que o colégio pede para a prova | |
| Valor da prova | Número | Obrigatório se a escola do aluno avalia por pontos; maior que zero | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Salvar e cadastrar outra | Mesma tela, com aluno já preenchido | default |
| Salvar | Mostra no painel e ao responsável | |
| Cancelar | Fim, sem cadastro | cancel |

**Mostra no painel e ao responsável** (tarefa de serviço)

A prova aparece no painel de pendências, na categoria de provas e trabalhos dos próximos 7 dias, e na visão da semana do responsável quando a data cai na semana atual.

**Estuda com o aluno para a prova** (tarefa manual, professora)

Como hoje, com provas e atividades impressas por ela, agora guiada pelo painel em vez da parede.

**Faz a prova** e **Recebe a nota e mostra à professora** (tarefas manuais, aluno)

Como hoje.

**Lança a nota** (tarefa de usuário, professora)

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Pontos obtidos | Número | Escola por pontos: obrigatório; de 0 até o valor da prova, com uma casa decimal | |
| Conceito | Seleção única | Escola por conceito: obrigatório; conceitos cadastrados para a escola | |

A tela mostra só o campo que vale para a escola do aluno.

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Salvar | Compara com o esperado pela escola | default |
| Cancelar | A prova continua sem nota | cancel |

**Compara com o esperado pela escola** (tarefa de serviço)

Escola por pontos: calcula o aproveitamento (pontos obtidos sobre o valor da prova) e compara com a média da escola. Escola por conceito: compara o conceito com o mínimo da escola. A prova fica marcada como "dentro do esperado" ou "abaixo do esperado". Para provas do reforço, vale a mesma regra da escola do aluno. A avaliação diagnóstica não tem nota e não entra na comparação.

**Registra o elogio no sistema** (tarefa de usuário, professora)

O elogio fica junto da nota, no histórico do aluno, e aparece para o responsável no relatório de progresso.

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Elogio | Área de texto | Obrigatório; termos pedagógicos | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Salvar | Parabeniza o aluno | default |
| Pular | Parabeniza o aluno, sem elogio registrado | cancel |

**Parabeniza o aluno** (tarefa manual, professora)

Como hoje, na aula.

**Avisa os pais** (tarefa manual, professora)

De boca ou pelo WhatsApp, como já acontece quando a nota é ruim. O sistema não envia mensagens; os pais também veem o elogio no relatório.

**Sinaliza reforço na matéria** (tarefa de serviço)

A sinalização aparece no painel de pendências da professora e, para o responsável, a matéria aparece como "Precisa de atenção" no relatório de progresso.

**Procura entender por que foi mal** e **Conversa com os pais** (tarefas manuais, professora)

Como hoje: a professora conversa com o aluno, olha a prova e depois fala com os pais. A diferença é que a conversa parte de um critério (a regra da escola do aluno) e os pais já veem a matéria como "Precisa de atenção".

**Passa atividades de reforço** (tarefa de usuário, professora)

As atividades são registradas como tarefas, na tela de registro de tarefa, com a origem Reforço e a matéria sinalizada já preenchidas, e aparecem na semana do responsável.

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Matéria | Seleção única | Obrigatório | Matéria sinalizada |
| Origem | Seleção única | Obrigatório | Reforço |
| Descrição | Caixa de texto | Obrigatório | |
| Prazo | Data | Obrigatório; não anterior à data de atribuição | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Salvar | Fim, aluno em reforço com registro | default |
| Cancelar | Fim; a sinalização continua no painel | cancel |
