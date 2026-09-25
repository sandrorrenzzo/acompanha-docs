# 10 — Regras de negócio

> Projeto Acompanha (TIAPN, PUC Minas Contagem). Regras que definem nota, reforço, status de tarefa, acesso e guarda de dados. Índice geral: [README](../README.md).

| ID | Regra | Situação |
|---|---|---|
| RN01 | As avaliações usam nota de 0,0 a 10,0, com uma casa decimal. | Decidida pela equipe |
| RN02 | A média da matéria é a média aritmética das 3 avaliações mais recentes do aluno naquela matéria (ou de todas, se houver menos de 3). | Decidida pela equipe |
| RN03 | Uma tarefa é considerada atrasada quando está com status Pendente e a data atual é posterior ao prazo. | Decidida pela equipe |
| RN04 | O aluno passa a "precisar de reforço" em uma matéria quando ocorrer pelo menos uma destas situações: (a) média da matéria abaixo de 6,0, com pelo menos 2 avaliações; (b) 2 ou mais tarefas da matéria atrasadas ou não entregues nos últimos 30 dias; (c) marcação manual da professora. Os valores 6,0, 2 tarefas e 30 dias ficam configuráveis. | Decidida pela equipe (limites configuráveis) |
| RN05 | A sinalização automática sai sozinha quando as condições (a) e (b) deixam de valer. A sinalização manual só sai quando a professora desmarca. | Decidida pela equipe |
| RN06 | Somente a professora altera o status da tarefa. O status registra a conferência feita pela professora, e não uma declaração: ele alimenta a regra de reforço (RN04) e o relatório, então precisa ter uma única fonte confiável. O responsável pode avisar que a tarefa foi feita (RF08), e a professora confirma. | Decidida pela equipe |
| RN07 | O responsável só acessa dados de alunos com vínculo ativo com ele. A verificação é feita no servidor em toda requisição, e não apenas escondendo itens na tela. | Obrigatória (LGPD) |
| RN08 | O cadastro do aluno só fica ativo depois que o consentimento de pelo menos um dos pais ou responsável legal for registrado. | Obrigatória (LGPD, art. 14, §1º) |
| RN09 | Ao encerrar a matrícula, o acesso dos responsáveis é bloqueado imediatamente e os dados do aluno são eliminados após 6 meses (prazo para eventual retorno ou relatório final). Estatísticas sem identificação podem ser mantidas. | Decidida pela equipe |
| RN10 | Pedido de revogação do consentimento ou de exclusão feito pelo responsável: acesso bloqueado no mesmo dia e dados eliminados em até 15 dias. | Decidida pela equipe |
| RN11 | As duas professoras têm o mesmo nível de acesso (decisão da parceira). As personas P1 e P2 se diferenciam pelos objetivos e pelo uso, não pelas permissões. | Decidida pela parceira |
| RN12 | Não são registrados diagnósticos médicos ou laudos (dados de saúde são dados sensíveis). As dificuldades são descritas apenas em termos pedagógicos. | Decidida pela equipe (minimização) |
