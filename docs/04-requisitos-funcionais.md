# 04. Requisitos funcionais

| ID | Descrição | Prioridade | Origem |
|---|---|---|---|
| RF01 | Cadastrar, editar e consultar alunos (nome, data de nascimento, ano escolar, matérias acompanhadas). | Alta | Nide |
| RF02 | Cadastrar o responsável e vinculá-lo aos alunos: cada aluno tem um único responsável com acesso, e um responsável pode ter mais de um aluno, com um único login. | Alta | Nide; vários filhos com um login |
| RF03 | Registrar o consentimento do responsável (data, forma de coleta e versão do termo). O aluno só fica ativo com consentimento registrado. | Alta | Consentimento e revogação; LGPD |
| RF04 | Cadastrar as matérias acompanhadas pela escolinha. | Alta | Nide |
| RF05 | Registrar aula: data, aluno, professora, presença (presente ou falta), matérias e conteúdos trabalhados e observação. | Alta | Registrar aula no computador |
| RF06 | Registrar tarefa vinculada a aluno e matéria, com origem (colégio ou reforço), descrição, data de atribuição e prazo. Só a professora registra. | Alta | Nide, Shirlei; registrar tarefas |
| RF07 | Atualizar o status da tarefa (Pendente, Entregue no prazo, Entregue com atraso, Não entregue), exclusivamente pela professora. | Alta | Registrar tarefas |
| RF08 | Permitir ao responsável sinalizar "meu filho fez a tarefa"; o aviso aparece no painel da professora e não altera o status. | Baixa | Avisar tarefa feita |
| RF09 | Registrar prova ou trabalho: aluno, matéria, origem (colégio ou reforço), data e descrição. Pode ser cadastrado antes da data, sem nota, e recebe nota de 0 a 10 com uma casa decimal depois de realizado. | Alta | Nide, Shirlei; provas e trabalhos com antecedência; lançar notas |
| RF10 | Sinalizar necessidade de reforço por matéria de forma automática, pela regra de reforço (média da matéria abaixo de 6,0), e manual (com motivo, inclusive a partir de uma avaliação diagnóstica). A automática sai sozinha e a manual só sai quando a professora desmarca. | Alta | Nide, Shirlei; avaliação diagnóstica; reforço automático e manual |
| RF11 | Exibir painel de pendências com cinco categorias: tarefas atrasadas, tarefas que vencem em até 3 dias, provas e trabalhos dos próximos 7 dias, alunos sinalizados para reforço e avisos do responsável. | Alta | Nide, Shirlei; painel ao abrir o sistema; provas e trabalhos com antecedência |
| RF12 | Exibir histórico por aluno em ordem cronológica (aulas, presença, tarefas, provas, trabalhos, avaliações diagnósticas e sinalizações), com filtro por matéria e período. | Alta | Histórico completo do aluno; ver a última aula |
| RF13 | Exibir relatório de progresso somente leitura com o conteúdo definido em "Conteúdo do relatório de progresso", abaixo. | Alta | Resumo do progresso no celular; vários filhos com um login |
| RF14 | Autenticar usuários por e-mail e senha; a professora pode redefinir a senha do responsável. | Alta | Todas as personas |
| RF15 | Autorizar o acesso por papel (professora ou responsável) e por vínculo: o responsável só acessa alunos vinculados a ele. | Alta | Ver só os próprios filhos; LGPD |
| RF16 | Encerrar matrícula: bloqueia na hora o acesso do responsável ao aluno e agenda a eliminação dos dados para 6 meses depois. | Alta | Nide; LGPD |
| RF17 | Eliminar ou anonimizar os dados de um aluno ao fim do prazo de guarda de 6 meses ou até 15 dias após o pedido do responsável. | Média | Pedir exclusão dos dados; LGPD |
| RF18 | Exibir página de privacidade em linguagem simples: dados coletados, finalidade, quem acessa, prazo de guarda e como pedir a revogação ou a exclusão. | Média | Consentimento e revogação; LGPD |
| RF19 | Registrar o pedido de revogação do consentimento ou de exclusão dos dados feito pelo responsável à professora, com data. O acesso é bloqueado no mesmo dia e a eliminação fica agendada para até 15 dias. | Média | Consentimento e revogação; pedir exclusão dos dados; LGPD |
| RF20 | Registrar avaliação diagnóstica: aluno, matéria, data e dificuldades observadas, sem nota e sem entrar na média da matéria. | Alta | Nide, Shirlei; avaliação diagnóstica |
| RF21 | Exibir ao responsável a visão da semana: última aula (data e conteúdos trabalhados), tarefas pendentes ou com prazo na semana e provas e trabalhos com data na semana. | Alta | Juscely, Ana Beatriz; última aula e semana |

## Conteúdo do relatório de progresso

- **Identificação:** nome do aluno, ano escolar e período do relatório (mês ou bimestre, escolhido pela professora).
- **Frequência:** aulas com presença sobre aulas registradas no período, em número e porcentagem.
- **Desempenho por matéria:** notas das provas e trabalhos do período, indicando a origem (colégio ou reforço), média da matéria, que é a média das 3 notas mais recentes, e situação: "Em dia" ou "Precisa de atenção", conforme a regra de reforço.
- **Conteúdos trabalhados:** lista resumida dos conteúdos registrados nas aulas, por matéria.
- **Tarefas:** quantidade atribuída, entregues no prazo, entregues com atraso, não entregues e pendentes, além da taxa de entrega no prazo.
- **Observação da professora:** texto livre, de caráter pedagógico, visível para o responsável.
