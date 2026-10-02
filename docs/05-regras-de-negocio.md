# 05. Regras de negócio

| ID | Regra | Situação |
|---|---|---|
| RN01 | As avaliações usam nota de 0,0 a 10,0, com uma casa decimal. | Validada com a parceira |
| RN02 | A média da matéria é a média aritmética das notas das 3 provas ou trabalhos mais recentes do aluno naquela matéria, do colégio ou do reforço (ou de todas, se houver menos de 3). A avaliação diagnóstica não entra na média. | Decidida pela equipe |
| RN03 | Uma tarefa, do colégio ou do reforço, é considerada atrasada quando está com status Pendente e a data atual é posterior ao prazo. | Decidida pela equipe |
| RN04 | O aluno passa a "precisar de reforço" em uma matéria quando ocorrer pelo menos uma destas situações: (a) média da matéria abaixo de 6,0, com pelo menos 2 notas; (b) marcação manual da professora, por exemplo a partir de uma avaliação diagnóstica. Tarefas atrasadas ou não entregues não geram reforço. O valor 6,0 fica configurável. | Validada com a parceira (limite configurável) |
| RN05 | A sinalização automática sai sozinha quando a média da matéria volta a ficar em 6,0 ou mais. A sinalização manual só sai quando a professora desmarca. | Decidida pela equipe |
| RN06 | Somente a professora registra tarefas, provas e trabalhos e altera o status da tarefa. Os itens do colégio são registrados por ela quando o aluno ou a família avisam. O status registra a conferência feita pela professora, e não uma declaração: ele alimenta o painel e o relatório, então precisa ter uma única fonte confiável. O responsável pode avisar que a tarefa foi feita (aviso de tarefa feita), e a professora confirma. | Decidida pela equipe |
| RN07 | O responsável só acessa dados de alunos com vínculo ativo com ele. A verificação é feita no servidor em toda requisição, e não apenas escondendo itens na tela. | Obrigatória (LGPD) |
| RN08 | O cadastro do aluno só fica ativo depois que o consentimento de pelo menos um dos pais ou responsável legal for registrado. | Obrigatória (LGPD, art. 14, §1º) |
| RN09 | Ao encerrar a matrícula, o acesso do responsável é bloqueado imediatamente e os dados do aluno são eliminados após 6 meses (prazo para eventual retorno ou relatório final). Estatísticas sem identificação podem ser mantidas. | Decidida pela equipe |
| RN10 | Pedido de revogação do consentimento ou de exclusão feito pelo responsável à professora, que o registra no sistema: acesso bloqueado no mesmo dia e dados eliminados em até 15 dias. | Decidida pela equipe |
| RN11 | As duas professoras têm o mesmo nível de acesso (decisão da parceira). A Nide e a Shirlei se diferenciam pelas séries que atendem, não pelas permissões. | Decidida pela parceira |
| RN12 | Não são registrados diagnósticos médicos ou laudos (dados de saúde são dados sensíveis). As dificuldades são descritas apenas em termos pedagógicos. | Decidida pela equipe (minimização) |
| RN13 | Cada aluno tem um único responsável com acesso ao sistema. Um responsável pode estar vinculado a mais de um aluno, com um único login. | Decidida pela equipe |
