# Matriz de rastreabilidade de IHC

> **Revisada em 03/10/2026** a partir dos feedbacks das Entregas [01](Feedback_Professor_Entrega01_Equipe21.md), [02](Feedback_Professor_Entrega02_Equipe21.md) e [03](Feedback_Professor_Entrega03_Equipe21.md). Três coisas que antes se misturavam passaram a ser distinguidas em todos os registros: **decisão de projeto** (a equipe escolheu assim), **refinamento de hipótese** (a afirmação ficou mais precisa) e **evidência obtida** (alguém verificou). Uma decisão de recorte **não refuta** uma hipótese sobre o domínio.

A matriz deve ser atualizada ao longo do semestre. Ela ajuda a demonstrar que a interface não surgiu arbitrariamente e registra **como o conhecimento da equipe evoluiu**.

Para projetos cujo TCC não previa interface, esta matriz é especialmente importante: deve ficar visível a passagem da **contribuição técnica do TCC** para um **cenário de uso plausível**, e desse cenário para as decisões de interação.

## 1. Derivação do escopo de IHC a partir do TCC

| Elemento | Registro da equipe | Evidência/justificativa | Estado |
|---|---|---|---|
| Tema do TCC | Tecnologias de Machine Learning para Detecção de Intrusões em Redes de Computadores: Uma Pesquisa Exploratória e Experimental | [MVP1](assets/01_dados_mvps/mvp1.pdf) | definido |
| Resultado técnico esperado | Modelo de IA/ML/LLM, estudo/benchmark/avaliação experimental, infraestrutura/backend e sistema embarcado | Treinamento e avaliação de classificadores (Decision Tree) aplicados em pipeline de captura em tempo real e hardware embarcado | definido |
| O TCC previa interface? | Sim | Previsão de um dashboard para monitoramento e gerenciamento da segurança da rede no MVP 2 | definido |
| Capacidade/contribuição central | Identificar e classificar tentativas de invasão cibernética em redes de computadores em tempo real, utilizando número otimizado de atributos | - Fonte: A. Thakkar e R. Lohiya, “A survey on intrusion detection system: feature selection, model, performance measures, application perspective, challenges, and future research directions,” Artificial Intelligence Review, vol. 54, pp. 4529–4593, 2021. doi: 10.1007/s10462-021-10037-9; <br> - Fonte: Z. Azam, M. M. Islam e M. N. Huda, “Comparative Analysis of Intrusion Detection Systems and Machine Learning-Based Model Analysis Through Decision Tree,” 2023. doi: 10.1109/2023.3296444; <br> - Fonte: W. S. Admass, Y. Y. Munaye e A. A. Diro, “Cyber security: State of the art, challenges and future directions,” 2023. doi: 10.1016/2023.10031 | definido |
| Possíveis beneficiários/stakeholders | Analistas de segurança (SOC), administradores de rede, gestores de TI e usuários finais da infraestrutura protegida | Entrega 1 / 3 | definido |
| Usuário escolhido para IHC | Analista de Segurança de Rede (analista SOC) — **P01, prioritário no fluxo de investigação**. A administradora de infraestrutura (**P02**) é **primária no fluxo de configuração** | Perfil diretamente impactado pela usabilidade do painel, responsável por interpretar ocorrências e **encaminhar** a resposta sob pressão de tempo. **Não executa a contenção** — ver Entrega 01, quadro no fim da seção 2. A justificativa das duas personas primárias está na Entrega 03, 1.3 | definido (decisão de projeto) |
| Objetivo principal do usuário | **P01:** interpretar uma conexão sinalizada e decidir o encaminhamento (descartar, confirmar ou escalar). **P02:** saber o efeito de uma mudança de configuração antes de aplicá-la | Entrega 01, 7.3 / Entrega 03, 1.3 | definido (decisão de projeto) |
| Contexto de uso adotado | SOC e salas de controle de TI; **também plantão remoto (home office)**, com um único monitor e iluminação não controlada | Entrega 03, seção 3 — **contexto suposto**, nenhuma observação de campo foi realizada | proposta (hipótese) |
| Interface/recorte de IHC | **Área de investigação** (observar o estado da rede; inspecionar uma conexão sinalizada com categoria, confiança e critério; registrar a decisão) e **área de configuração**, separada, para o classificador ativo. **Fora do recorte:** executar bloqueio ou isolamento | Deriva da necessidade de P01 de interpretar o resultado do modelo e da de P02 de alterar o sistema sabendo a consequência | proposta |
| Relação com o TCC | Parte Prevista | O desenvolvimento de um dashboard com indicadores de performance e seleção de algoritmos já faz parte do planejamento do MVP 2 e das entregas do projeto | definido |

> Se o escopo de IHC mudar ao longo do semestre, preserve a decisão anterior no histórico e registre **qual evidência motivou a mudança**.

## 2. Registro de hipóteses e lacunas da Entrega 1

Use esta tabela para itens importantes marcados como `[H]` ou `[?]`. Preserve o histórico: não apague uma hipótese refutada.

<!--| ID | Afirmação / dúvida inicial | Tipo | Por que importa | Como/onde investigar | Evidência obtida | Estado atual | Impacto no projeto |
|---|---|---|---|---|---|---|---|
| H01 | {{...}} | H / ? | {{...}} | Entrega 2 / 3 / 7 / outra | {{link/fonte ou PENDENTE}} | aberta / sustentada / refutada / refinada | {{...}} |
| H02 | {{...}} | H / ? | {{...}} | {{...}} | {{...}} | aberta | {{...}} |-->

> **Sobre a coluna “O que foi efetivamente obtido”:** ela registra apenas o que foi **verificado**, com a fonte. Quando nada foi verificado, isso é dito com todas as letras — “PENDENTE” ou “Nada”. Decisões de projeto e refinamentos de redação aparecem identificados como tais, para não serem confundidos com evidência.

**Vocabulário dos estados** (fixado nesta revisão):

| Estado | Significa |
|---|---|
| **aberta** | A afirmação continua sem verificação |
| **refinada** | A formulação ficou mais precisa, ou foi desmembrada. **Continua sem verificação** |
| **sustentada** | Alguém verificou e a afirmação se confirmou. Exige dizer **quem**, **como** e **com quantas pessoas** |
| **refutada** | Alguém verificou e a afirmação não se confirmou |
| **fora do recorte** | A equipe decidiu não tratar o tema. **Não diz nada sobre a verdade da afirmação** |

> **Erro corrigido nesta revisão:** várias linhas estavam marcadas como **refutada** quando o que ocorrera foi uma **decisão de recorte** (H06, H18) ou um **refinamento** (H16). Decidir não usar uma persona de gestor não torna falso que gestores consultem relatórios. Esses casos passaram a **fora do recorte** e a **refinada**, e estão registrados na seção 5.
>
> **Fotografia inicial preservada:** a coluna “Afirmação inicial” mantém o enunciado da Entrega 01 como ele foi escrito. O que evoluiu aparece nas colunas seguintes.

| ID | Afirmação / dúvida inicial | Tipo | Por que importa | Como/onde investigar | Evidência obtida | Estado atual | Impacto no projeto |
|---|---|---|---|---|---|---|---|
| H01 | Redução do tempo de resposta a incidentes (MTTR) via painel modular. | H | Valida se a interface realmente agiliza o diagnóstico do analista. | **Entregas 12–14** (avaliação) | **Nada.** A Entrega 02 examinou interfaces e a Entrega 05 modelará tarefas; nenhuma das duas mede tempo de trabalho humano. A referência anterior a “Entrega 2 / 5” foi corrigida | aberta | Justifica o layout focado em síntese visual |
| H02 | Viabilidade operacional em hardware limitado/embarcado. | H | Garante que a interface rode de forma leve na borda (edge). | Entrega 08 | Nada. O efeito que interessa à IHC é a **latência percebida na tela** (Entrega 01, 9.3) | aberta | Limita o peso das telas e define metas de tempo de resposta |
| H03 | Mapeamento de perfis diretos (SOC, SysAdmins, gestores). | H | Define os atores centrais da solução interativa. | Entrega 03 (construção) / Entrega 07 (verificação) | **Decisão de projeto:** foram construídas duas personas — P01 Thiago (analista) e P02 Vanessa (administradora), **ambas primárias**. Construir uma persona não verifica a existência do papel | refinada | Orienta a arquitetura em duas áreas: investigação e configuração |
| H04 | O analista monitora o tráfego e avalia ocorrências em tempo real. | H | Identifica o papel operacional de nível 1/2 no SOC. | Entrega 03 / 05, verificação na Entrega 07 | **Decisão de projeto:** persona P01 definida. **Nenhum analista foi observado ou entrevistado** | refinada | Define as funções da área de investigação |
| H05 | O administrador ajusta parâmetros de captura e escolhe algoritmos. | H | Identifica o papel administrativo e de infraestrutura. | Entrega 03 / 05, verificação na Entrega 07 | **Decisão de projeto:** persona **P02, primária** (justificativa na Entrega 03, 1.3). **Lacuna:** quando ela configura, com quem combina e de que informações depende está descrito como hipótese, não como dado | refinada | Justifica a área de configuração separada, com prevenção de erro |
| H06 | O gestor consulta relatórios e decide sobre investimentos. | H | Identifica a necessidade de visões consolidadas e executivas. | Entrega 07 | **Nada verificado.** A equipe decidiu não criar persona de gestor: ele permanece *stakeholder* no contexto social (Entrega 03, seção 3) | **fora do recorte** (antes: refutada) | **Correção:** a hipótese sobre a atividade do gestor continua plausível e não verificada. Consequência: **relatórios executivos saem do escopo** — o impacto registrado antes contradizia a própria decisão |
| H07 | Analistas precisam de dados pré-processados mesmo dominando termos técnicos. | H | Evita que a interface exponha dados brutos sem síntese. | Entrega 07 | **Nada verificado.** A Entrega 03 **supõe** essa necessidade ao descrever Thiago; a Entrega 02 mostra que concorrentes oferecem síntese — o que descreve os produtos, não a necessidade do nosso público | aberta | Prioriza indicadores sobre logs brutos |
| H08 | Em momentos de ataque, a interface deve evitar excesso visual e destacar severidade. | H | Evita sobrecarga cognitiva (*dashboard clutter*) em situações críticas. | Entregas 06 e 12–14 | **Nada verificado.** A redação anterior dizia que “as personas validaram” esta hipótese. **Uma persona é uma representação construída pela equipe; ela não é participante e não valida nada.** O que existe é uma **decisão de design** tomada a partir da hipótese | aberta | Guia a hierarquia visual — a ser testada com usuários |
| H09 | O usuário busca acesso seguro e resposta rápida para evitar vazamento. | H | Mapeia a motivação primária e de negócio do usuário. | Entrega 04 | PENDENTE | aberta | Direciona o foco em tempo de reação |
| H10 | O usuário precisa manter a rede operacional mitigando ameaças. | H | Mapeia o objetivo contínuo de proteção da infraestrutura. | Entrega 04 / 05 | PENDENTE. **“Mitigar” é objetivo do usuário no mundo, não função desta interface** (Entrega 01, quadro no fim da seção 2) | aberta | Define métricas de saúde da rede no topo do painel |
| H11 | Observar o estado da rede (A01) é a atividade mais frequente. | H | Estabelece qual tela deve ser a visualização padrão. | Entrega 07 | PENDENTE. **Estimativa da equipe**, repetida na Entrega 03 — repetição não é verificação | aberta | Torna a observação a tela de entrada |
| H12 | Investigar uma conexão sinalizada (A02) é a atividade mais crítica. | H | Define onde um erro do usuário traz maiores consequências. | Entrega 04 / 07 | PENDENTE. Estimativa da equipe a partir da consequência de erro | aberta | **F02 passou a prioridade Alta** na Entrega 01, 9.2 |
| H13 | Dificuldade de correlacionar métricas brutas sem ferramenta visual. | H | Mapeia o gargalo de usabilidade das ferramentas atuais. | Entrega 02 (interfaces) / Entrega 07 (pessoas) | **Obtido na Entrega 02:** os concorrentes tratam o problema com recortes prontos, filtros e contagem de resultados — o que indica que ele é **reconhecido no domínio**. **Não obtido:** se a dificuldade existe **para o nosso perfil** | refinada | É o problema de IHC do projeto. Justifica RC02 e RC04 |
| H14 | Cenário: o analista leva 40 minutos filtrando logs durante uma invasão. | H | Serve de cenário de referência para validar a solução proposta. | Entrega 04 | **Nada.** Cenário fictício. **A duração foi retirada:** não pode servir de linha de base. Personagem uniformizado como **Thiago** (antes: “Cleitin” na Entrega 01, 4.5 e “Lucas” na seção 10) | aberta | Serve para discutir o problema. **Não** para medir melhoria |
| H15 | A interação ocorre em salas de SOC ou estações sob pressão. | H | Mapeia o contexto físico e ambiental de uso. | Entrega 03 (descrição) / Entrega 07 (verificação) | **Decisão de projeto:** contexto descrito na Entrega 03, seção 3, incluindo o **plantão remoto**. Nenhuma observação de campo foi feita | refinada | Exige legibilidade em iluminação variável e painel que funcione em **um único monitor** |
| H16 | O sistema será usado em workstations e monitores conectados a embarcados. | H | Define o porte dos dispositivos de visualização. | Entrega 03 / 08 | **Refinamento, não refutação.** A hipótese misturava dois equipamentos. **O que mudou:** separou-se o equipamento de **processamento** (embarcado, que o usuário não opera) do equipamento de **interação** (notebook/desktop com navegador). **O que não mudou:** o processamento segue no embarcado | **refinada** (antes: refutada) | **Correção:** a justificativa anterior citava “notebooks, desktops e workstations” sem dizer qual parte da hipótese caiu. Direciona o design para tela de desktop |
| H17 | O ambiente exige uso contínuo, múltiplos monitores e modo escuro. | H | Mapeia requisitos de conforto visual prolongado. | Entregas 06 e 12–14 | **Nada verificado.** O registro anterior (“contexto mapeado na entrega 3”) convertia a hipótese em decisão visual | aberta | **Objetivo:** legibilidade e conforto prolongado. **Modo escuro é uma alternativa a testar**, não decisão decorrente. O painel também precisa funcionar em **um monitor só** |
| H18 | Existe hierarquia operacional: L1 tria, L2 investiga, gestor avalia. | H | Organiza os papéis de uso dentro da equipe. | Entrega 07 | **Nada verificado.** A equipe decidiu não criar persona de gestor — e **a própria Entrega 03, seção 3, continua afirmando a hierarquia**. As duas coisas são compatíveis: o gestor existe no contexto e não é alvo do design | **aberta** (antes: refutada) | **Correção:** retirar o gestor do elenco de personas não refuta a existência da hierarquia. L1, L2 e administrador deixaram de ser tratados como papéis equivalentes (Entrega 03, seção 3) |
| H19 | As alternativas exibem bem linhas do tempo e filtros. | H | Identifica convenções de mercado que devem ser mantidas. | Entrega 02 | **Obtido — a presença:** filtros, seletor de período e visualização temporal existem em `visualizacao_tempo.png`, `eventos.png` (C02) e nas capturas do FortiView (C01). **Não obtido — a qualidade:** “fazem bem” é julgamento e exigiria observar alguém usando | refinada | Preserva convenções verificadas como presentes |
| H20 | As alternativas pecam por complexidade e excesso de alertas irrelevantes. | H | Identifica os pontos fracos dos concorrentes a evitar. | Entrega 02 / Entrega 07 | **Obtido — percepção de complexidade:** relatos no G2, Reddit e PeerSpot (`image-8` a `image-12`), **ao lado de relatos opostos**. **Não obtido — excesso de alertas irrelevantes:** crítica de complexidade de navegação não comprova ruído de alerta. São problemas distintos | refinada | Foca na redução de ruído visual; a parte sobre alertas segue sem verificação |
| H21 | O usuário está habituado a gráficos de rosca, KPIs e tabelas coloridas. | H | Define o vocabulário visual e os componentes familiares. | Entrega 07 | **Obtido — os componentes existem** nas interfaces, com rótulo textual junto da cor em `nivel_severidade.png`. **Não obtido — familiaridade:** encontrar um componente numa interface diz respeito a quem a **projetou**, não a quem a **usa** | aberta | **Correção:** o registro anterior tratava presença como familiaridade. Adota componentes **plausíveis**, a confirmar |
| H22 | Configurações globais (limites de alerta) fazem sentido. | H | Avalia se a parametrização do sistema cabe no escopo. | Entrega 05 / 07 | PENDENTE | aberta | Define se haverá tela de limites globais |
| H23 | Gestão de usuários/permissões não é prioritária para o recorte. | — | Delimita o escopo pedagógico da disciplina. | **Decisão da equipe** | Não é hipótese a investigar: é escolha de escopo. **Correção:** o destino anterior dizia “Entrega 7 (Escopo de Interação)” — a **Entrega 07 é de coleta de dados** | **fora do recorte** | Remove telas de login e perfis do protótipo |
| H24 | CRUD tradicional não se aplica ao domínio de tráfego contínuo. | — | Evita aplicação de padrões de interface inadequados ao domínio. | **Decisão da equipe** | Escolha de padrão, fundamentada na natureza do domínio | **fora do recorte** | Descarta formulários CRUD |
| H25 | Tela de ajuda com guia de ataques ajudaria iniciantes. | H | Avalia necessidade de suporte instrucional na tela. | Entregas 05 / 06 / 12–14 | PENDENTE | aberta | Define modais ou *tooltips* explicativos |
| H26 | A interface reduzirá o tempo de identificação de ocorrências. | H | Define a proposta principal de valor da solução de IHC. | Entregas 12–14 | PENDENTE. **Encaminhamento de H01.** A linha de base será **medida no próprio teste**, nunca retirada do cenário fictício H14 | aberta | Meta de usabilidade |
| H27 | A interface trará clareza na alternância dos modelos de ML. | H | Mede a eficiência do controle modular do pipeline. | Entregas 07 e 12–14 | PENDENTE. **Refinada:** envolve também tornar visível **a P01** que o classificador mudou (Entrega 03, seção 3) | refinada | Meta de usabilidade da área de configuração |
| H28 | *Nova (revisão E01, 2.4):* analistas de SOC já estão familiarizados com ferramentas semelhantes. | H | Define o que a interface pode pressupor. | Entrega 07 | PENDENTE. Substitui um `[F]` indevido | aberta | Define o que a interface pode pressupor |
| H29 | *Nova (revisão E01, 2.4):* o analista decide sob pressão; a janela de decisão é curta. | H | Define as metas de usabilidade (Entrega 08). | Entrega 07 | PENDENTE. Substitui “decisões instantâneas” | aberta | Base das metas de usabilidade (Entrega 08) |
| H30 | *Nova (revisão E01, 4.1):* o processo atual segue indício → consulta → interpretação → encaminhamento. | H | É a hipótese de processo que estrutura as Entregas 04 e 05. | Entrega 07 | PENDENTE. Substitui a generalização sobre as alternativas | aberta | Estrutura as Entregas 04 e 05 e a etapa 1 da jornada |
| H31 | *Nova (revisão E01, 5.5):* há necessidade de retenção de histórico para auditoria. | H | Define se o histórico entra no recorte. | Entrega 07 | PENDENTE. Substitui um `[F]` indevido | aberta | Define se histórico e registro de decisão entram no recorte |

**Recomendações derivadas da Entrega 02**

| ID | Recomendação | Origem (achado → evidência) | Hipóteses relacionadas | Para onde vai |
|---|---|---|---|---|
| RC01 | Visão de entrada com poucos indicadores, detalhe em camadas | Separação panorama/detalhe em C01 e C02; carga informacional alta nos dois | H08, H13 | Entregas 05 e 06. “Poucos indicadores” é **escolha de simplificação**, não benefício comprovado |
| RC02 | Recortes prontos por origem, destino e fluxo | Observado em `Fortigate_sources/Destinations/sessions.png` | H13, H19 | Entregas 05 e 06. **Severidade ainda não tem critério definido** no projeto |
| RC03 | Distinguir categoria prevista, confiança, severidade e justificativa | Regra identificável em `eventos.png` (C02); assinatura nomeada em C01 (documentação) | H07, H08 | Entregas 05, 06 e 09–11. **Regra ≠ classificador:** a equivalência entre explicação por regra e por atributos é hipótese |
| RC04 | Panorama → filtro → detalhe, com contagem de resultados visível | Contagem observada em `eventos.png`; estado da consulta visível em C01 | H13, H20 | Entregas 05 e 06. Filtro por clique em gráfico é **proposta**, sem evidência observada |


## 3. Rastreabilidade entre contribuição técnica, necessidades e artefatos

| ID  | Capacidade do TCC utilizada                                     | Necessidade/problema                                                      | Persona       | Cenário problema                                 | Objetivo/tarefa                          | HTA/GOMS/CTT | Cenário de interação / signos                          | MoLIC    | Tela(s) Figma | Heurística / problema | Tarefa no teste | Decisão/melhoria                         |
| --- | --------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------- | ------------------------------------------------ | ---------------------------------------- | ------------ | ------------------------------------------------------ | -------- | ------------- | --------------------- | --------------- | ---------------------------------------- |
| R01 | Classificação do tráfego em tempo real, com categoria prevista e confiança | [H13] O analista precisa reunir o contexto de uma conexão para julgar se a classificação corresponde a um incidente | P01 — Thiago (primária, investigação) | C01 — conexão sinalizada durante o turno | Observar o estado da rede (A01) e investigar uma conexão sinalizada (A02); **registrar a decisão** | PENDENTE | Painel com ocorrências, contexto do fluxo, filtros e contagem de resultados | PENDENTE | PENDENTE | PENDENTE | PENDENTE | Define a área de investigação. **Contenção fica fora** — Entrega 01, quadro no fim da seção 2 |
| R02 | Pipeline modular: alternância do classificador ativo | [H05/H27] A administradora precisa saber o efeito de uma mudança antes de aplicá-la | P02 — Vanessa (primária, configuração) | C02 — troca do classificador em janela planejada | Ajustar o classificador ativo (A03) sabendo a consequência | PENDENTE | Comparação entre modelo atual e candidato, confirmação explícita, caminho de volta | PENDENTE | PENDENTE | PENDENTE | PENDENTE | Define a área de configuração, separada da investigação |
| R03 | Identificação do classificador que produziu cada resultado | [H27] Quando Vanessa troca o modelo, muda o que Thiago vê — e ele precisa poder atribuir a mudança a uma causa | **P01 e P02** | Coordenação entre os dois fluxos | Saber qual classificador está ativo e desde quando | PENDENTE | Indicação persistente do modelo ativo na área de investigação | PENDENTE | PENDENTE | PENDENTE | PENDENTE | **Linha nova nesta revisão:** é o ponto onde os dois perfis se cruzam (Entrega 03, seção 3) |


## 4. Rastreabilidade de padrões de interface

Use esta tabela quando o projeto incorporar padrões como dashboard, relatório, histórico, filtros ou administração. O objetivo é **justificar o padrão**, não apenas listar telas.

| ID da tela/fluxo | Padrão de interface | Objetivo/tarefa que justifica | Informação/ação principal | Evidência de necessidade | Artefatos relacionados |
|---|---|---|---|---|---|
| F01 | dashboard | Observar o estado da rede e decidir se há algo a investigar (A01) | “Há algo fora do padrão agora?” — poucos indicadores, sem detalhe | [H11] frequência estimada; [H08] carga sob pressão; **RC01** | C01, C02 (Entrega 02); jornada etapa 2 |
| F02 | histórico com filtros | Restringir o conjunto de conexões e, depois, recuperar o que foi decidido (A02 e passagem de plantão) | Filtros prontos, **contagem de resultados após cada filtro**, registro da decisão legível por outra pessoa | [H13]; [H31] retenção para auditoria; **RC04** | Jornada etapas 3, 6 e 7 |
| F03 | administração/CRUD | Ajustar o classificador ativo sabendo a consequência (A03) | Estado atual, comparação, **efeito previsto antes de confirmar**, caminho de volta | [H05]; [H27]; Entrega 03, quadro “Por que as duas personas são primárias” | Decorre de P02 ser primária |
| F04 | detalhamento/explicabilidade | Investigar uma conexão sinalizada e julgar se corresponde a um incidente (A02) | Contexto do fluxo + **categoria prevista, confiança, severidade e critério, distintos entre si** | [H12] criticidade estimada; [H13] dificuldade de correlacionar; **RC02, RC03** | Jornada etapas 3 e 4. Atende a ação F02 da Entrega 01 (9.2), cuja prioridade foi revisada para Alta |
| — | relatório executivo | — | — | [H06] **fora do recorte**: o gestor não é persona deste projeto | Registrado para preservar o histórico da decisão |
| — | usuários/perfis/permissões | — | — | [H23] **fora do recorte** (decisão de escopo da disciplina) | Idem |
| — | personalização de painéis | — | — | [H] **Hipótese, não necessidade.** Observada no Wazuh (Entrega 02); retirada das necessidades de P01 na revisão da Entrega 03 | Entrega 07 |


## 5. Registro de mudanças de escopo

> Registra **mudanças efetivas**: decisões de recorte, reclassificações de estado e correções de registro. A fotografia inicial da Entrega 01 é preservada na seção 2.
| Data | O que mudou | Evidência/feedback que motivou | Artefatos afetados | Responsável |
|---|---|---|---|---|
| 03/10/2026 | **P02 (Vanessa) consolidada como persona primária** | Feedback E03, item 1: a Entrega 03 declarava P02 como secundária em uma seção e primária na ficha e na matriz | Entrega 03 (seções de entrada, 1.3, síntese), esta matriz (seções 1, 3 e 4) | Marcela |
| 03/10/2026 | **Contenção retirada do recorte declarado.** A interface apoia perceber, interpretar, decidir e encaminhar; bloquear/isolar ocorre fora dela | Feedback E01, item 2 e E03, item 5: o texto prometia “conter ameaças” e “mitigar invasões”, mas F01–F03 descreviam visualizar, inspecionar e alternar | Entrega 01 (quadro no fim da seção 2, além de 2.2, 4.4, 7.3, 7.4, 9.2, 13), Entrega 03 (quadro “Onde termina a análise e onde começa a contenção” e objetivo da jornada), esta matriz | Equipe |
| 03/10/2026 | **H06 e H18 deixaram de constar como refutadas** | Feedback E01, item 6: retirar o gestor do elenco de personas é decisão de recorte e não refuta hipótese sobre o domínio | Seção 2 desta matriz; Entrega 03, seção 3 | Equipe |
| 03/10/2026 | **H16 reclassificada de refutada para refinada** | Feedback E01, item 6: a justificativa não dizia qual parte da hipótese caiu. Separou-se equipamento de processamento (embarcado) de equipamento de interação (desktop) | Seção 2; Entrega 01, 9.3; Entrega 03, seção 3 | Equipe |
| 03/10/2026 | **H08 deixou de constar como “validada pelas personas”** | Feedback E01, item 6 e E03, item 3: persona é representação construída pela equipe, não participante | Seção 2; Entrega 03, seção 2 | Equipe |
| 03/10/2026 | **Modo escuro deixou de ser decisão; voltou a ser alternativa em investigação** | Feedback E03, item 7: fadiga visual não leva automaticamente a tema escuro, e H17 segue pendente | Entrega 03, 1.4; seção 2 desta matriz | Lucas |
| 03/10/2026 | **Personalização de painéis retirada das necessidades de P01** | Feedback E03, item 7: na Entrega 02 era possibilidade condicionada; virou necessidade sem justificativa | Entrega 03, 1.4; seção 4 desta matriz | Lucas |
| 03/10/2026 | **F02 passou de prioridade Média para Alta** | Feedback E01, item 5: a prioridade contradizia A02/H12, a atividade identificada como mais crítica | Entrega 01, 9.2; seção 4 desta matriz | Equipe |
| 03/10/2026 | **Linha R03 criada:** identificação do classificador ativo para quem investiga | Feedback E03, item 6: faltava explicitar como um perfil acompanha o efeito da ação do outro | Seção 3 desta matriz; Entrega 03, seção 3 | Equipe |
| 03/10/2026 | **Produtos deixaram de ser descartados por “não ter interface”** | Feedback E02, item 4: cinco deles têm console próprio, e log/CLI também são interfaces | Entrega 02 (mapa de alternativas e 3.1) | Equipe |
| 03/10/2026 | **Hipóteses H28–H31 criadas** | Feedback E01, item 3: afirmações sobre práticas profissionais, pressão de tempo, processo atual e auditoria estavam marcadas como `[F]` sem sustentação | Entrega 01 (2.4, 4.1, 5.5); seção 2 desta matriz | Equipe |


## Como usar

- Use identificadores estáveis (`H01`, `P01`, `C01`, `T01`, `M01`, `F01`, `UT01`).
- Quando uma necessidade/problema tiver origem em hipótese da Entrega 1, cite o ID correspondente.
- Em TCC sem interface original, pelo menos uma linha deve mostrar claramente **como uma capacidade técnica chega até uma tarefa de usuário e uma tela/fluxo**.
- Uma linha pode se desdobrar quando um objetivo possui múltiplos caminhos.
- Não force relação inexistente: se algo ainda não foi modelado, marque `PENDENTE`.
- Ao remover uma funcionalidade, registre a decisão em vez de apagar silenciosamente o histórico.
- Dashboard, CRUD, filtros e relatórios só devem aparecer quando houver objetivo/tarefa que os justifique.
