# Arquitetura

O n8n é a ponte entre o **GLPI RH** (origem) e o **GLPI Suporte / TI** (destino). O banco MySQL da origem fornece os chamados; o node OpenAI gera a descrição; a API REST do destino cria o Ticket; uma API compatível com WhatsApp notifica; por fim, o MySQL da origem registra o processamento.

```mermaid
flowchart TD
    A[Schedule Trigger] --> B[GLPI RH / MySQL]
    B --> C[Buscar admissões concluídas e não processadas]
    C --> D[OpenAI]
    D --> E[Gerar descrição para TI]
    E --> F[GLPI REST API]
    F --> G[Criar chamado de acessos]
    G --> H[WhatsApp]
    H --> I[Notificar responsável]
    I --> J[Atualizar chamado do RH como processado]
```

A ordem acima descreve o workflow exportado. Falhas intermediárias e múltiplos itens ainda exigem tratamento específico; veja [melhorias futuras](melhorias-futuras.md).
