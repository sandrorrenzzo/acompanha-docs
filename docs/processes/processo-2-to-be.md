### Processo 2 TO BE – Consulta do progresso pelo responsável

O responsável deixa de perguntar à professora e consulta sozinho, a qualquer hora, o progresso do filho. Primeiro o sistema mostra a semana: última aula, tarefas e provas e trabalhos. Se quiser, ele abre o relatório do mês ou do bimestre. Se alguma matéria aparece como "Precisa de atenção", a família age: ajuda em casa ou conversa com a professora. A professora não precisa mais responder de memória; só escreve a observação pedagógica do período, que aparece no relatório.

O modelo está em [02-consulta-do-progresso-to-be.bpmn](../bpmn/02-consulta-do-progresso-to-be.bpmn), em BPMN 2.0 no formato do bpmn.io. Para abrir ou editar, arraste o arquivo para o [demo.bpmn.io](https://demo.bpmn.io) ou abra no Camunda Modeler.

Participam do processo o responsável, o Sistema Acompanha e a professora.

#### O que muda em relação a hoje

| **Hoje** | **Com o Acompanha** |
| --- | --- |
| Pergunta por WhatsApp ou pessoalmente | Entra no sistema, a qualquer hora |
| Espera a professora ficar livre | O sistema mostra a semana do filho na hora |
| A professora responde com o que lembra | O sistema monta o relatório com o que foi registrado |
| Sabe só o que perguntou | Vê a semana e o período completos, e sabe quais matérias precisam de atenção |

#### Fluxo

1. O responsável quer saber como o filho está e entra no sistema.
2. O sistema mostra a semana do filho: última aula, tarefas e provas e trabalhos.
3. **Quer ver o período?** Se não, o processo termina com o responsável **informado sobre a semana**.
4. Se quer, o sistema monta o relatório do mês ou do bimestre e o responsável lê o relatório.
5. **Alguma matéria precisa de atenção?**
   - Se não, o processo termina com o responsável **informado, com o filho em dia**.
   - Se sim, a família ajuda em casa ou conversa com a professora. O processo termina com a **família agindo sobre a dificuldade**.

Em paralelo, no fim do mês ou do bimestre, a professora escreve a observação pedagógica do período, que aparece no relatório. Se ela não escrever, o relatório mostra "Sem observação neste período".

Entrar no sistema inclui o login e, para quem tem mais de um filho, a escolha do aluno. O responsável só vê alunos com vínculo ativo com ele; sem vínculo ativo (por exemplo, matrícula encerrada), o acesso é negado e fica no registro de acessos. Esses passos são detalhe de tela e por isso não aparecem no diagrama.

O aviso de tarefa feita, que o responsável também pode mandar pelo sistema, faz parte da gestão de tarefas e não deste processo.

#### Detalhamento das atividades

**Entra no sistema** (tarefa de usuário, responsável)

Login com e-mail e senha (mínimo de 8 caracteres, tentativas limitadas por usuário e por IP). Quem tem mais de um aluno vinculado escolhe o aluno numa lista.

**Mostra a semana do filho** (tarefa de serviço)

Tela somente leitura, feita para o celular (de 360 px de largura em diante, sem rolagem horizontal).

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Data da última aula | Data | Somente leitura | |
| Conteúdos trabalhados na última aula | Área de texto | Somente leitura | |
| Tarefas pendentes ou com prazo na semana | Tabela | Somente leitura; matéria, descrição, prazo e status | |
| Provas e trabalhos com data na semana | Tabela | Somente leitura; matéria, tipo e data | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Ver relatório | Monta o relatório do período | default |
| Trocar de aluno | Lista de alunos vinculados | |
| Sair | Fim do processo, informado sobre a semana | cancel |

**Monta o relatório do período** (tarefa de serviço) e **Lê o relatório** (tarefa de usuário, responsável)

Relatório somente leitura. O período (mês ou bimestre) é escolhido pela professora.

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Identificação | Caixa de texto | Nome do aluno, ano escolar e período do relatório | |
| Frequência | Número | Aulas com presença sobre aulas registradas no período, em número e porcentagem | |
| Desempenho por matéria | Tabela | Notas do período com a origem e o elogio da professora, quando houver, se ficou dentro ou abaixo do esperado pela escola e situação ("Em dia" ou "Precisa de atenção") | |
| Conteúdos trabalhados | Tabela | Lista resumida dos conteúdos das aulas, por matéria | |
| Tarefas | Tabela | Atribuídas, entregues no prazo, entregues com atraso, não entregues, pendentes e taxa de entrega no prazo | |
| Observação da professora | Área de texto | Somente leitura; "Sem observação neste período" quando vazia | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Voltar | Semana do filho | default |

**Ajuda em casa ou conversa com a professora** (tarefa manual, responsável)

Fora do sistema. A matéria marcada "Precisa de atenção" já tem atividades de reforço registradas pela professora (processo 1), que aparecem nas tarefas da semana.

**Escreve a observação do período** (tarefa de usuário, professora)

| **Campo** | **Tipo** | **Restrições** | **Valor default** |
| --- | --- | --- | --- |
| Aluno | Seleção única | Obrigatório | |
| Período | Seleção única | Obrigatório; mês ou bimestre | |
| Observação | Área de texto | Obrigatório; só termos pedagógicos, sem diagnósticos médicos ou laudos | |

| **Comandos** | **Destino** | **Tipo** |
| --- | --- | --- |
| Salvar | Observação aparece no relatório | default |
| Cancelar | Fim, sem observação | cancel |
