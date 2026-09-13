# Matriz de rastreabilidade de IHC

A matriz deve ser atualizada ao longo do semestre. Ela ajuda a demonstrar que a interface não surgiu arbitrariamente e registra **como o conhecimento da equipe evoluiu**.

Para projetos cujo TCC não previa interface, esta matriz é especialmente importante: deve ficar visível a passagem da **contribuição técnica do TCC** para um **cenário de uso plausível**, e desse cenário para as decisões de interação.

## 1. Derivação do escopo de IHC a partir do TCC

| Elemento | Registro da equipe | Evidência/justificativa | Estado |
|---|---|---|---|
| Tema do TCC | Tecnologias de Machine Learning para Detecção de Intrusões em Redes de Computadores: Uma Pesquisa Exploratória e Experimental | [MVP1](assets\01_dados_mvps\mvp1.pdf) | definido |
| Resultado técnico esperado | Modelo de IA/ML/LLM, estudo/benchmark/avaliação experimental, infraestrutura/backend e sistema embarcado | Treinamento e avaliação de classificadores (Decision Tree) aplicados em pipeline de captura em tempo real e hardware embarcado | definido |
| O TCC previa interface? | Sim | Previsão de um dashboard para monitoramento e gerenciamento da segurança da rede no MVP 2 | definido |
| Capacidade/contribuição central | Identificar e classificar tentativas de invasão cibernética em redes de computadores em tempo real, utilizando número otimizado de atributos | - Fonte: A. Thakkar e R. Lohiya, “A survey on intrusion detection system: feature selection, model, performance measures, application perspective, challenges, and future research directions,” Artificial Intelligence Review, vol. 54, pp. 4529–4593, 2021. doi: 10.1007/s10462-021-10037-9; - Fonte: Z. Azam, M. M. Islam e M. N. Huda, “Comparative Analysis of Intrusion Detection Systems and Machine Learning-Based Model Analysis Through Decision Tree,” 2023. doi: 10.1109/2023.3296444;- Fonte: W. S. Admass, Y. Y. Munaye e A. A. Diro, “Cyber security: State of the art, challenges and future directions,” 2023. doi: 10.1016/2023.10031 | definido |
| Possíveis beneficiários/stakeholders | Analistas de segurança (SOC), administradores de rede, gestores de TI e usuários finais da infraestrutura protegida | {{fonte ou hipótese}} | [H] |
| Usuário escolhido para IHC | Analista de Segurança de Rede (Analista SOC) | Perfil diretamente impactado pela usabilidade do painel, responsável por avaliar alertas de intrusão e conter ameaças sob pressão de tempo | [H] |
| Persona principal | P01 — Rafael Costa | Analista de segurança de rede com foco em operação contínua, alerta e resposta rápida a ameaças | [H] |
| Persona secundária | P02 — Camila Rodrigues | Administradora de rede e infraestrutura, responsável por ajustar parâmetros e monitorar o funcionamento do sistema | [H] |
| Objetivo principal do usuário | Monitorar o tráfego de rede em tempo real para identificar, categorizar e validar anomalias/ataques com agilidade | {{...}} |[H] |
| Contexto de uso adotado | Centros de Operações de Segurança (SOC) ou salas de controle de infraestrutura de TI em empresas e organizações | {{...}} | [H] |
| Interface/recorte de IHC | Dashboard interativo de monitoramento em tempo real com categorização de ataques (DoS, Probe, R2L, U2R) e painel de controle para seleção/chaveamento dos algoritmos de ML | Deriva da necessidade do analista SOC de interpretar rapidamente os resultados do modelo preditivo e controlar o pipeline do IDS em execução | proposta |
| Relação com o TCC | Parte Prevista | O desenvolvimento de um dashboard com indicadores de performance e seleção de algoritmos já faz parte do planejamento do MVP 2 e das entregas do projeto | definido |

> Se o escopo de IHC mudar ao longo do semestre, preserve a decisão anterior no histórico e registre **qual evidência motivou a mudança**.

## 2. Registro de hipóteses e lacunas da Entrega 1

Use esta tabela para itens importantes marcados como `[H]` ou `[?]`. Preserve o histórico: não apague uma hipótese refutada.

<!--| ID | Afirmação / dúvida inicial | Tipo | Por que importa | Como/onde investigar | Evidência obtida | Estado atual | Impacto no projeto |
|---|---|---|---|---|---|---|---|
| H01 | {{...}} | H / ? | {{...}} | Entrega 2 / 3 / 7 / outra | {{link/fonte ou PENDENTE}} | aberta / sustentada / refutada / refinada | {{...}} |
| H02 | {{...}} | H / ? | {{...}} | {{...}} | {{...}} | aberta | {{...}} |-->

| ID | Afirmação / dúvida inicial | Tipo | Por que importa | Como/onde investigar | Evidência obtida | Estado atual | Impacto no projeto |
|---|---|---|---|---|---|---|---|
| H01 | Redução do tempo de resposta a incidentes (MTTR) via painel modular. | H | Valida se a interface realmente agiliza o diagnóstico do analista. | Entrega 2 / 5 (Modelagem de tarefas) | PENDENTE | aberta | Justifica o layout focado em síntese visual. |
| H02 | Viabilidade operacional do sistema em hardware limitado/embarcado. | H | Garante que a interface rode de forma leve na borda (edge). | Entrega 8 (Restrições de Usabilidade) | PENDENTE | aberta | Limita o peso computacional das telas do dashboard. |
| H03 | Mapeamento de perfis diretos (SOC, SysAdmins, Pesquisadores/Gestores). | H | Define os atores centrais da solução interativa. | Entrega 3 (Detalhamento de Perfis) | PENDENTE | aberta | Orienta a arquitetura de navegação do sistema. |
| H04 | Analista de Segurança monitora o tráfego e avalia alertas em tempo real. | H | Identifica o papel operacional de nível 1/2 no SOC. | Entrega 3 / 5 | PENDENTE | aberta | Define as funcionalidades principais do dashboard. |
| H05 | Administrador de Rede ajusta parâmetros de captura e escolhe algoritmos. | H | Identifica o papel administrativo e de infraestrutura. | Entrega 3 / 5 | PENDENTE | aberta | Justifica a existência da tela de configuração/troca de ML. |
| H06 | Gestor de Segurança visualiza relatórios e decide sobre investimentos. | H | Identifica a necessidade de visões consolidadas e executivas. | Entrega 3 / 5 | PENDENTE | aberta | Define os relatórios exportáveis de alto nível. |
| H07 | Analistas necessitam de dados pré-processados mesmo dominando termos técnicos. | H | Evita que a interface exponha dados brutos sem síntese. | Entrega 3 (Perfil de Usuário) | PENDENTE | aberta | Prioriza indicadores gráficos sobre logs brutos. |
| H08 | Em momentos de ataque, a interface deve evitar excesso visual e destacar severidade. | H | Evita sobrecarga cognitiva (*dashboard clutter*) em situações críticas. | Entrega 6 / 8 | PENDENTE | aberta | Guiará a hierarquia visual e o contraste de alertas. |
| H09 | Usuário busca acesso seguro e resposta rápida para evitar vazamento de dados. | H | Mapeia a motivação primária e de negócio do usuário. | Entrega 4 (Situações Problemáticas) | PENDENTE | aberta | Direciona o foco em tempo de reação (MTTR). |
| H10 | Usuário precisa manter a rede operacional mitigando ameaças antes do impacto. | H | Mapeia o objetivo contínuo de proteção da infraestrutura. | Entrega 4 / 5 | PENDENTE | aberta | Define métricas de saúde da rede no topo do painel. |
| H11 | Monitoramento em tempo real (A01) é a atividade mais frequente da rotina. | H | Estabelece qual tela deve ser a visualização padrão. | Entrega 5 (Modelagem de Tarefas) | PENDENTE | aberta | Torna o monitoramento a tela principal (*landing page*). |
| H12 | Investigação de alertas (A02) é a atividade mais crítica para evitar vazamentos. | H | Define onde um erro do usuário traz maiores consequências. | Entrega 4 / 5 | PENDENTE | aberta | Exige fluxos simples de detalhamento de alertas. |
| H13 | Dificuldade de correlacionar métricas brutas sem uma ferramenta visual. | H | Mapeia o gargalo de usabilidade das ferramentas atuais. | Entrega 2 / 4 | PENDENTE | aberta | Justifica o uso de gráficos correlacionados. |
| H14 | Cenário de uso: Cleitin leva 40 minutos filtrando logs cruos durante invasão. | H | Serve de cenário de referência para validar a solução proposta. | Entrega 4 (Cenários de Uso) | PENDENTE | aberta | Avaliará se a nova interface reduz esse tempo. |
| H15 | A interação ocorre em salas de SOC ou estações sob pressão de crise. | H | Mapeia o contexto físico e ambiental de uso. | Entrega 3 (Contexto de Uso) | PENDENTE | aberta | Exige design focado em rápida legibilidade. |
| H16 | O sistema será usado em workstations e monitores conectados a embarcados. | H | Define o porte dos dispositivos de visualização. | Entrega 3 / 8 | PENDENTE | aberta | Direciona o design para telas grandes/desktop. |
| H17 | O ambiente de uso exige uso contínuo com múltiplos monitores e Dark Mode. | H | Mapeia requisitos de conforto visual prolongado. | Entrega 3 / 6 | PENDENTE | aberta | Define o uso de tema escuro como padrão da interface. |
| H18 | Existe hierarquia operacional onde o L1 tria, L2 investiga e Gestor avalia. | H | Organiza os papéis de uso dentro da equipe. | Entrega 3 / 5 | PENDENTE | aberta | Define níveis de profundidade na navegação. |
| H19 | Soluções atuais fazem bem a exibição de gráficos de linha de tempo e filtros. | H | Identifica convenções de mercado que devem ser mantidas. | Entrega 2 (Análise Concorrencial) | PENDENTE | aberta | Aproveita padrões visuais familiares ao usuário. |
| H20 | Soluções atuais pecam por alta complexidade e excesso de alertas irrelevantes. | H | Identifica os pontos fracos dos concorrentes a evitar. | Entrega 2 | PENDENTE | aberta | Foca na redução de ruído visual e falsos alertas. |
| H21 | Usuários estão habituados com gráficos de rosca, KPIs e tabelas coloridas. | H | Define o vocabulário visual e os componentes familiares. | Entrega 2 / 6 | PENDENTE | aberta | Adota componentes gráficos padrão de SOC. |
| H22 | Administração/configurações globais (limites de alerta) fazem sentido. | H | Avalia se a parametrização do sistema cabe no escopo. | Entrega 5 / 7 | PENDENTE | aberta | Define se haverá tela dedicada de limites globais. |
| H23 | Gestão de Usuários/Permissões não é prioridade para o escopo de IHC. | H | Delimita o escopo pedagógico da disciplina. | Entrega 7 (Escopo de Interação) | PENDENTE | aberta | Remove telas de login/perfis do protótipo final. |
| H24 | CRUD tradicional não se aplica ao domínio de tráfego contínuo. | H | Evita aplicação de padrões de interface inadequados ao domínio. | Entrega 5 | PENDENTE | aberta | Descarta formulários CRUD tradicionais no projeto. |
| H25 | Tela de Ajuda/Documentação com guia de ataques pode ajudar iniciantes. | H | Avalia necessidade de suporte instrucional na tela. | Entrega 5 / 6 | PENDENTE | aberta | Define a inclusão de modais ou tooltips explicativos. |
| H26 | A interface reduzirá o tempo de identificação de ataques pelo analista. | H | Define a proposta principal de valor da solução de IHC. | Entrega 12–14 (Avaliação de Usabilidade) | PENDENTE | aberta | Meta de usabilidade para testes com usuários. |
| H27 | A interface trará clareza e transparência na alternância dos modelos de ML. | H | Mede a eficiência do controle modular do pipeline. | Entrega 12–14 | PENDENTE | aberta | Meta de usabilidade para a função de troca de ML. |

## 3. Rastreabilidade entre contribuição técnica, necessidades e artefatos

| ID | Capacidade do TCC utilizada | Necessidade/problema | Persona | Cenário problema | Objetivo/tarefa | HTA/GOMS/CTT | Cenário de interação / signos | MoLIC | Tela(s) Figma | Heurística / problema | Tarefa no teste | Decisão/melhoria |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| R01 | Detecção de intrusão em tempo real com classificação de tráfego | O analista precisa identificar e priorizar ameaças sem examinar logs crus | P01 — Rafael Costa | C01 — alerta de tráfego anômalo durante operação | Monitorar rede e validar incidente | PENDENTE | Dashboard com alertas, severidade e filtros | PENDENTE | PENDENTE | PENDENTE | PENDENTE | Define a tela principal de monitoramento |
| R02 | Modelos de ML para classificação de ataques | O administrador precisa ajustar e monitorar o algoritmo ativo do sistema | P02 — Camila Rodrigues | C02 — mudança de algoritmo/parametrização | Configurar pipeline e validar desempenho | PENDENTE | Configuração de algoritmos e indicadores de desempenho | PENDENTE | PENDENTE | PENDENTE | PENDENTE | Define a área de controle do sistema |
| R03 | Visualização de indicadores e categorização de ameaças | O gestor precisa compreender riscos e evolução do ambiente | P01/P02 | C03 — apresentação de relatório executivo e auditoria | Acompanhar saúde da rede e risco operacional | PENDENTE | Visão resumida com gráficos e histórico | PENDENTE | PENDENTE | PENDENTE | PENDENTE | Apoia a criação de relatórios e dashboards executivos |

Use esta tabela quando o projeto incorporar padrões como dashboard, relatório, histórico, filtros ou administração. O objetivo é **justificar o padrão**, não apenas listar telas.

| ID da tela/fluxo | Padrão de interface | Objetivo/tarefa que justifica | Informação/ação principal | Evidência de necessidade | Artefatos relacionados |
|---|---|---|---|---|---|
| F01 | dashboard | {{T01}} | {{...}} | {{H01/evidência...}} | {{C01/M01}} |
| F02 | histórico com filtros | {{T02}} | {{...}} | {{...}} | {{...}} |
| F03 | administração/CRUD | {{T03}} | {{...}} | {{...}} | {{...}} |

## 5. Registro de mudanças de escopo

| Data | O que mudou | Evidência/feedback que motivou | Artefatos afetados | Responsável |
|---|---|---|---|---|
| {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |

## Como usar

- Use identificadores estáveis (`H01`, `P01`, `C01`, `T01`, `M01`, `F01`, `UT01`).
- Quando uma necessidade/problema tiver origem em hipótese da Entrega 1, cite o ID correspondente.
- Em TCC sem interface original, pelo menos uma linha deve mostrar claramente **como uma capacidade técnica chega até uma tarefa de usuário e uma tela/fluxo**.
- Uma linha pode se desdobrar quando um objetivo possui múltiplos caminhos.
- Não force relação inexistente: se algo ainda não foi modelado, marque `PENDENTE`.
- Ao remover uma funcionalidade, registre a decisão em vez de apagar silenciosamente o histórico.
- Dashboard, CRUD, filtros e relatórios só devem aparecer quando houver objetivo/tarefa que os justifique.
