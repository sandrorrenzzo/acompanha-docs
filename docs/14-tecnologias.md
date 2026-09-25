# 14 — Tecnologias

> Projeto Acompanha (TIAPN, PUC Minas Contagem). Tecnologias escolhidas e por quê. Índice geral: [README](../README.md).

- **Aplicação web:** interface em React, publicada no Cloudflare Pages (plano gratuito).
- **Banco de dados:** PostgreSQL relacional no Supabase (plano gratuito, região São Paulo), com chaves estrangeiras e restrições de integridade.
- **Autenticação e autorização:** Supabase Auth (senhas com hash bcrypt) e políticas Row Level Security no banco, que garantem que cada responsável só leia os dados dos próprios filhos.
- **Backup e versionamento:** código no GitHub e backup diário do banco por rotina agendada no GitHub Actions.
