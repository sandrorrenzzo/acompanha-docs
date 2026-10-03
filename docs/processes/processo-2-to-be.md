### Processo 2 TO BE – Consulta do progresso pelo responsável

O responsável consulta sozinho, a qualquer hora, apenas os alunos vinculados a ele. Primeiro aparece a visão da semana, com a última aula, as tarefas pendentes e as provas e trabalhos da semana. Se quiser, ele abre o relatório do mês ou do bimestre. A professora só escreve a observação pedagógica do período.

O modelo está em [02-consulta-do-progresso-to-be.bpmn](../bpmn/02-consulta-do-progresso-to-be.bpmn), em BPMN 2.0 no formato do bpmn.io. Para abrir ou editar, arraste o arquivo para o [demo.bpmn.io](https://demo.bpmn.io) ou abra no Camunda Modeler.

Participam do processo o responsável, o Sistema Acompanha e a professora.

#### Fluxo

1. O responsável quer saber como o filho está e faz login com e-mail e senha.
2. **Tem vínculo ativo com algum aluno?** Se não tem, o processo termina com **acesso negado e registrado**.
3. **Tem mais de um aluno vinculado?** Se tem, o sistema lista os alunos vinculados e o responsável escolhe um.
4. O sistema mostra a semana do aluno: última aula, tarefas e provas e trabalhos.
5. O responsável consulta a semana do filho.
6. **Quer ver o relatório do período?** Se não, o processo termina com o responsável **informado sobre a semana**.
7. Se quer, o sistema monta o relatório do mês ou do bimestre e o responsável lê o relatório. O processo termina com o responsável **informado**.

Em paralelo, no fim do mês ou do bimestre, a professora escreve a observação pedagógica do período, que fica disponível no relatório.

#### Detalhamento das atividades

**Faz login com e-mail e senha** (tarefa de usuário, responsável)

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| E-mail | Caixa de texto | Obrigatório; formato de e-mail | |
| Senha | Caixa de texto | Obrigatório; mínimo de 8 caracteres; tentativas limitadas por usuário e por IP | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Entrar | Vínculo ativo com algum aluno? | default |

**Vínculo ativo com algum aluno?** (decisão do sistema)

O responsável só acessa alunos com vínculo ativo com ele. A verificação é feita no servidor em toda requisição. Tentativas de acessar outro aluno são negadas e ficam no registro de acessos.

**Lista os alunos vinculados** (tarefa de serviço) e **Escolhe o aluno** (tarefa de usuário, responsável)

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Aluno | Seleção única | Só alunos vinculados ao responsável | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Abrir | Mostra a semana | default |

**Mostra a semana: última aula, tarefas e provas** (tarefa de serviço) e **Consulta a semana do filho** (tarefa de usuário, responsável)

Tela somente leitura, feita para o celular (de 360 px de largura em diante, sem rolagem horizontal).

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Data da última aula | Data | Somente leitura | |
| Conteúdos trabalhados na última aula | Área de texto | Somente leitura | |
| Tarefas pendentes ou com prazo na semana | Tabela | Somente leitura; matéria, descrição, prazo e status | |
| Provas e trabalhos com data na semana | Tabela | Somente leitura; matéria, tipo e data | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Ver relatório | Monta o relatório do mês ou bimestre | default |
| Avisar tarefa feita | Aviso no painel da professora; não muda o status da tarefa | |
| Trocar de aluno | Escolhe o aluno | |
| Sair | Fim do processo | cancel |

**Monta o relatório do mês ou bimestre** (tarefa de serviço) e **Lê o relatório de progresso** (tarefa de usuário, responsável)

Relatório somente leitura. O período (mês ou bimestre) é escolhido pela professora.

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Identificação | Caixa de texto | Nome do aluno, ano escolar e período do relatório | |
| Frequência | Número | Aulas com presença sobre aulas registradas no período, em número e porcentagem | |
| Desempenho por matéria | Tabela | Notas do período com a origem, média da matéria e situação ("Em dia" ou "Precisa de atenção") | |
| Conteúdos trabalhados | Tabela | Lista resumida dos conteúdos das aulas, por matéria | |
| Tarefas | Tabela | Atribuídas, entregues no prazo, entregues com atraso, não entregues, pendentes e taxa de entrega no prazo | |
| Observação da professora | Área de texto | Somente leitura | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Voltar | Consulta a semana do filho | default |

**Escreve a observação pedagógica do período** (tarefa de usuário, professora)

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Aluno | Seleção única | Obrigatório | |
| Período | Seleção única | Obrigatório; mês ou bimestre | |
| Observação | Área de texto | Obrigatório; só termos pedagógicos, sem diagnósticos médicos ou laudos | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Salvar | Observação disponível no relatório | default |
| Cancelar | Fim, sem observação | cancel |
