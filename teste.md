# Entrega 3 — Personas, mapa de empatia, contexto de uso e jornada

**Data:** 27/08/2026  
**Status:** 🟩 concluída  
**Responsabilidade:** 1 persona por integrante; 1 mapa de empatia, 1 contexto de uso consolidado e 1 jornada por equipe (salvo orientação diferente do docente).

## Objetivo da atividade

Representar grupos de usuários de forma útil para decisões de design. Persona não é personagem decorativo: suas características devem alterar requisitos, prioridades, linguagem, fluxos ou critérios de avaliação.

## Atenção a projetos técnicos

Em TCCs sem interface original, a persona pode representar um **profissional que se apropria da contribuição técnica**: DBA, analista, cientista de dados, administrador, pesquisador, técnico, operador, gestor ou especialista de domínio.

Não escolha um perfil apenas porque “parece combinar” com a tecnologia. Explique **qual objetivo esse perfil teria e qual parte da contribuição do TCC produziria valor para ele**. Se ainda for hipótese, mantenha como hipótese/proto-persona a validar.

Também considere papéis diferentes quando houver tarefas distintas, por exemplo:

- operador que executa análises;
- administrador que configura e gerencia permissões;
- especialista que interpreta resultados;
- gestor que consulta relatórios e decide;
- auditor que revisa histórico.

## Entradas da Entrega 1

Antes de criar personas, retome os tipos de usuários, características relevantes, objetivos e hipóteses registradas na Entrega 1. A persona **não deve transformar uma hipótese inicial em fato por meio de uma história fictícia**.

| Item da Entrega 1 | Status inicial | Evidência disponível agora | Como será tratado nesta entrega |
|---|---|---|---|
| H03 — perfis diretos (SOC, SysAdmins, Gestores) | H | O projeto prevê analistas, administradores e gestores como atores relevantes do processo de segurança de rede | incorporado como base das personas P01 e P02 |
| H04 — analista monitora tráfego e interpreta alertas em tempo real | H | A atividade de monitoramento é a mais frequente e crítica, conforme A01 e A02 | base para a persona primária P01 |
| H05 — administrador ajusta parâmetros de captura e algoritmo | H | A configuração de pipeline e seleção de modelos é tarefa individual do ambiente de operação | base para a persona secundária P02 |
| H06 — gestor avalia relatórios e decide investimentos | H | Existe necessidade de visão consolidada e relatórios executivos | mantido como stakeholder, mas não como foco principal do design |
| H07 — usuários entendem termos técnicos, mas precisam de síntese visual | H | A análise concorrencial reforça a necessidade de dashboards e filtros por severidade | incorporado aos requisitos da interface |
| H08 — em crise, o sistema deve reduzir ruído visual e priorizar severidade | H | Fortinet e Wazuh usam painéis com priorização visual e filtros hierárquicos | orienta o design da persona P01 |
| H15–H18 — contexto operacional, hardware, Dark Mode e hierarquia de papéis | H | O uso ocorre em SOCs e estações de trabalho com pressão de tempo e múltiplos monitores | incorporado ao contexto de uso |

## 1. Personas

### Persona P01 — Rafael Costa

**Autor(a):** Lucas Kerr do Amaral — 22.123.032-9  
**Tipo:** primária  
**Base de evidências:** proto-persona a validar com base em literatura, análise concorrencial e hipóteses da Entrega 1 (H03, H04, H07, H08, H11, H12, H15–H18)  
**Hipóteses da Entrega 1 relacionadas:** H03, H04, H07, H08, H11, H12, H15, H16, H17, H18

![Persona P01](../assets/03_personas/persona_p01.svg)

| Campo | Descrição |
|---|---|
| Faixa etária / contexto relevante | 28 a 42 anos, trabalha em ambientes corporativos ou de prestação de serviços de segurança com alta carga operacional. |
| Ocupação/papel | Analista de Segurança de Rede / SOC L1-L2, responsável por monitorar o tráfego, validar alertas e priorizar intervenções. |
| Conhecimento do domínio | Alto conhecimento em redes, protocolos, portas, tráfego e indicadores de segurança; compreende termos técnicos como SYN, pacotes, origem/destino e categorias de ataque. |
| Experiência tecnológica | Familiarizado com dashboards de segurança, SIEMs, IDS/IPS, ferramentas de linha de comando e visualização de logs. |
| Objetivos | Monitorar a rede em tempo real, identificar anomalias rapidamente, classificar incidentes e reduzir o tempo de resposta a ataques. |
| Necessidades | Visualização resumida de alertas e métricas, filtros por severidade e origem, correlação rápida entre indicadores e contexto do evento. |
| Dores/frustrações | Volume elevado de dados, logs pouco legíveis, falsos positivos e atraso na análise de uma intrusão em curso. |
| Motivadores | Manter a infraestrutura disponível, reduzir MTTR e aumentar confiança na decisão de contenção. |
| Restrições/acessibilidade | Precisa de leitura rápida em telas grandes, com contraste adequado e pouca sobrecarga visual; trabalha em condições de pressão e atenção prolongada. |
| Ambiente típico de uso | Sala de operação de segurança, estação de trabalho com múltiplos monitores e acesso a ferramentas de monitoramento e rede. |
| Comportamentos relevantes | Prioriza alertas críticos, filtra por origem e destino, compara métricas em dashboards e compara categoria de ataque com contexto operacional. |

**Decisões de design influenciadas por P01:**

- Priorizar a tela de monitoramento e alertas como visão principal da interface.
- Usar indicadores de severidade, filtros por categoria e origem/destino para reduzir sobrecarga cognitiva.
- Apresentar síntese visual em vez de logs brutos como elemento principal.
- Permitir investigação progressiva, do resumo para o detalhamento do evento.

### Persona P02 — Camila Rodrigues

**Autor(a):** Marcela Nalesso — 22.222.011-3  
**Tipo:** secundária  
**Base de evidências:** proto-persona a validar com base em hipóteses da Entrega 1 (H05, H16, H17, H18), análise de concorrência e contexto de uso operacional  
**Hipóteses da Entrega 1 relacionadas:** H05, H16, H17, H18

![Persona P01](../assets/03_personas/persona_p01.svg)

| Campo | Descrição |
|---|---|
| Faixa etária / contexto relevante | 30 a 45 anos, atua em empresas com infraestrutura de rede e ambiente digital crítico. |
| Ocupação/papel | Administradora de Rede e Infraestrutura / responsável por configurar o pipeline de monitoramento e os algoritmos de classificação. |
| Conhecimento do domínio | Conhecimento médio-alto em arquitetura de rede, servidores, políticas de segurança e operação de sistemas críticos. |
| Experiência tecnológica | Experimentada em operação de servidores, ferramentas de monitoramento e manutenção de infraestrutura de segurança. |
| Objetivos | Ajustar parâmetros de captura, validar o desempenho dos modelos e manter a plataforma operacional e segura. |
| Necessidades | Configuração clara, visão de performance do sistema, parametrização sem excesso de complexidade e capacidade de comparar modelos. |
| Dores/frustrações | Dificuldade em compreender o impacto de mudanças de configuração, excesso de opções técnicas e necessidade de configurar cenários em ambiente crítico. |
| Motivadores | Garantir disponibilidade da rede, manter o sistema em operação e aumentar confiança no modelo de detecção. |
| Restrições/acessibilidade | Requer operações seguras, atualização controlada e entendimento do impacto das decisões em ambiente produtivo. |
| Ambiente típico de uso | Estação de trabalho do administrador, acesso a servidores ou plataforma embarcada, com necessidade de monitoramento contínuo. |
| Comportamentos relevantes | Explora parâmetros do sistema, compara métricas de execução e prioriza estabilidade do ambiente sobre experimentação excessiva. |

**Decisões de design influenciadas por P02:**

- Incluir uma área de configuração funcional, com parâmetros essenciais e visibilidade do estado do sistema.
- Exibir métricas de desempenho do modelo e da infraestrutura para facilitar ajustes sem ambiguidade.
- Sustentar a ideia de painel modular, permitindo configuração do algoritmo ativo de forma simples e segura.

### Síntese das personas

As personas apresentam papéis distintos, mas complementares. P01 é a persona prioritária porque representa o uso mais frequente e crítico do sistema: monitorar, interpretar e agir rapidamente diante de ameaças reais em tempo real. P02 representa a administração e ajuste do sistema, definindo requisitos de configuração e estabilidade operacional. A diferença central entre elas está na orientação da tarefa: P01 prioriza rapidez e decisão sob pressão; P02 prioriza controle, parametrização e desempenho do ambiente. Isso evita a criação de personas redundantes e assegura que o design atenda tanto à operação quanto à governança técnica.

## 2. Mapa de empatia — equipe

**Persona escolhida:** P01  
**Justificativa:** P01 concentra o caso de uso mais crítico e frequente da proposta, em que o analista precisa interpretar rapidamente sinais de intrusão e decidir sem perder tempo. Esse perfil é o mais relevante para validar a usabilidade do dashboard e a prioridade de informação.

![Mapa de empatia](../assets/03_personas/mapa_empatia.svg)

Documentação em texto do mapa de empatia:

- O que vê: fluxo de rede em tempo real, indicadores de tráfego, alertas por severidade, origem/destino, gráficos de categoria de ataque e painel de saúde da rede.
- O que ouve: relatos de lentidão, falhas funcionais, alertas de analistas, solicitações de contenção e observações operacionais sobre incidentes em andamento.
- O que diz/faz: “vou filtrar por origem do ataque”, “preciso confirmar se é um falso positivo”, “vou priorizar os alertas críticos”, “preciso reduzir o tempo de resposta”.
- O que pensa/sente: os minutos importam, há pressão para decidir, o risco de erro é alto e o sistema precisa mostrar informações com clareza.
- Dores: sobrecarga de logs, ruído visual, dificuldades de correlação entre alertas e contexto, risco de falso negativo ou atraso.
- Ganhos: redução do MTTR, maior segurança operacional, confiança no diagnóstico, foco no que realmente importa e menor esforço mental.

**Evidência vs hipótese:**

- Evidência: a atividade A01 (monitoramento) é a mais frequente; A02 (gerenciamento de alerta) é a mais crítica; há necessidade de síntese visual para correlacionar métricas brutas e priorizar severidade.
- Hipótese: a interface deve reduzir a carga cognitiva, oferecer tema escuro e permitir resposta rápida em situações de crise; isso ainda precisa ser validado em avaliações e testes com usuários.

## 3. Contexto de uso — consolidação

| Dimensão | Descrição | Implicação de design |
|---|---|---|
| Usuários | Analistas de segurança e administradores de rede atuando em operação contínua de monitoramento e resposta a incidentes. | A interface deve atender a operações repetitivas e exigentes, com foco em ação rápida e clareza visual. |
| Tarefas | Monitorar fluxo de rede, identificar anomalias, investigar alertas, classificar categoria de ataque e ajustar parâmetros do sistema. | O sistema deve oferecer fluxos de leitura rápida, detalhamento progressivo e configuração simples de parâmetros críticos. |
| Equipamentos | Estações de trabalho com monitores de alta resolução e acesso a infraestrutura de rede e embarcados de processamento. | O design deve priorizar telas desktop, alta legibilidade e uso em múltiplos monitores. |
| Ambiente físico | SOC, salas de TI e ambientes de operação com iluminação controlada e pressão por respostas rápidas. | O layout deve ter contraste adequado, visual limpo e suporte ao uso contínuo em modo escuro. |
| Ambiente social/organizacional | Hierarquia operacional em que analista L1 contextualiza alertas, L2 investiga e gestores validam impactos. | A interface deve permitir diferentes níveis de profundidade sem perder a leitura do contexto principal. |
| Papéis/permissões/governança | O analista atua em resposta operacional, o administrador controla a infraestrutura e o gestor acompanha a segurança do ambiente. | O sistema deve diferenciar papel e acesso sem sobrecarregar a navegação principal. |
| Volume de dados/histórico | Há grande quantidade de tráfego e registros históricos para auditoria, classificação e correlação de eventos anteriores. | O painel deve agrupar eventos e permitir histórico filtrado, em vez de mostrar dados brutos como primeira linha de visão. |

## 4. Jornada do usuário — equipe

**Persona:** P01  
**Objetivo da jornada:** Confirmar e mitigar uma anomalia ou tentativa de intrusão antes que ela comprometa a disponibilidade, integridade ou confidencialidade da rede.  
**Início e fim da jornada:** A jornada começa quando o analista percebe lentidão, alerta ou sinal de risco no ambiente e termina quando a ameaça é classificada, investigada e contida ou descartada com evidência.

| Etapa | Situação/ação | Objetivo | Pensamento/emoção | Dor | Oportunidade de design | Evidência |
|---|---|---|---|---|---|---|
| 1 | O analista observa um pico de tráfego ou alerta de segurança na estação de operação | Detectar rapidamente que algo está fora do normal | “Há alguma anomalia sendo gerada?” | O evento pode ser confundido com uso legítimo, sem contexto imediato | Indicadores principais e alertas de severidade devem ser visíveis no primeiro carregamento | H11, H12, H13 |
| 2 | O analista abre o dashboard de monitoramento | Entender se a ocorrência é relevante e qual é a gravidade | “Preciso saber se isso é um ataque real” | Muitos dados sem hierarquia impedem a leitura rápida | Painel com síntese visual, categoria de ataque e severidade priorizada | H07, H08, Wazuh/Fortinet |
| 3 | Ele investiga origem, destino, tráfego e categoria do evento | Correlacionar o alerta ao contexto real da rede | “Qual é a natureza do evento?” | A ausência de filtros e contexto obriga análise manual dos logs | Filtros por origem, destino e categoria; detalhamento progressivo | H04, H12 |
| 4 | O analista valida se é um falso positivo ou uma intrusão real | Tomar decisão segura e rápida de contenção | “Não posso agir sem certeza” | A interpretação incorreta causa prejuízos e tempo perdido | Exibir confiança do modelo, contexto e status do evento com clareza | H04, H09, H12 |
| 5 | O analista decide a ação de resposta e acompanha a evolução do problema | Contener a ameaça e manter a rede operacional | “Preciso reverter o impacto sem interromper o negócio” | Falta de rastreabilidade e resposta lenta agravam a situação | Histórico, evolução temporal e painel de estado da rede | H14, H15, H18 |
| 6 | O alerta é encerrado, registrado e pode ser revisado posteriormente | Aprender com o incidente e melhorar a operação | “Tenho uma base para auditoria e melhoria” | Ausência de rastreio dificulta a análise pós-incidente | Histórico e documentação de ações no sistema | H05, H18 |

## Síntese

As necessidades que devem aparecer obrigatoriamente nos cenários e nas tarefas seguintes são:

- monitorar a rede com atenção contínua e legibilidade imediata;
- interpretar uma anomalia em poucos segundos ou minutos, sem depender de logs brutos;
- priorizar alertas por severidade e risco operacional;
- correlacionar origem, destino, categoria e contexto para decidir sobre contenção;
- reduzir a sobrecarga cognitiva em situações de crise;
- manter rastreabilidade e evolução do evento para auditoria e resposta.

Esses requisitos orientam diretamente o design de dashboard, filtros, alertas, histórico e indicadores de resposta à intrusão.

## Checklist

- [x] Existe pelo menos uma persona por integrante.
- [x] As personas não são apenas diferenças demográficas superficiais.
- [x] Está claro o que é dado real e o que é hipótese/proto-persona.
- [x] A persona não “validou por ficção” uma hipótese da Entrega 1; afirmações continuam marcadas como hipótese quando não há evidência.
- [x] Objetivos e dores têm consequência para o design.
- [x] Contexto de uso está coerente com a Entrega 1.
- [x] Em TCC sem interface original, a persona possui relação explícita com a contribuição técnica.
- [x] Papéis administrativos, técnicos e decisórios só foram criados quando possuem objetivos/tarefas diferentes.
- [x] Jornada possui etapas, dores e oportunidades e não é apenas wireflow.
- [x] IDs das personas foram adicionados à rastreabilidade.
