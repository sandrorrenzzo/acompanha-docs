# 12 — Restrições e escopo

> Projeto Acompanha (TIAPN, PUC Minas Contagem). Limites legais, de custo, hospedagem e equipamentos, e o que fica fora desta versão. Índice geral: [README](../README.md).

| ID | Tipo | Restrição |
|---|---|---|
| R01 | Legal | O tratamento de dados de crianças e adolescentes deve seguir a LGPD (Lei 13.709/2018), em especial o art. 14: melhor interesse da criança, consentimento específico e destacado de pelo menos um dos pais ou responsável legal, e informação pública e simples sobre os dados coletados. |
| R02 | Custo | A parceira não tem orçamento para software: a solução deve ter custo mensal zero, durante e depois da disciplina. Qualquer serviço pago só pode ser adotado com aprovação prévia da proprietária. |
| R03 | Hospedagem | Banco PostgreSQL e autenticação no Supabase (plano gratuito, região São Paulo) e aplicação web no Cloudflare Pages (plano gratuito, permite uso comercial e não hiberna). Foram descartados o Vercel Hobby (uso apenas não comercial) e o plano gratuito do Render (hiberna após 15 minutos e o banco expira em 30 dias). As contas serão criadas no e-mail da escolinha, que passa a ser a dona dos dados e dos serviços depois da disciplina. Risco conhecido: o Supabase pausa projetos gratuitos após 7 dias sem uso (ex.: férias); o guia de uso explica como reativar. |
| R04 | Equipamentos | O sistema roda no navegador, sem instalação, nos equipamentos que as professoras e as famílias já têm: Android 10 ou superior, iOS 15 ou superior e Windows 10 ou superior, nas duas versões mais recentes de Chrome, Edge e Safari, e com conexão móvel 4G. Nenhum equipamento novo será comprado. |
| R05 | Tecnologia | A disciplina exige sistema web com banco de dados relacional. |
| R06 | Prazo | O desenvolvimento está limitado ao cronograma da disciplina (semestre 2026). |
| R07 | Manutenção | A equipe não garante suporte depois da disciplina; por isso o sistema deve ser simples de operar e entregue com um guia de uso para as professoras. |

## Fora do escopo

- Módulo financeiro (mensalidades, pagamentos).
- Envio automático de mensagens por e-mail ou WhatsApp (possível trabalho futuro).
- Várias unidades ou escolas no mesmo sistema (multi-unidade).
- Acesso dos próprios alunos ao sistema.
