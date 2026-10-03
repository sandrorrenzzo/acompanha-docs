### Processo 1 AS IS – Provas e trabalhos do colégio

Se o aluno não avisa, a prova ou o trabalho passa sem preparação (já aconteceu com um trabalho de História de 10 pontos). A professora só sabe a nota se o aluno mostrar, não registra, e quando a nota é ruim apenas avisa o responsável de boca.

O modelo está em [01-provas-e-trabalhos-as-is.bpmn](../bpmn/01-provas-e-trabalhos-as-is.bpmn), em BPMN 2.0 no formato do bpmn.io. Para abrir ou editar, arraste o arquivo para o [demo.bpmn.io](https://demo.bpmn.io) ou abra no Camunda Modeler.

Participam do processo o aluno, a professora e o responsável. Nenhuma atividade usa sistema: todas são tarefas manuais.

#### Fluxo

1. O colégio marca uma prova ou um trabalho.
2. **O aluno avisa a professora?** Se não avisa, o processo termina com a prova ou o trabalho **sem preparação**.
3. Se avisa, a professora ajuda o aluno a estudar ou a fazer o trabalho.
4. Chega a data da prova ou da entrega.
5. **O aluno mostra a nota?** Se não mostra, o processo termina e a **professora não sabe o resultado**.
6. Se mostra, a professora vê a nota, sem registrar.
7. **Foi mal na matéria?** Se não, **nada é feito**.
8. Se foi mal, a professora fala com o responsável que o aluno precisa estudar mais a matéria, e o responsável recebe o aviso verbal. O processo termina com um **aviso sem histórico**.

#### Detalhamento das atividades

| **Atividade** | **Quem executa** | **Como é feito hoje** | **Problema** |
| --- | --- | --- | --- |
| Ajuda o aluno a estudar ou a fazer o trabalho | Professora | Na aula, com o caderno do aluno na escolinha | Só acontece se o aluno avisou da prova ou do trabalho |
| Vê a nota, sem registrar | Professora | O aluno mostra a prova ou o boletim | A nota não fica guardada, e não há média por matéria |
| Fala com o responsável que o aluno precisa estudar mais a matéria | Professora | De boca | A decisão depende da memória e da percepção da professora |
| Recebe o aviso verbal | Responsável | Conversa com a professora | Não há histórico para consultar depois |
