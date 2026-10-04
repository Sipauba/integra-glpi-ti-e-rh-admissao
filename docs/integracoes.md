# Integrações

| Integração | Papel | Configuração necessária |
| --- | --- | --- |
| n8n | Orquestra o agendamento e os sete nodes | Importar o JSON e associar Credentials |
| MySQL / GLPI RH | Origem e controle dos chamados de admissão | Acesso de leitura e atualização a `glpi_tickets` |
| OpenAI | Converte o formulário em descrição estruturada | Credential OpenAI no n8n |
| GLPI REST API | Inicia sessão e cria Ticket técnico | URL, App-Token, User Token e IDs do ambiente |
| WhatsApp API | Notifica após a criação do chamado | URL, instância, destino e Credential de autenticação |

A API de mensagens do export segue o padrão da Evolution API ou serviço compatível. Configure o destino no seu ambiente. Nenhuma Credential funcional está incluída neste repositório.
