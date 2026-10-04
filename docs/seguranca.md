# Segurança e privacidade

O export original continha tokens GLPI explícitos. **Rotacione o User Token e o App-Token e revogue ou substitua qualquer outra Credential exposta antes de publicar ou ativar o fluxo.** Mascarar o JSON não invalida credenciais antigas.

- Mantenha App-Token, User Token e outras Credentials em armazenamento seguro no n8n; não deixe tokens hardcoded em URLs ou headers.
- Não versione `.env`, exports brutos do n8n, backups, outputs de produção ou arquivos de Credentials. Sanitize cada export antes de publicar.
- Formulários de admissão podem incluir nome, CPF, salário, telefone e outros dados pessoais. Minimize o que é enviado à IA e à notificação, respeite controles de acesso e retenção do ambiente.
- Use apenas dados fictícios em documentação e exemplos. Não publique logs ou payloads de chamados reais.
- Execute uma auditoria de segredos, por exemplo com `gitleaks detect --source .`, antes de enviar alterações públicas.

Os placeholders do JSON são intencionalmente inválidos. Configure o workflow em um ambiente seguro antes da execução.
