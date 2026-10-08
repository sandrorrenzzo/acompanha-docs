### Processo 2 AS IS – Consulta do progresso pelo responsável

Os responsáveis pedem notícias com frequência, a maioria todos os dias. A professora responde de memória, porque não há registro, e muitas vezes só no fim da aula ou do dia, porque está atendendo os alunos. O responsável só sabe o que perguntou.

O modelo está em [02-consulta-do-progresso-as-is.bpmn](../bpmn/02-consulta-do-progresso-as-is.bpmn), em BPMN 2.0 no formato do bpmn.io. Para abrir ou editar, arraste o arquivo para o [demo.bpmn.io](https://demo.bpmn.io) ou abra no Camunda Modeler.

Participam do processo o responsável e a professora. Nenhuma atividade usa sistema: todas são tarefas manuais.

#### Fluxo

1. O responsável quer saber como o filho está.
2. Pergunta por WhatsApp ou pessoalmente.
3. **A professora está livre para responder?** Se está em aula, a resposta espera o fim da aula ou do dia.
4. A professora responde com o que lembra.
5. O responsável recebe a resposta. O processo termina com o responsável sabendo **só o que perguntou**.

#### Detalhamento das atividades

| **Atividade** | **Quem executa** | **Como é feito hoje** | **Problema** |
| --- | --- | --- | --- |
| Pergunta por WhatsApp ou pessoalmente | Responsável | Mensagem ou conversa com a professora | A maioria pergunta todos os dias |
| Responde com o que lembra | Professora | Lembra do que aconteceu nas aulas | Não há registro para consultar; interrompe a aula ou fica para o fim do dia |
| Recebe a resposta | Responsável | Mensagem ou conversa | A resposta chega atrasada e cobre só o que foi perguntado |
