### Processo 1 AS IS – Provas e trabalhos do colégio

Quando o aluno entra na escolinha, a Nide pede aos pais, no WhatsApp, o cronograma de provas que o colégio entrega no início do período letivo. Ela imprime o cronograma e prega na parede da escolinha, para revisitar sempre, lembrar os alunos das provas e estudar com eles de forma direcionada. Depois da prova, se o aluno mostra a nota e ela é boa, a Nide parabeniza; se não é, procura entender o que aconteceu e conversa com os pais. Nada disso fica registrado.

O modelo está em [01-provas-e-trabalhos-as-is.bpmn](../bpmn/01-provas-e-trabalhos-as-is.bpmn), em BPMN 2.0 no formato do bpmn.io. Para abrir ou editar, arraste o arquivo para o [demo.bpmn.io](https://demo.bpmn.io) ou abra no Camunda Modeler.

Participam do processo a professora, o aluno e o responsável. Nenhuma atividade usa sistema: todas são tarefas manuais.

#### Fluxo

1. O aluno entra na escolinha.
2. A professora pede o cronograma de provas aos pais, no privado do WhatsApp, e eles mandam.
3. A professora imprime o cronograma e prega na parede da escolinha.
4. Com base no cronograma e no que o colégio pede para cada prova, ela estuda com o aluno, aplicando provas e atividades que ela mesma imprime.
5. No dia da prova, o aluno faz a prova.
6. Quando recebe a nota, o aluno mostra à professora. **A nota foi boa?**
   - Se foi, a professora parabeniza o aluno e **segue a rotina**.
   - Se não foi, ela procura entender por que o aluno foi mal e conversa com os pais. O processo termina com os **pais avisados, sem registro**.

#### Detalhamento das atividades

| **Atividade** | **Quem executa** | **Como é feito hoje** | **Problema** |
| --- | --- | --- | --- |
| Pede o cronograma de provas no WhatsApp | Professora | Mensagem no privado com os pais | Feito uma vez, na entrada; trabalhos passados durante o período e datas alteradas não estão no cronograma |
| Manda o cronograma | Responsável | Encaminha o que recebeu do colégio | |
| Imprime e prega o cronograma na parede | Professora | Folha impressa na parede da escolinha | Só serve a quem está na escolinha; o responsável não vê o que vem pela frente, e nada avisa que uma prova está chegando |
| Estuda com o aluno para a prova | Professora | Provas e atividades impressas por ela | O que foi estudado para cada prova não fica registrado |
| Faz a prova | Aluno | No colégio | |
| Recebe a nota e mostra à professora | Aluno | Mostra a prova corrigida ou o boletim | Depende de o aluno mostrar; a nota não é anotada, e não há histórico por matéria |
| Parabeniza o aluno | Professora | Na aula | |
| Procura entender por que foi mal | Professora | Conversa com o aluno e olha a prova | A decisão de que a nota foi ruim é de cabeça, sem critério nem histórico |
| Conversa com os pais | Professora | De boca ou pelo WhatsApp | Não fica registro da conversa nem do que foi combinado |
