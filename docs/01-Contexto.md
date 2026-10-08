# Introdução

O Acompanha é um sistema web de acompanhamento pedagógico individualizado para a Divertindo a Mente, escolinha de reforço escolar. Ele passa a registrar aulas, tarefas e notas, que hoje não ficam anotadas em lugar nenhum, e dá aos responsáveis uma visão simples do progresso dos próprios filhos.

Projeto da disciplina Trabalho Interdisciplinar: Aplicações para Processos de Negócio (PUC Minas Contagem).

## Cliente

A Divertindo a Mente é uma escolinha de reforço escolar no bairro Bela Vista, em Contagem/MG, que atende principalmente famílias do próprio bairro. A proprietária, Ieronides (Nide), é também a professora principal e atende os alunos de todas as séries até o 5º ano; no projeto, ela atua como *Product Owner*, conforme a [ata de acordo com a parceira](atas/ata-acordo-com-cliente-externo.pdf); a professora auxiliar, Shirlei, atende os alunos do 6º ano.

Nas aulas, o foco é ajudar nas atividades, nos trabalhos e nos estudos do colégio. Cada aluno tem um caderno próprio na escolinha, onde a professora aplica atividades com base no que ele está estudando no colégio.

A escolinha não tem orçamento para software, e os equipamentos disponíveis são o computador da escolinha e os celulares dos responsáveis (veja as [restrições](02-Especificacao.md#restrições)).

## Problema

Hoje não existe acompanhamento pedagógico registrado. A planilha no Drive é usada só para o controle financeiro, e a tentativa de anotar aulas, tarefas e notas nela foi abandonada por falta de tempo. Quando a professora percebe uma dificuldade, avisa o responsável de boca.

Isso traz dois problemas mais evidentes:

- **Provas e trabalhos do colégio se perdem.** A professora pede aos pais o cronograma de provas do colégio e o prega na parede da escolinha, mas trabalhos passados durante o período e datas alteradas não estão nele. Se o aluno não avisa, a professora não fica sabendo da prova ou do trabalho e o aluno vai sem a ajuda do reforço (já aconteceu com um trabalho de História de 10 pontos). A professora só sabe a nota se o aluno mostrar, e não a registra.
- **Os responsáveis dependem da memória da professora.** Eles pedem notícias com frequência, a maioria todos os dias, e cada pedido toma tempo da professora, que responde de memória porque não há registro.

## Objetivos

O objetivo geral é desenvolver um sistema web que registre o acompanhamento pedagógico de cada aluno da Divertindo a Mente e permita aos responsáveis consultar o progresso dos próprios filhos.

Os objetivos específicos são:

- Registrar aulas, presença, tarefas, provas, trabalhos, notas e avaliações diagnósticas de cada aluno, numa tela simples que caiba na rotina corrida das professoras.
- Mostrar à professora, ao abrir o sistema, um painel com o que está atrasado, o que vence nos próximos dias e quem precisa de reforço.
- Sinalizar automaticamente a necessidade de reforço quando uma prova fica abaixo do esperado pela escola do aluno (cada escola tem sua regra, por pontos ou por conceito), além de permitir a marcação manual.
- Oferecer ao responsável, pelo celular, a visão da semana e o relatório de progresso do mês ou do bimestre, somente dos alunos vinculados a ele.
- Tratar os dados das crianças conforme a LGPD, com consentimento registrado, acesso restrito por vínculo e eliminação dos dados no encerramento ou a pedido do responsável.

## Justificativa

O AS-IS foi montado a partir das entrevistas com as duas professoras e da conversa com a proprietária. Como hoje nada é registrado, não há como medir quanto tempo o sistema economiza; o ganho está em passar a ter um registro que hoje não existe.

As entrevistas com os responsáveis reforçam a necessidade:

- Todas acompanham de perto, e a maioria pede notícias todos os dias.
- Tarefas e dificuldades aparecem nas 4 respostas; notas em 2; faltas em 1.
- Uma responsável tem dois filhos na escolinha, o que confirma a necessidade de ver mais de um aluno com o mesmo acesso.

## Público-alvo

- **Professoras (usuárias operadoras):** as duas professoras da escolinha, que registram aulas, tarefas, provas, trabalhos e notas no computador da escolinha, numa rotina de demanda bastante corrida. Têm o mesmo nível de acesso e se diferenciam pelas séries que atendem.
- **Responsáveis (usuários de consulta):** mães e pais dos alunos, que consultam o progresso dos próprios filhos pelo celular. A facilidade com tecnologia informada por eles vai de 3 a 5, numa escala de 1 a 5: o sistema precisa ser simples, mas ninguém se declarou com pouca familiaridade.
- **Alunos:** não usam o sistema. Seus dados são tratados com cuidado especial por serem crianças e adolescentes (veja [tratamento de dados](02-Especificacao.md#tratamento-de-dados-lgpd)).

As personas detalhadas estão na [especificação do projeto](02-Especificacao.md#personas).
