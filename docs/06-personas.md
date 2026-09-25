# 06 — Personas

> Projeto Acompanha (TIAPN, PUC Minas Contagem). Quem são as personas e em que pé está a troca das provisórias pelas reais. Índice geral: [README](../README.md).

## Decisão: personas reais

As personas do projeto passam a ser **pessoas reais** da comunidade da Divertindo a Mente, e não perfis fictícios. As entrevistas serão aplicadas pela proprietária, Ieronildes (Nide), com o roteiro do documento [07 — Roteiro de entrevistas](07-roteiro-entrevistas.md). Composição definida (6 personas, uma por integrante do grupo):

| Persona | Quem será entrevistado | Por que esse perfil |
|---|---|---|
| P1 | Ieronildes, a Nide (proprietária e professora principal) | Usuária operadora com foco em gestão e no contato com as famílias |
| P2 | Shirlei (professora auxiliar) | Usuária operadora com foco no registro do dia a dia |
| P3 a P6 | 4 responsáveis reais, com perfis diferentes entre si | Sugestão de variedade: pouca familiaridade com celular, avô ou avó responsável, pais separados (dois responsáveis) e responsável atento à privacidade |

Regras para as entrevistas:

- Antes de começar, a pessoa é informada sobre o trabalho e aceita participar (texto de abertura no documento [07 — Roteiro de entrevistas](07-roteiro-entrevistas.md)).
- Nos documentos aparecem apenas o primeiro nome e a idade do entrevistado; nenhum dado que identifique a criança (nome, escola regular, foto) é registrado (LGPD, RN12).
- Quando as respostas chegarem, as personas provisórias abaixo são substituídas, e histórias de usuário e requisitos são revisados se algum perfil real mudar as necessidades.

## Personas provisórias (fictícias, a substituir pelas reais)

As personas abaixo foram usadas na revisão da Sprint 1 e servem apenas de referência até a chegada das respostas das entrevistas.

### P1 (provisória) — Cláudia Martins, 52 anos — Proprietária e professora principal (usuária operadora)

- Contexto: É dona da escolinha e, além de dar aula, cuida das matrículas e da conversa com as famílias. É quem decide quais alunos precisam de mais atenção e quem responde às cobranças dos pais.
- Tecnologia: Usa notebook com Windows para as planilhas e celular Android para WhatsApp. Sabe usar planilhas, mas não tem paciência para sistemas com muitos menus.
- Objetivos: Ter uma visão geral da turma sem abrir várias planilhas; saber, no início do dia, quem está com tarefa atrasada ou precisa de reforço; preparar um retorno para os pais em poucos minutos.
- Frustrações: Montar o histórico de um aluno antes de uma conversa com a família exige juntar várias abas; já esqueceu de cobrar tarefas porque a anotação se perdeu.
- Fala: "Quero abrir o sistema de manhã e já saber quem eu preciso olhar hoje."
- Usa: Painel de pendências, histórico por aluno, relatório de progresso, cadastro e encerramento de matrícula.
- RFs: RF01, RF02, RF03, RF11, RF12, RF13, RF16
- Base: Inspirada no perfil da proprietária da Divertindo a Mente.

### P2 (provisória) — Juliana Rocha, 29 anos — Professora auxiliar (usuária operadora)

- Contexto: Atende os alunos em sala, muitas vezes alternando com a professora principal. Tem o mesmo acesso da proprietária, mas o foco dela é o registro do dia a dia, não a gestão.
- Tecnologia: Usa quase só o celular; raramente abre o notebook. Registra as coisas entre um aluno e outro, com pouco tempo.
- Objetivos: Registrar a aula, a tarefa passada e a nota em poucos toques pelo celular; saber o que a outra professora trabalhou na última aula com aquele aluno para dar continuidade.
- Frustrações: Quando pega um aluno que estava com a outra professora, não sabe em que ponto ele parou; anotar no papel e passar para a planilha depois dá retrabalho.
- Fala: "Se eu não conseguir registrar pelo celular em dois minutos, eu vou deixar para depois e vou esquecer."
- Usa: Registro de aula e presença, criação de tarefas, registro de avaliação, histórico do aluno, sinalização manual de reforço.
- RFs: RF05, RF06, RF07, RF09, RF10, RF12
- Base: Inspirada no perfil da professora auxiliar da Divertindo a Mente.

### P3 (provisória) — Patrícia Souza, 38 anos — Mãe do Pedro, 9 anos, 4º ano (usuária de consulta)

- Contexto: Trabalha como operadora de caixa em turnos alternados e quase nunca consegue falar com a professora no horário de saída.
- Tecnologia: Celular Android simples, com pouco espaço e pacote de dados limitado. Usa WhatsApp e aplicativo do banco; não usa computador.
- Objetivos: Ver, rapidamente e pelo celular, se o filho tem tarefa pendente e se está com dificuldade em alguma matéria.
- Frustrações: Só fica sabendo que o filho está com dificuldade quando a professora chama para conversar.
- Fala: "Eu só quero saber se está tudo bem ou se eu preciso sentar com ele hoje."
- Usa: Resumo do progresso no celular, lista de tarefas pendentes.
- RFs: RF13, RF14, RF15
- Base: Persona hipotética de responsável, a validar com a parceira.

### P4 (provisória) — Roberto Almeida, 45 anos — Pai da Laura, 12 anos, 7º ano (usuário de consulta)

- Contexto: É separado e tem guarda compartilhada. A mãe da Laura também é responsável e hoje é quem recebe as informações da escolinha.
- Tecnologia: Analista administrativo, usa computador o dia todo e se sente à vontade com sistemas e relatórios.
- Objetivos: Acompanhar notas por matéria e a evolução ao longo do bimestre com o próprio acesso, sem depender da ex-esposa.
- Frustrações: Recebe as informações de segunda mão e atrasadas.
- Fala: "Eu também sou responsável por ela e quero ver as mesmas informações que a mãe vê."
- Usa: Relatório de progresso detalhado por matéria e período.
- RFs: RF02, RF13, RF15, RF19
- Base: Persona hipotética de responsável, a validar com a parceira.

### P5 (provisória) — Maria Aparecida Lima, 67 anos — Avó e responsável legal do Gabriel (8) e da Sofia (11) (usuária de consulta)

- Contexto: Aposentada, cria os dois netos e é quem assina tudo por eles.
- Tecnologia: Pouca familiaridade digital; usa o celular com letra grande e pede ajuda à neta mais velha para coisas novas.
- Objetivos: Saber se os dois netos estão indo bem, com linguagem simples e sem ter de interpretar gráficos.
- Frustrações: Sistemas com muitas telas e senhas difíceis; letras pequenas.
- Fala: "Me mostra do jeito mais simples se eles estão bem ou não."
- Usa: Um único acesso para ver os dois netos; situação por matéria com indicação clara (em dia / precisa de atenção).
- RFs: RF02, RF13, RF14
- Base: Persona hipotética de responsável, a validar com a parceira.

### P6 (provisória) — Fernanda Costa, 34 anos — Mãe do Davi, 10 anos, 5º ano (usuária de consulta)

- Contexto: Enfermeira em regime de plantão. O Davi tem dificuldade em matemática e ela se preocupa com quem pode ver as informações sobre ele.
- Tecnologia: Usa celular e computador com facilidade; lê termos de uso antes de aceitar.
- Objetivos: Acompanhar o progresso do filho com a certeza de que só a família e as professoras veem os dados dele, e poder pedir a exclusão se ele sair da escolinha.
- Frustrações: Não saber para que servem os dados coletados nem por quanto tempo ficam guardados.
- Fala: "Quem mais vai ver as notas e as dificuldades do meu filho?"
- Usa: Termo de consentimento, página de privacidade, pedido de exclusão de dados, relatório de progresso.
- RFs: RF03, RF15, RF17, RF18
- Base: Persona hipotética de responsável, a validar com a parceira.
