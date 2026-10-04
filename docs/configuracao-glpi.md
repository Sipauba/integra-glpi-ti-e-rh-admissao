# Configuração do GLPI

## Origem: GLPI RH

Forneça ao n8n uma Credential MySQL com acesso mínimo necessário a `glpi_tickets`. A consulta usa `itilcategories_id`, `status` e `notifica_glpi_ti`; a atualização altera `notifica_glpi_ti`. Esse último campo **pode ser uma customização**, não uma coluna padrão do GLPI. Crie e configure o campo no seu ambiente, se necessário, e confira as permissões de leitura e atualização. Substitua o ID fictício `9999` da categoria na consulta.

## Destino: GLPI Suporte / TI

Habilite a API REST e configure URL, App-Token e User Token em armazenamento seguro. O workflow inicia sessão em `initSession` e abre um `Ticket`. Substitua os IDs `9999` do payload pelos IDs próprios do seu ambiente: entidade (`GLPI_ENTITY_ID`), solicitante (`GLPI_REQUESTER_ID`), categoria (`GLPI_CATEGORY_ID`), SLA (`GLPI_SLA_ID`) e tipo de requisição (`GLPI_REQUEST_TYPE_ID`). Revise também `type`, `status`, `urgency`, `impact` e `priority`.

O arquivo `.env.example` enumera parâmetros, mas **não parametriza automaticamente o JSON**. Depois da importação, atribua Credentials de n8n e configure manualmente os campos dos nodes antes de ativar o fluxo. Nunca publique um export que contenha tokens ou URLs reais.
