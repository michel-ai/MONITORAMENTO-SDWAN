📊 SD-WAN Network Monitoring Dashboard
Este projeto consiste em um Dashboard unificado de monitoramento de infraestrutura SD-WAN, desenvolvido para centralizar a visibilidade de conectividade, incidentes e abertura de chamados de múltiplos centros operacionais do Governo do Estado do Pará.

O painel integra dados de saúde de rede de ponta a ponta, unificando a camada física (links de operadoras), monitoramento ativo de ativos e a camada de governança/chamados.

<img width="1869" height="976" alt="image" src="https://github.com/user-attachments/assets/ece04381-0993-41bc-b392-2713a1d3795c" />


🚀 Principais Funcionalidades
Visão Consolidada de Unidades (SD-WAN): Status em tempo real de links (UP/DOWN), consumo de banda, perda de pacotes e latência de operadoras como Claro, Starlink e redes locais (Prodepa).

Geolocalização dos Nós: Mapa interativo integrado mostrando a distribuição geográfica e o status de conectividade das unidades no estado.

Gestão de Incidentes (Zabbix): Painel interno que consome a API do Zabbix para exibir alertas críticos (High, Disaster), tempo de duração do incidente (Age) e histórico de problemas resolvidos nos últimos 15 dias.

Integração com ITSM / Operadoras: Exibição direta de chamados abertos via Jira e Claro GRC (exemplo: acompanhamento do Ticket #9801986 da Claro para a unidade UECOMT AEROPORTO).

Filtros Avançados de Busca: Agrupamento rápido por Horário de Funcionamento, Sede ou Designação do link.

🛠️ Arquitetura e Integrações
O ecossistema do dashboard é alimentado por três pilares principais:


┌────────────────────────┐      ┌────────────────────────┐      ┌────────────────────────┐
│     Zabbix API         │      │     Claro GRC API      │      │     Jira Service Desk  │
│ (Métricas de Rede/SLA) │      │ (Chamados de Link/Wan) │      │ (Incidentes Internos)  │
└───────────┬────────────┘      └───────────┬────────────┘      └───────────┬────────────┘
            │                               │                               │
            └───────────────────────────────┼───────────────────────────────┘
                                            ▼
                             ┌─────────────────────────────┐
                             │    Dashboard SD-WAN Core    │
                             └─────────────────────────────┘


Monitoramento (Zabbix): Coleta ativa de Health-Checks das interfaces WAN e latência de equipamentos FortiGate.

Provedores (Claro GRC): Sincronização automatizada para trazer o status do posicionamento técnico da operadora (EM RESOLUÇÃO, NOVO ITEM).

Filtros Dinâmicos: Classificação por metadados das unidades (ex: horários operacionais de funcionamento como 08h - 17h).

📸 Demonstração do Painel
Visão Geral do Dashboard
O painel exibe cartões dinâmicos para cada localidade com múltiplos links redundantes. No exemplo, o nó UECOMT AEROPORTO aponta um alerta de falha no link principal da Claro, operando pelo link de contingência.

Central de Incidentes (Zabbix) & Chamados Claro GRC
Detalhamento de problemas ativos categorizados por severidade e a janela de acompanhamento direto com a operadora Claro.

|

Visualização em Mapa Geográfico
Mapeamento dos pontos de presença (PoPs) ativos no território.

🧑‍💻 Tecnologias e Conceitos Aplicados
Monitoramento de Redes: ICMP Jitter, Perda de Pacotes, Latência de Redes Anycast/SD-WAN.

Segurança de Borda: Monitoramento de appliances FortiGate.

UX/UI para Operações (NOC): Desenvolvimento focado em painéis de alta criticidade (Dark Mode para redução de fadiga visual, código de cores baseado no padrão ITIL de severidade).

📄 Licença
Este dashboard é de uso institucional e as imagens foram anonimizadas/protegidas para fins de exibição de portfólio de engenharia de redes.
