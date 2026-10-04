# Melhorias futuras

As sugestões abaixo **não foram implementadas** nesta versão de preservação e documentação.

- Mover tokens hardcoded para Credentials e usar uma Credential específica para o GLPI; parametrizar IDs, categoria de admissão e destino de notificação.
- Tratar falhas e resposta vazia da OpenAI, falhas da API do GLPI e da notificação; adicionar retry controlado e encerrar a sessão GLPI quando aplicável.
- Registrar os IDs dos chamados de origem e destino, processar múltiplos itens com segurança, evitar duplicatas e garantir idempotência.
- Condicionar a atualização de `notifica_glpi_ti` à execução bem-sucedida da IA, da sessão GLPI, da criação do Ticket e do envio da notificação ou tratamento explícito de sua falha.
- Adicionar logs estruturados, observabilidade, auditoria, sub-workflows e testes automatizados.
- Minimizar e proteger dados pessoais em prompts, mensagens, logs e retenção.
