# 06. Requisitos não funcionais

| ID | Categoria | Requisito (critério mensurável) | Prioridade |
|---|---|---|---|
| RNF01 | Usabilidade | O registro de aula e de tarefa é simples: uma única tela, com poucos campos e sem etapas extras, para caber na rotina corrida das professoras. | Alta |
| RNF02 | Responsividade | As telas das professoras são feitas para o navegador do computador (a partir de 1280 px de largura). As telas do responsável funcionam de 360 px a 1920 px de largura sem rolagem horizontal, com prioridade para o celular, e são testadas em celulares reais dos responsáveis. | Alta |
| RNF03 | Desempenho | 95% das requisições do painel, do histórico e do relatório respondem em até 2 segundos, com uma base de 30 alunos e 1 ano de registros. | Média |
| RNF04 | Disponibilidade | Sistema disponível em pelo menos 99% do horário de funcionamento da escolinha (de segunda a sexta, das 8h às 19h30), medido mensalmente por monitor externo (no máximo cerca de 2 horas e meia fora do ar por mês nesse horário). O serviço não pode hibernar nem ter partida a frio de mais de 5 segundos. | Média |
| RNF05 | Segurança | Senhas armazenadas com hash seguro e salt (nunca em texto puro), mínimo de 8 caracteres; limite de tentativas de login por usuário e por IP. | Alta |
| RNF06 | Segurança | Toda comunicação usa HTTPS (TLS). | Alta |
| RNF07 | Privacidade | A autorização por vínculo, em que o responsável só acessa os alunos vinculados a ele, é verificada em 100% dos endpoints que retornam dados de aluno, coberta por teste automatizado. | Alta |
| RNF08 | Auditoria | Acessos e alterações em dados de alunos ficam registrados (quem, quando, o quê) e são guardados por 6 meses. | Média |
| RNF09 | Confiabilidade | Backup automático diário do banco, com arquivo criptografado, guardado por 7 dias, com pelo menos 1 teste de restauração antes da entrega. | Média |
| RNF10 | Integridade | Banco relacional com chaves estrangeiras e restrições (ex.: nota entre 0 e 10, prazo não anterior à atribuição). | Alta |
| RNF11 | Acessibilidade | Texto com no mínimo 16 px nas telas do responsável no celular e contraste que atenda ao nível AA das WCAG 2.1. | Média |
