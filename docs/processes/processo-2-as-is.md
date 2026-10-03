### Processo 2 AS IS – Consulta do progresso pelo responsável

Os responsáveis pedem notícias com frequência, a maioria todos os dias, e cada pedido toma tempo da professora, que responde de memória porque não há registro; o responsável só sabe o que perguntou, quando a professora consegue responder.

O modelo está em [02-consulta-do-progresso-as-is.bpmn](../bpmn/02-consulta-do-progresso-as-is.bpmn), em BPMN 2.0 no formato do bpmn.io. Para abrir ou editar, arraste o arquivo para o [demo.bpmn.io](https://demo.bpmn.io) ou abra no Camunda Modeler.

Participam do processo o responsável e a professora. Nenhuma atividade usa sistema: todas são tarefas manuais.

#### Fluxo

1. O responsável quer saber como o filho está.
2. Pergunta por WhatsApp ou pessoalmente.
3. A professora responde de memória, sem registro para consultar.
4. O responsável recebe a resposta. O processo termina com o responsável **informado**, apenas sobre o que perguntou.

#### Detalhamento das atividades

| **Atividade** | **Quem executa** | **Como é feito hoje** | **Problema** |
| --- | --- | --- | --- |
| Pergunta por WhatsApp ou pessoalmente | Responsável | Mensagem ou conversa com a professora | A maioria pergunta todos os dias |
| Responde de memória, sem registro para consultar | Professora | Lembra do que aconteceu nas aulas | Toma tempo da professora e depende da memória |
| Recebe a resposta | Responsável | Mensagem ou conversa | Só sabe o que perguntou, quando a professora consegue responder |
