# Sistema de Automação de Emails com Google Apps Script

Automação de envio de emails utilizando Google Apps Script integrada ao Google Sheets

# Descrição
 A planilha era utilizada pela equipe de atendimento e backoffice para registrar, monitorar e direcionar reclamações de clientes para as lojas responsáveis pelas vendas, incluindo franquias. Além disso, os dados registrados eram utilizados para análises internas e reuniões.
 Inicialmente, todo o processo era manual, desde o preenchimento das informações até o envio dos emails para as lojas, o que demandava tempo da equipe e reduzia a capacidade de análise e resolução dos casos.
 Para solucionar esse problema, foi desenvolvida uma automação utilizando Google Apps Script integrada ao Google Sheets, permitindo que, a partir dos dados preenchidos na planilha, os  emails fossem enviados automaticamente conforme a solicitação do cliente, através de gatilhos programados.
 Como funcionalidades adicionais, o sistema registra automaticamente o link do email enviado em uma coluna da planilha, permitindo o acompanhamento das tratativas. Também foi implementado um controle de SLA com base no tempo de resposta, utilizando cores para facilitar a visualização, além de uma regra de limitação de execução baseada em período.
 Além disso, foi integrada uma API que, a partir do número do pedido, permite buscar automaticamente informações como a loja responsável e o telefone do cliente, reduzindo erros de preenchimento e otimizando o tempo do atendente.

# Funcionalidades
- Envio automático de emails com base em gatilho executado a cada 5 minutos
- Personalização do conteúdo dos emails de acordo com os dados da planilha 
- Controle de envio através de status ("Pendente" e "Enviado") para evitar duplicidade
- Bloqueio de envio para linhas incompletas (campo em branco como segurança)
- Atualização automática do status para "Enviado" após disparo do email
- Registro do link do email enviado diretamente na planilha para acompanhamento 
- Controle de SLA com base em tempo de resposta, utilizando indicadores visuais
- Integração com API para preenchimento automático de dados a partir do número do pedido

# Fluxo do sistema
• O atendente preenche os dados na planilha
• Define o status como "Pendente"
• O gatilho automático executa o script a cada 5 minutos
• O sistema valida as condições (status e campos de preenchimento)
• O email é gerado e enviado automaticamente 
• O status é atualizado para "Enviado"
• O link do email é registrado na planilha 
• O sistema continua monitorando resposta e SLA

# Tecnologias 
- Google Apps Script
- Google Sheets
- Gmail
- API (integração para consulta de dados via número do pedido - VTEX)

# Impacto
- Redução significativa do tempo gasto com envio manual de emails
- Eliminação da necessidade de dividir o trabalho entre envio e análise 
- Maior foco da equipe na tratativa e resolução dos casos
- Redução de erros de preenchimento com uso de API
- Melhoria na organização e acompanhamento dos atendimentos 

# Diferenciais 
- Uso de controle por status para evitar reprocessamento de dados
- Implementação de execução em blocos (200 linhas) para evitar limite de tempo do Apps Script
- Otimização de processamento considerando apenas registros recentes (até 20 dias)
- Integração com API para automação de preenchimento de dados críticos
