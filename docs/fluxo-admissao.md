# Fluxo de admissão

A consulta em `glpi_tickets` filtra uma categoria de admissão (`itilcategories_id`), chamados em status elegíveis e `notifica_glpi_ti = 0`. O valor `9999` publicado para a categoria é fictício. O SQL de seleção e atualização preserva as condições e referências do fluxo original, com essa única substituição de literal.

O node **Gera Conteúdo Chamado** recebe o conteúdo do formulário, que pode estar em HTML, texto ou JSON. O prompt existente pede para identificar os campos encontrados dinamicamente e gerar uma descrição legível. Ele orienta a remover HTML, manter nomes de campos quando possível, incluir campos novos, deixar ausências sem preenchimento e não inventar informações. Isso permite lidar com alterações futuras no formulário sem fixar uma lista de campos no workflow.

Após criar o Ticket no GLPI de suporte e enviar a mensagem, a consulta `UPDATE` define `notifica_glpi_ti = 1` no chamado de origem. O valor `0` indica pendência; `1`, processamento. O campo pode ser customizado e precisa existir no banco de origem. A sequência atual não garante idempotência nem confirmação transacional entre os sistemas.
