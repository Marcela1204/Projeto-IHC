# Entrega 7 — Coleta de dados, necessidades e aspectos éticos

**Data:** 22/10/2026 · **Revisada em:** 16/11/2026  
**Status:** `🟩 Concluído`  
**Instrumento I01 on-line:** {{URL do formulário publicado}} · versão **I01-v2**, de {{16/11/2026}}


## Objetivo da atividade

Planejar dados necessários para compreender usuários e requisitos de IHC, escolher técnicas adequadas e documentar instrumentos de modo que a aplicação possa ser reproduzida por pessoas diferentes.

## Para escopos de IHC derivados de TCC técnico

Quando o usuário e a interface foram propostos pela disciplina, uma prioridade da coleta é investigar se esse **cenário de uso realmente faz sentido**. Não trate o exercício de comercialização da Entrega 1 como validação de mercado.

Perguntas úteis incluem:

- esse perfil realmente realiza a atividade imaginada?
- quais ferramentas usa hoje?
- quais informações consulta?
- quais decisões toma?
- que vocabulário utiliza?
- quais parâmetros compreende e quais deveriam ser abstraídos?
- precisa de dashboard, histórico, filtros, relatórios ou comparação? Por quê?
- quais erros são frequentes e quais são críticos?
- existem papéis/permissões diferentes?
- que resultados do algoritmo/modelo seriam úteis ou difíceis de interpretar?

Quando o acesso ao perfil profissional for difícil, discuta com o docente alternativas metodológicas (especialistas próximos, dados secundários, literatura, participantes proxy) e registre as limitações. **Não esconda a limitação da amostra.**

## Hipóteses e lacunas prioritárias herdadas da Entrega 1

Antes de decidir “que dados coletar”, retome os itens `[H]` e `[?]` da Entrega 1 e o registro de hipóteses em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md). A coleta deve responder perguntas reais do projeto, e não apenas produzir um formulário porque a técnica foi solicitada.

| ID | Hipótese/lacuna | Evidência atual | Decisão que depende da resposta | Prioridade |
|---|---|---|---|---|
| H04 | O analista monitora o tráfego e avalia ocorrências em tempo real. | Persona P01 foi construída pela equipe, mas ainda não foi validada com analistas reais. | Confirmar se a atividade de investigação realmente acontece em plantão, com ritmo acelerado e critério de priorização. | alta |
| H05 | O administrador ajusta parâmetros de captura e escolhe algoritmos. | A persona P02 foi definida como primária, mas a rotina exata de configuração, reversão e validação ainda não foi observada. | Verificar se a troca de modelo e a avaliação de impacto são tarefas reais e frequentes, e em que etapa a decisão ocorre. | alta |
| H07 | Analistas precisam de dados pré-processados mesmo dominando termos técnicos. | A equipe supõe que os usuários precisam de resumo, contexto e severidade, mas isso ainda não foi verificado. | Definir se a tela deve priorizar síntese visual, filtros e explicação, ou se os usuários preferem maior detalhe técnico. | alta |
| H11 | Observar o estado da rede (A01) é a atividade mais frequente. | Baseado em estimativa da equipe e no fluxo de investigação proposto. | Confirmar a frequência e a relevância da atividade para a área de monitoramento, antes de priorizar o dashboard de entrada. | média |
| H12 | Investigar uma conexão sinalizada (A02) é a atividade mais crítica. | A hipótese é motivada pela consequência de erro, mas ainda não investigada com profissionais. | Definir se a interface deve priorizar decisões, justificativas, histórico e rastreabilidade durante a análise de uma ocorrência. | alta |
| H28 | Profissionais de SOC já conhecem ferramentas semelhantes. | A equipe assume familiaridade com convenções de SIEM, alertas e filtros. | Saber até que ponto o público conhece padrões de monitoramento e qual vocabulário ele usa. | média |
| H29 | O analista decide sob pressão e com janela de decisão curta. | Contexto de uso foi proposto com base no domínio e no cenário de operação. | Validar a urgência da tarefa e a importância de legibilidade instantânea, priorização visual e redução de ruído. | alta |
| H30 | O processo atual segue indício → consulta → interpretação → encaminhamento. | Ainda não foi confirmado em campo. | Validar a sequência real do trabalho para construir um fluxo de interface compatível com a prática profissional. | alta |
| H31 | Há necessidade de retenção de histórico para auditoria. | Hipótese importante, especialmente para plantão e passagem de turno. | Definir se o sistema precisa registrar decisões, justificar ações e permitir revisão posterior. | alta |

## Parte A — necessidades e requisitos de IHC

> **Responsabilidade:** solução individual por integrante.

### A01 — Lucas Kerr do Amaral

*Autor(a):* Lucas Kerr do Amaral — 22.123.032-9

#### Que dados coletar?

| Dado/informação | Hipótese/lacuna relacionada | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| Fluxo diário do analista de SOC ao identificar uma ocorrência suspeita | H04, H30 | Entender a sequência real de trabalho: como ele percebe o alerta, o que consulta e como decide | Estrutura do dashboard de entrada, ordem de leitura e agrupamento de informações |
| Quais sinais ele considera decisivos para classificar um alerta | H07, H12, H28 | A informação relevante pode ser diferente de “dados técnicos crus”; a interface precisa refletir o critério humano | Níveis de resumo, prioridades de visualização, painel de contexto e explicação |
| Tempo médio de resposta e pressão de operação | H29 | A decisão ocorre sob limitação temporal; a interface deve reduzir carga cognitiva | Hierarquia visual, destaque de severidade e simplificação do processo |
| Como ele usa histórico, filtros e comparação de dados | H11, H31 | A auditoria e o retorno do plantão dependem de recuperar o que já foi avaliado | Histórico de ocorrências, filtros por origem/destino/severidade e registro de decisão |
| O que distingue falso positivo, verdadeiro positivo e caso ambíguo | H07, H12 | A decisão humana depende da forma como a situação é interpretada | Linguagem de classificação, critérios visuais e explicações do sistema |

#### De quem coletar?

| Perfil/stakeholder | Critério de inclusão | Relação com persona/público |
|---|---|---|
| Analista de SOC (nível 1 ou 2) | Atuar em monitoramento de rede/segurança e lidar com alertas em plantão ou rotina | P01 — Thiago Albuquerque, fluxo de investigação |
| Especialista em operação de segurança | Experiência em triagem de alertas, incidentes ou redes | Papel próximo ao analista, útil para validar linguagem e critério |
| Operador de infraestrutura / plantão de TI | Trabalha com resposta a incidentes e continuidade da operação | Stakeholder secundário, mas útil para entender urgência operacional |

#### Aspectos éticos

A coleta com analistas envolve informações sobre rotina, tempo de resposta, priorização de incidentes e percepções sobre falhas operacionais. O risco principal não é a presença de dados pessoais sensíveis em si, mas a possibilidade de expor padrões de desempenho, falhas de processo ou indicadores de pressão de trabalho em contextos organizacionais. Por isso, a coleta deve ser voluntária e explicitar que a participação pode ser interrompida a qualquer momento.

O consentimento informado explica (roteiro na Parte C): objetivo da pesquisa, duração estimada, itens que serão perguntados, uso do material para fins acadêmicos e que a identidade do participante será protegida. Gravação de áudio só ocorre com autorização explícita, dada antes de qualquer registro; não há gravação de tela nem de vídeo. Dados de rede, endereços IP, nomes de ambientes e detalhes que permitam identificar a organização devem ser minimizados ou omitidos.

A anonimização remove nomes, identificadores, nomes de clientes, topologias e estruturas internas. As regras concretas de gravação, armazenamento, acesso e descarte estão no protocolo de I02 e na Parte C. As respostas são vinculadas a códigos (E01, E02…) e a origem nunca é revelada em apresentações. O risco maior é a exposição de conhecimento operacional crítico sobre a infraestrutura de uma empresa; por isso, a coleta deve priorizar perguntas sobre o trabalho de investigação e não sobre detalhes técnicos sensíveis da rede.

---

### A02 — Marcela Nalesso

**Autor(a):** Marcela Nalesso — 22.222.011-3   

#### Que dados coletar?

| Dado/informação | Hipótese/lacuna relacionada | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| Como a troca de modelo ou o ajuste de configuração é feito na prática | H05, H22, H27 | A rotina real pode não corresponder ao que a equipe imagina; a interface precisa respeitar o processo | Área de configuração, sinal de mudança de modelo, confirmação antes de aplicar |
| Quais métricas o administrador observa antes de decidir | H05, H27 | A decisão de manter, ajustar ou reverter configurações depende de indicadores mais do que de uma única métrica | Comparação entre modelo atual e candidato, painel de validação e revisão de impacto |
| Como ele interpreta “impacto”, “desempenho” e “segurança” no contexto operacional | H05, H27, H28 | O vocabulário do domínio pode exigir abstrações e tradução visual para reduzir erro | Termos e legendas do painel, etiquetas de ação e explicações sobre risco |
| Frequência e criticidade de alterações na configuração do IDS | H22, H29 | Isso define se a ação deve ser tratada como tarefa rotineira ou de alerta prioritário | Prioridade visual, fluxo de confirmação e possibilidade de reversão |
| Necessidade de histórico e rastreio de mudanças | H31, H27 | É preciso saber se e como o administrador consulta alterações passadas, antes de supor que ele precisa de quem, quando e por quê | Indicador de modelo ativo, histórico de trocas e trilha de decisão |

#### De quem coletar?

| Perfil/stakeholder | Critério de inclusão | Relação com persona/público |
|---|---|---|
| Administrador de infraestrutura / segurança operacional | Atua na manutenção de IDS, regras, políticas e parametrização | P02 — Vanessa Toledo, fluxo de configuração e validação |
| Analista de rede / SOC com rotina de parametrização | Já teve contato com ajustes de sensibilidade, tráfego e alertas | Papel complementar, importante para entender o ponto de contato entre configuração e investigação |
| Gestor de TI ou responsável por estabilidade da rede | Acompanha impacto operacional e decisão de mudança | Stakeholder de contexto, principalmente para avaliar risco, mudança e continuidade |

#### Aspectos éticos

A pesquisa com administradores envolve dados sobre configuração de rede, regras, taxa de alertas e impacto em infraestrutura crítica. Embora não sejam necessariamente dados pessoais, esses elementos podem revelar arquitetura de rede, design de firewall, políticas internas e vulnerabilidades operacionais, sendo sensíveis para a organização. Portanto, a coleta deve enfatizar o processo de decisão e não detalhes de infraestrutura que permitam mapear uma rede em produção.

A introdução do formulário informa que a pesquisa não exige exposição de dados confidenciais e que o participante pode pular qualquer item não essencial. O questionário não coleta capturas de tela, e-mail nem nome. Nomes de hosts, sub-redes, senhas, endpoints internos ou dados de clientes não são solicitados nem aceitos (Parte C).

Para garantir minimização, os dados devem ser anonimizados por meio de códigos e substituição de nomes, endereços e identificadores. A análise deve considerar apenas os padrões de decisão, critérios de avaliação e linguagem necessária para o design, e não a arquitetura completa do ambiente. Armazenamento, acesso e descarte seguem o protocolo de I01 (local, pessoas com acesso e data de descarte definidos).


### Terminologia usada nos instrumentos

Os instrumentos usam os termos com o significado fixado nas Entregas 09–11, adaptados ao vocabulário do participante:

| Termo do projeto | Significado | Como aparece para o participante |
|---|---|---|
| modelo | O componente que classifica o tráfego (no projeto, o SVM do estágio 2) | “modelo, regra ou configuração da ferramenta de detecção” |
| classificação | O que o modelo atribui a um alerta (ataque, benigno, pendente) | “a classificação ou severidade que a ferramenta atribui” |
| veredito do analista | A decisão humana registrada sobre o alerta (ataque, benigno, indefinido) | “a decisão que você toma sobre o alerta” |
| incerteza da classificação | O quanto o próprio modelo está perto de classificar de outro jeito | não é perguntada diretamente; investigamos **que tipo de evidência** torna a classificação interpretável |
| troca de modelo | Promover um candidato ou reverter ao anterior | “alteração de regra, limiar ou modelo” |

## Parte B — ferramentas de coleta

> Cada integrante prepara uma técnica completa. As técnicas são diferentes entre si e o questionário está entre elas, conforme o enunciado da disciplina.

### Instrumento I01 — Questionário estruturado (on-line, com ramificação por perfil)

**Autor(a) e responsável pela aplicação:** Marcela Nalesso — 22.222.011-3  
**Técnica:** questionário autoaplicável on-line  
**Link para resposta:** {{URL do formulário publicado}}  
**Plataforma:** Google Forms, com a opção “Coletar endereços de e-mail” **desativada**, sem login obrigatório e sem upload de arquivos  
**Versão:** I01-v2 (este documento), publicada em {{dd/mm/2026}}. Qualquer alteração após o teste interno gera I01-v3, com data e descrição registradas na tabela de versões abaixo  
**Objetivo:** mapear, por perfil, a rotina de investigação e de configuração, as informações consultadas antes de decidir, o que acontece depois da decisão, a pressão de tempo e o vocabulário usado.  
**Público:** analistas de SOC/monitoramento, administradores de rede/segurança que configuram ferramentas de detecção e gestores de TI/segurança.

| Versão | Data | O que mudou |
|---|---|---|
| I01-v1 | 22/10/2026 | Versão só textual, 19 questões, sem ramificação (não publicada) |
| I01-v2 | 16/11/2026 | Introdução ética, ramificação por perfil, perguntas reformuladas, tipo e obrigatoriedade por item |
| I01-v2 publicada | {{dd/mm/2026}} | {{“sem mudanças” ou o que mudou após o teste interno}} |

#### Protocolo de recrutamento e aplicação

| Item | Definição |
|---|---|
| Amostra mínima pretendida | **5** respostas do bloco Investigação (analistas/operadores), **3** do bloco Configuração (administradores) e até **3** do bloco Gestão. Justificativa de viabilidade: perfis especializados e de acesso difícil para uma equipe de duas pessoas em duas semanas; o objetivo é identificar padrões e contradições, não estimar proporções da população |
| Critérios de inclusão | 18 anos ou mais; atuar ou ter atuado nos últimos 2 anos em monitoramento de rede/segurança, configuração de ferramentas de detecção (IDS/IPS, SIEM, *firewall*) ou gestão dessas equipes |
| Critérios de exclusão | Integrantes da Equipe 21 e pessoas que participaram da elaboração das personas, protótipos ou instrumentos; quem não atende à inclusão. Colegas de curso sem experiência profissional na área podem responder, mas são marcados como ***proxy*** (pergunta 1.3) e analisados **à parte** |
| Canal de recrutamento | (1) contatos profissionais diretos dos dois integrantes, por mensagem individual; (2) grupos de ex-alunos e de estágio da instituição em segurança/redes; (3) indicação dos próprios participantes (bola de neve), sem pedir dados de quem foi indicado |
| Convite (texto) | “Olá, somos estudantes de IHC e estamos pesquisando como profissionais de monitoramento e segurança de redes investigam alertas e alteram configurações de ferramentas de detecção. O questionário é anônimo, leva de 8 a 12 minutos e não pede nenhum dado da sua empresa ou da sua rede. Link: {{URL}}. Obrigado!” |
| Responsável | Marcela Nalesso (publicação, convites, acompanhamento); Lucas Kerr do Amaral (teste interno e revisão) |
| Modalidade e período | Remota e autoaplicável; coleta de {{dd/mm}} a {{dd/mm/2026}} (2 semanas), com um lembrete único após 7 dias |
| Duração confirmada | {{min}} minutos, cronometrada no teste interno com 2 respondentes que não entram na amostra (meta: 8–12 min) |
| Sequência de consentimento | Seção 0 (introdução) → pergunta 0.1 de aceite, **obrigatória**; quem escolhe “Não aceito” é enviado direto ao encerramento, sem ver nenhuma pergunta |
| Registro das respostas | Planilha de respostas vinculada ao formulário; cada linha recebe um código **Q01, Q02…** na ordem de chegada; a data/hora automática é mantida só para a ordem e descartada na exportação |
| Armazenamento e acesso | Formulário e planilha numa pasta do Google Drive da conta institucional de Marcela, compartilhada **somente** com Lucas. Nenhum dado bruto vai para o GitHub: no repositório entram apenas tabelas agregadas por perfil e trechos de respostas abertas sob o código Q, revisados conforme a Parte C |
| Retenção e descarte | Dados brutos mantidos até **{{31/12/2026}}**, depois do encerramento da disciplina; nessa data o formulário, a planilha e as exportações locais são excluídos (inclusive da lixeira) por Marcela, e Lucas confirma por escrito no registro de decisões do repositório |
| Pedido de exclusão | Atendido enquanto a resposta puder ser localizada pelo **código de resposta** que o participante cria (pergunta 5.1) e até a data de descarte. Sem o código, a resposta não pode ser localizada, porque não coletamos identificação |

#### Instrumento (conteúdo do formulário publicado)

**Seção 0 — Introdução (texto visível antes da primeira pergunta)**

> **Pesquisa acadêmica — investigação de alertas e alterações em ferramentas de detecção de rede**
>
> Este questionário faz parte de um trabalho da disciplina de Interação Humano-Computador. Queremos entender como profissionais de monitoramento e de segurança de redes **investigam alertas** e **alteram configurações** de ferramentas de detecção, para projetar uma interface que apoie esse trabalho.
>
> **Para quem:** pessoas que atuam (ou atuaram nos últimos 2 anos) com monitoramento de rede, configuração de ferramentas de detecção ou gestão dessas equipes.  
> **Duração:** cerca de 8 a 12 minutos.  
> **Participação voluntária:** você pode parar a qualquer momento, sem justificativa, e pode pular qualquer pergunta que não esteja marcada como obrigatória. Não há respostas certas ou erradas e **não avaliamos o seu desempenho** nem o da sua equipe.  
> **O que coletamos:** só as suas respostas. **Não coletamos e-mail, nome nem qualquer identificação.**  
> **Não informe:** nomes de pessoas, clientes ou organizações; endereços IP, nomes de hosts, sub-redes, topologia; senhas; nomes internos de sistemas; capturas de tela. Se precisar dar um exemplo, descreva-o de forma genérica (ex.: “um servidor web interno”).  
> **Uso dos dados:** apenas acadêmico. Os resultados aparecem de forma agregada ou em trechos curtos sob um código (Q01, Q02…). Os dados brutos ficam acessíveis só aos dois integrantes da equipe e serão excluídos em {{31/12/2026}}.  
> **Exclusão da sua resposta:** ao final, você pode criar um código de resposta. Com ele, podemos localizar e apagar a sua resposta até {{31/12/2026}}.  
> **Contato:** Lucas Kerr do Amaral e Marcela Nalesso — {{e-mail institucional da equipe}}.

| # | Pergunta | Tipo de resposta | Regra |
|---|---|---|---|
| 0.1 | Li as informações acima e aceito participar. | Única escolha: Aceito / Não aceito | **Obrigatória.** “Não aceito” → encerramento |

**Seção 1 — Perfil (todos)**

| # | Pergunta | Tipo de resposta | Regra |
|---|---|---|---|
| 1.1 | Qual destas descrições mais se aproxima do seu trabalho **principal** hoje? | Única escolha: (a) Investigo alertas e eventos de segurança ou de rede (ex.: analista de SOC, NOC, plantão) · (b) Configuro e mantenho ferramentas de detecção, regras ou limiares (ex.: administrador de rede/segurança) · (c) Coordeno ou gerencio equipes de TI/segurança · (d) Nenhuma destas | **Obrigatória.** Encaminha: (a) → Seção 2; (b) → Seção 3; (c) → Seção 3G; (d) → encerramento com agradecimento (fora do público) |
| 1.2 | Há quanto tempo você atua nessa função? | Única escolha: menos de 1 ano · 1 a 3 anos · mais de 3 a 5 anos · mais de 5 anos | Obrigatória |
| 1.3 | Você atua nessa função profissionalmente (emprego ou estágio)? | Única escolha: Sim · Não, conheço a área por estudo ou projeto | Obrigatória. “Não” marca a resposta como *proxy* |
| 1.4 | Que tipos de ferramenta você usa nesse trabalho? Marque todos que se aplicam. | Caixas de seleção: SIEM · IDS/IPS · *firewall* com console de monitoramento · plataforma de observabilidade/logs · *scripts* e linha de comando · planilhas · nenhuma · outro (texto) | Opcional. Pedimos o **tipo**, não o produto da empresa |

**Seção 2 — Investigação de alertas** (só para 1.1 = a)

| # | Pergunta | Tipo de resposta | Regra |
|---|---|---|---|
| 2.1 | Com que frequência você analisa alertas ou registros de rede/segurança? | Única escolha: várias vezes ao dia · cerca de uma vez por dia · algumas vezes por semana · algumas vezes por mês ou menos · não realizo esta atividade | Obrigatória |
| 2.2 | Em que situações essa análise acontece? Marque todas que se aplicam. | Caixas: turno regular · plantão ou sobreaviso · só durante incidentes/crises · outra (texto) | Opcional. (Frequência e contexto separados: antiga pergunta 3) |
| 2.3 | Pense no último alerta que você investigou. Sem citar nomes, endereços ou sistemas, conte o que você olhou primeiro e o que olhou depois. | Parágrafo | Opcional |
| 2.4 | O que você costuma consultar antes de decidir sobre um alerta? **Marque todas que se aplicam.** | Caixas: origem e destino da conexão · protocolo/serviço · volume comparado ao habitual · histórico do equipamento ou usuário · severidade atribuída pela ferramenta · classificação ou pontuação da ferramenta · fontes externas de ameaças · colegas · outro (texto) | Opcional. (Antiga 5, agora com múltipla seleção declarada) |
| 2.5 | Das opções que você marcou acima, qual você consulta **primeiro**? | Lista suspensa com as mesmas opções | Opcional |
| 2.6 | Como você costuma perceber que algo está fora do padrão? | Parágrafo | Opcional. (Substitui a antiga 11, que já propunha a solução) |
| 2.7 | Com que frequência você precisa decidir sobre um alerta antes de reunir todas as informações que gostaria? | Escala: nunca · raramente · às vezes · frequentemente · sempre | Obrigatória |
| 2.8 | Quando a ferramenta atribui uma classificação ou severidade a um alerta, o que você costuma fazer com ela? | Única escolha: na maioria das vezes aceito · uso como ponto de partida e confirmo com outras informações · costumo desconsiderar · depende do caso · a ferramenta que uso não atribui | Obrigatória |
| 2.9 | Em que situações você desconfia da classificação da ferramenta? | Parágrafo | Opcional |
| 2.10 | O que acontece **depois** que você decide sobre um alerta? Marque todas que se aplicam. | Caixas: registro em ferramenta de chamados · registro na própria ferramenta de monitoramento · aviso informal (chat, telefone) · encaminho a outra equipe · não costuma haver registro · outro (texto) | Opcional. (Substitui as antigas 15 e 16, que pressupunham a utilidade do registro) |
| 2.11 | Quando você retoma um caso iniciado por outra pessoa (ex.: troca de turno), como sabe o que já foi feito? | Parágrafo, com a opção de escrever “não retomo casos de outras pessoas” | Opcional |
| 2.12 | Você costuma ficar sabendo quando uma regra, limiar ou modelo da ferramenta de detecção é alterado? | Única escolha: sempre · às vezes · raramente · nunca · não sei | Obrigatória |
| 2.13 | Se fica sabendo, como? | Parágrafo | Opcional; mostrado a todos do bloco. (Substitui a antiga 13, que sugeria a importância de “quem mudou” e “há quanto tempo”) |

**Seção 3 — Configuração da ferramenta de detecção** (só para 1.1 = b)

| # | Pergunta | Tipo de resposta | Regra |
|---|---|---|---|
| 3.1 | Com que frequência você altera regras, limiares ou modelos de detecção em produção? | Única escolha: toda semana ou mais · algumas vezes por mês · algumas vezes por ano · nunca alterei · não realizo esta atividade | Obrigatória. “Nunca alterei” ou “não realizo” → pula para 3.6 |
| 3.2 | Qual foi o motivo da **última** alteração que você fez? | Única escolha: muitos alertas falsos · ataque que não foi detectado · mudança na rede ou nos serviços · atualização do fornecedor · manutenção planejada · outro (texto) | Opcional |
| 3.3 | Antes de aplicar uma alteração, o que você verifica? Marque todas que se aplicam. | Caixas: resultados em dados de teste · comparação com a configuração atual · efeito previsto no volume de alertas · carga do equipamento · aprovação de outra pessoa · nada formal · outro (texto) | Opcional |
| 3.4 | Em geral, quão **arriscada** você considera uma alteração de regra ou modelo em produção? | Escala 1–5 (1 = nada arriscada, 5 = muito arriscada) | Obrigatória. (A antiga 12 misturava risco e frequência; frequência está em 3.1) |
| 3.5 | Nos últimos 6 meses, quantas vezes foi preciso desfazer uma alteração? | Única escolha: nenhuma · 1–2 · 3–5 · mais de 5 · não sei | Opcional |
| 3.6 | Como os analistas que investigam alertas ficam sabendo de uma alteração? | Caixas: aviso formal · registro de mudanças consultável · informalmente · não ficam sabendo · não sei · outro (texto) | Opcional |
| 3.7 | Depois de uma alteração, como você verifica se ela teve o efeito esperado? | Parágrafo | Opcional |

**Seção 3G — Gestão** (só para 1.1 = c)

| # | Pergunta | Tipo de resposta | Regra |
|---|---|---|---|
| 3G.1 | Qual é a sua participação em alterações na ferramenta de detecção? | Única escolha: aprovo · sou consultado(a) · sou informado(a) depois · não participo | Obrigatória |
| 3G.2 | Que informações sobre alertas e incidentes chegam até você? Marque todas que se aplicam. | Caixas: relatórios periódicos · painel que consulto · comunicação da equipe · não recebo · outro (texto) | Opcional |
| 3G.3 | O que você precisa saber para aprovar ou questionar uma alteração? | Parágrafo | Opcional |

**Seção 4 — Ferramentas de monitoramento (todos os perfis)**

| # | Pergunta | Tipo de resposta | Regra |
|---|---|---|---|
| 4.1 | Para cada item, indique como ele aparece no seu trabalho hoje. Itens: indicadores resumidos · filtros (por origem, destino, protocolo…) · comparação com período anterior · detalhamento de uma ocorrência · histórico de decisões anteriores · explicação de por que algo foi sinalizado | Grade de múltipla escolha, uma resposta por linha: uso e me ajuda · uso, mas ajuda pouco · não uso · não conheço | Opcional por linha. (Substitui as antigas 10 e 17: em vez de uma preferência única por componentes complementares, pergunta o uso de cada um) |
| 4.2 | Que informação, se aparecesse junto de um alerta, **ajudaria** você a decidir? E qual **atrapalharia** (por excesso, ruído ou risco de interpretação errada)? | Parágrafo | Opcional. (Substitui a antiga 14) |
| 4.3 | O que mais dificulta o seu trabalho de monitoramento hoje? Marque **até 3**. | Caixas (validação: no máximo 3): excesso de alertas · falta de contexto · dificuldade de comparar com o habitual · pouca visibilidade do que já foi decidido · não entender por que algo foi sinalizado · ferramentas separadas · nenhuma dificuldade relevante · outro (texto) | Opcional |

**Seção 5 — Encerramento (todos)**

| # | Pergunta | Tipo de resposta | Regra |
|---|---|---|---|
| 5.1 | Se quiser poder pedir a exclusão da sua resposta, crie um código de resposta (ex.: duas letras e quatro números à sua escolha) e guarde-o. | Resposta curta | Opcional. Não use nome, data de nascimento nem dado pessoal |

Texto final: “Obrigado! Se quiser excluir a sua resposta até {{31/12/2026}}, escreva para {{e-mail institucional da equipe}} informando o código criado. Os resultados agregados serão publicados no repositório do projeto.”

#### Como os dados serão analisados

As respostas são analisadas **por perfil** (Seção 2, 3 e 3G separadas; *proxy* à parte). Só se comparam perfis em itens idênticos (seções 1 e 4, e os pares 2.12 × 3.6) e com interpretação declarada abaixo. Questões fechadas: frequências por perfil. Questões abertas: codificação temática por dois codificadores (Lucas e Marcela), com categorias iniciais “ordem de consulta”, “percepção do anormal”, “confiança na classificação”, “o que acontece depois”, “retomada”, “comunicação de mudanças”, “verificação do efeito”; categorias novas são acrescentadas quando aparecem em pelo menos duas respostas. Com a amostra prevista, os resultados indicam padrões e contradições, não proporções da população.

| Item | Hipótese | Sustenta se… | Refina ou contraria se… | Decisão de interface que depende disso |
|---|---|---|---|---|
| 2.1, 2.2 | H04, H11 | A maioria do bloco Investigação analisa alertas diariamente ou mais, em turno ou plantão | Análise semanal ou só em crises → o panorama de entrada perde prioridade frente ao registro e à retomada | Prioridade do painel de entrada (A01) |
| 2.3, 2.4, 2.5 | H07, H30 | A ordem relatada começa por um indício e passa por contexto antes da decisão | Começa pela classificação da ferramenta e para ali → reforça o risco de tomar classificação por confirmação. Começa por detalhe técnico cru → resumo pode ser secundário | Ordem panorama → recorte → detalhe; o que aparece primeiro no detalhe do alerta |
| 2.7 | H29 | “Frequentemente” ou “sempre” na maioria do bloco | “Raramente/nunca” → a urgência foi superestimada; legibilidade instantânea perde peso frente a completude | Hierarquia visual e quantidade de informação no topo |
| 2.8, 2.9 | H07, H12 | “Ponto de partida e confirmo” é a resposta típica, com situações de desconfiança descritas | “Na maioria das vezes aceito” → a interface precisa separar com mais força classificação e veredito (Entrega 06, 5.1-D) | Rótulos “classificado como…”, separação classificação × veredito |
| 2.10, 2.11 | H31, H30 | Há registro e encaminhamento formais ou informais, e retomada depende de saber o que foi feito | “Não costuma haver registro” → não presumir que o usuário adotará o registro; investigar por quê antes de manter D04 como está | D04 (registro e encaminhamento), passagem de plantão |
| 2.12, 2.13 × 3.6 | H27, R03 | Analistas dizem “raramente/nunca” ou “não sei”, e administradores dizem que avisam | Os dois lados dizem que a comunicação funciona → o indicador de modelo ativo pode ser secundário | Indicador de modelo ativo, aviso de troca (F02.3T) |
| 3.1, 3.2 | H05 | Alterações ocorrem ao menos algumas vezes por ano, motivadas por alertas falsos ou ataques perdidos | Quase ninguém altera → T01 é rara; a área de troca pode ser mais simples e mais guiada | Frequência assumida para T01; quanto ensinar na própria tela |
| 3.3, 3.4, 3.5 | H05, H22 | Verificação prévia de resultados e efeito; risco percebido alto (4–5); reversões acontecem | Risco baixo e nenhuma verificação → confirmação e efeito previsto podem parecer burocracia; testar o custo | Comparação, efeito previsto, confirmação e reversão (D05) |
| 3.7, 3G.3 | H31, H27 | Verificação do efeito depende de dados de antes e depois da mudança | Verificação só pela percepção dos analistas → o sinal “alertas não confirmados” (D05) precisa ser validado | Quadro antes × depois; histórico de trocas (D06) |
| 4.1 | H07, H28 | Itens “uso e me ajuda” indicam convenções conhecidas | “Não conheço” frequente → explicar mais na tela. “Uso, mas ajuda pouco” → investigar por quê na entrevista | Quais componentes manter e quais explicar |
| 4.2, 4.3 | H07, H08 | Respostas citam contexto e motivo do sinal como ajuda | Respostas citam excesso de informação como problema → reduzir o detalhe padrão. **Preferência por resumo não é prova de que o detalhe é dispensável**: cruzar com 2.3–2.5 (o que a pessoa realmente consulta) | Nível de detalhe padrão no detalhe do alerta |

Hipóteses que nenhum item responder continuam **abertas** na rastreabilidade, sem preenchimento por suposição.

---

### Instrumento I02 — Entrevista semiestruturada

**Autor(a) e responsável pela aplicação:** Lucas Kerr do Amaral — 22.123.032-9  
**Técnica:** entrevista semiestruturada individual  
**Objetivo:** compreender a rotina real de investigação de alertas, os critérios de decisão, o que acontece depois da decisão e o vocabulário de quem opera com alertas de rede, com exemplos concretos que o questionário não captura.  
**Público:** analistas de SOC/monitoramento e, em menor número, administradores que configuram ferramentas de detecção.

#### Protocolo de recrutamento e aplicação

| Item | Definição |
|---|---|
| Amostra mínima pretendida | **3** entrevistas: 2 analistas (perfil P01) e 1 administrador (perfil P02); até 5 se houver disponibilidade. Viabilidade: cada sessão exige agendamento com profissional em horário de trabalho |
| Critérios de inclusão | 18 anos ou mais; ao menos 6 meses de atuação profissional (emprego ou estágio) em monitoramento ou configuração de ferramentas de detecção |
| Critérios de exclusão | Integrantes da Equipe 21; quem participou da construção dos protótipos; quem já foi U01/U02 na Entrega 14 (para não misturar avaliação de protótipo com levantamento de prática) |
| Canal de recrutamento | Contatos profissionais diretos dos integrantes e respondentes do I01 que, **fora do formulário**, escreverem ao e-mail da equipe dizendo que aceitam ser entrevistados (o formulário não pede contato) |
| Convite (texto) | “Olá, sou estudante de IHC e estou pesquisando como profissionais investigam alertas de rede. Gostaria de conversar 25–30 minutos, por vídeo ou presencialmente, sobre a sua rotina — sem nenhum dado da sua empresa ou da sua rede. A participação é voluntária e anônima. Podemos marcar?” |
| Responsável | Lucas Kerr do Amaral (entrevistador); Marcela Nalesso (anotadora, quando presente) |
| Modalidade | Remota (chamada de vídeo com **câmera opcional**) ou presencial em sala reservada da instituição; o participante escolhe |
| Duração confirmada | 25–30 minutos de entrevista + 5 de abertura e encerramento, confirmada na entrevista-piloto (não conta na amostra) |
| Sequência de consentimento | Abertura (texto abaixo) → perguntas de consentimento C1–C3 respondidas em voz alta e anotadas antes de qualquer pergunta do roteiro → roteiro → encerramento |
| Registro | **Com autorização de áudio:** gravação só de áudio, no celular do entrevistador em modo avião, transferida em até 24 h para a pasta restrita e apagada do aparelho; transcrição em até 7 dias, já com os dados identificáveis removidos; o áudio é apagado logo após a transcrição. **Sem autorização:** anotações em tempo real pela anotadora (ou pelo entrevistador), em documento sob o código da entrevista, lidas em voz alta ao participante no encerramento |
| Armazenamento e acesso | Pasta do Google Drive da conta institucional de Lucas, compartilhada **somente** com Marcela. A relação código ↔ nome fica numa nota separada dessa pasta, no mesmo Drive, e é apagada junto com os dados. No GitHub entram apenas trechos transcritos sob o código E01, E02… |
| Retenção e descarte | Transcrições e notas até **{{31/12/2026}}**; nessa data Lucas exclui a pasta, a nota de correspondência e cópias locais, e Marcela confirma no registro de decisões. Áudio: apagado após a transcrição (no máximo 7 dias) |

#### Texto de abertura (lido ao participante)

> “Obrigado por aceitar conversar. Sou {{nome}}, estudante de Interação Humano-Computador, e estou com {{nome}}, que vai anotar. Queremos entender como você investiga alertas e como as decisões são tomadas — **não estamos avaliando você nem a sua empresa**. A conversa leva uns 30 minutos. Você pode não responder qualquer pergunta e pode parar a qualquer momento, sem explicar por quê.
>
> Por favor, **não cite** nomes de pessoas, clientes ou da sua empresa, endereços IP, nomes de máquinas ou de redes, senhas nem detalhes da arquitetura. Se precisar de um exemplo, descreva de forma genérica, como ‘um servidor web interno’. Se algo assim escapar, eu paro de anotar aquele trecho.
>
> O que você disser será usado só neste trabalho acadêmico, sob um código como E01, sem o seu nome. Só nós dois teremos acesso às notas, que serão apagadas em {{31/12/2026}}.”

**Perguntas de consentimento (anotadas antes do roteiro):**

- **C1.** “Você aceita participar nessas condições?” — se não, encerrar com agradecimento.
- **C2.** “Você autoriza gravarmos **apenas o áudio**, para transcrever? O áudio é apagado depois da transcrição, em até 7 dias.” — se não, seguir só com anotações.
- **C3.** “Se depois quiser retirar alguma resposta, pode escrever para {{e-mail institucional da equipe}} citando o código {{E0n}}, que vou te passar no final. Tudo bem?”

#### Roteiro

Perguntas abertas primeiro. As categorias da equipe (síntese, contexto, histórico, explicação) **só** entram como sondas, e só depois de o participante trazer o próprio relato sobre o tema.

1. Conte-me como é a sua rotina quando aparece um alerta de rede ou uma atividade suspeita.
2. Pense no último alerta que você investigou. O que você olhou primeiro? E depois?
3. Como você decide se uma ocorrência merece atenção imediata ou pode esperar?
4. Quais informações você usa para decidir se uma conexão é suspeita ou não?
5. Em que ferramentas você busca essas informações? Como passa de uma para outra?
6. O que ajuda você a decidir “há um problema real” ou “é ruído”?
7. Quando a ferramenta já traz uma classificação ou severidade, o que você faz com ela? Quando você desconfia dela?
8. O que falta ou atrapalha nas ferramentas que você usa hoje? *(Antiga 8, agora aberta)*
9. Quando há pressão de tempo, o que muda na forma como você investiga?
10. Depois que você decide, o que acontece? Fica registrado em algum lugar? Para quem vai?
11. Como funciona a passagem de plantão ou a retomada de um caso que ficou em aberto?
12. Você fica sabendo quando alguém altera uma regra, limiar ou modelo da ferramenta de detecção? Como? *(para administradores: como você comunica uma alteração e como verifica o efeito dela?)*
13. Que palavras ou termos você e a sua equipe usam para falar de um alerta que se confirmou, de um que não se confirmou e de um que ficou em dúvida?
14. Como você decide o quanto de detalhe precisa ver antes de concluir? *(Antiga 14, agora aberta)*
15. Há alguma informação que você prefere **não** ver numa tela, por excesso, ruído ou risco de interpretação errada?

**Sondas** (usadas só depois do relato, sem sugerir resposta):

- “Você poderia me dar um exemplo concreto, sem nomes?”
- “O que torna isso crítico ou não crítico?”
- “O que aconteceu em seguida?”
- “Você mencionou {{X}}. Em que momento isso ajuda? Em que momento atrapalha?”
- *Só se o participante já tiver falado do tema:* “Nessa situação, o que faria mais diferença: um resumo, mais contexto da conexão, o histórico do que já foi decidido ou uma explicação de por que foi sinalizado? Por quê?”

#### Texto de encerramento (lido ao participante)

> “Muito obrigado. Antes de terminar, vou resumir o que anotei para você confirmar ou corrigir. {{resumo}} Quer retirar ou mudar alguma coisa? O seu código é **{{E0n}}**; com ele você pode pedir a exclusão das suas respostas até {{31/12/2026}} pelo e-mail {{e-mail institucional da equipe}}. Quando o trabalho terminar, os resultados ficam no repositório do projeto, sem identificação.”

#### Como os dados serão analisados

Codificação temática, feita de forma independente por Lucas e Marcela sobre as transcrições ou notas e depois conciliada. Categorias iniciais: “rotina e ordem de consulta”, “critérios de decisão”, “uso da classificação da ferramenta”, “pressão de tempo”, “o que acontece depois”, “retomada”, “comunicação de mudanças”, “vocabulário”. Para cada hipótese, a análise registra o que foi **sustentado, refinado ou deixado em aberto**, com o trecho que apoia, separando analistas e administradores. A entrevista não é usada para contar preferências: ela explica **por que** os padrões do questionário aparecem, e onde os dois instrumentos discordam, a discordância é registrada em vez de resolvida por suposição.

## Parte C — Consentimento e privacidade aplicados

Regras que valem para os dois instrumentos e que estão escritas no material entregue ao participante (introdução de I01 e abertura de I02):

1. **Não solicitamos nem aceitamos:** senhas; nomes de pessoas, clientes ou organizações; endereços IP, nomes de hosts, sub-redes, topologia; nomes internos de sistemas; capturas de tela de produção; qualquer detalhe que permita reconstruir a infraestrutura.
2. **Se o participante citar algo identificável espontaneamente:** na entrevista, o entrevistador interrompe a anotação daquele trecho, registra só a **categoria** necessária ao estudo (ex.: “servidor web interno”, “empresa do setor financeiro”) e, se houver áudio, o trecho é omitido na transcrição. No questionário, a resposta aberta é editada antes de qualquer citação, substituindo o dado pela categoria entre colchetes; o dado original não é copiado para lugar nenhum.
3. **Sem avaliação individual:** nenhuma pergunta mede desempenho do participante ou da equipe dele, e nenhum resultado é apresentado de forma que permita identificar uma organização.
4. **Mínimo necessário:** não coletamos e-mail, nome, cargo exato, empresa nem cidade. A função é perguntada por descrição de atividade (1.1).
5. **Exclusão:** atendida enquanto a resposta puder ser localizada pelo código (Q do formulário, criado pelo participante; E da entrevista, informado no encerramento) e até a data de descarte.
6. **Acesso e descarte:** só Lucas e Marcela acessam dados brutos; datas e responsáveis de descarte estão nos protocolos de I01 e I02.

O modelo de termo da disciplina ([`../instrumentos/termo_consentimento_modelo.md`](../instrumentos/termo_consentimento_modelo.md)) foi adaptado nesses dois textos: para I01, o aceite é a pergunta 0.1; para I02, as perguntas C1–C3, anotadas com data e código.

## Limitações previstas

- **Participantes *proxy*.** Se só for possível recrutar estudantes ou profissionais de áreas próximas, as respostas deles são analisadas à parte (pergunta 1.3). Um *proxy* pode contribuir para vocabulário e leitura de telas, mas **não valida** práticas de SOC ou de configuração de modelos como se fosse o profissional-alvo.
- **Amostra pequena e por conveniência.** Os resultados indicam padrões; nenhuma resposta isolada transforma hipótese em fato.
- **Perfis de gestão** podem não aparecer; nesse caso, a Seção 3G fica sem dados e as hipóteses relacionadas permanecem abertas.

## Síntese

O questionário e a entrevista se complementam: o questionário mostra **padrões por perfil** sobre frequência, ordem de consulta, uso da classificação da ferramenta, o que acontece depois da decisão e como as alterações são comunicadas; a entrevista explica **por que** esses padrões aparecem, com exemplos. Os dois verificam H04, H05, H07, H11, H12, H22, H27, H28, H29, H30 e H31. Depois da aplicação, a rastreabilidade registra, para cada hipótese, se ela foi **sustentada, refinada ou permaneceu aberta**, qual dado a apoia e qual decisão de interface mudou ou continuou provisória — em especial a priorização da informação, a explicabilidade das classificações, os critérios de incerteza, o registro do veredito, o histórico de mudanças e os limites da comparação de modelos.

## Checklist

- [ ] Hipóteses/lacunas prioritárias da Entrega 1 foram revisitadas.
- [ ] Se o escopo de IHC foi derivado de TCC técnico, a coleta investiga a plausibilidade do usuário, tarefa e contexto adotados (1.1, 2.1, 3.1, 3G.1).
- [ ] Perguntas não pressupõem que dashboard, CRUD, filtros ou relatórios sejam necessários; investigam a necessidade (4.1 pergunta o uso; 2.10 pergunta o que acontece depois da decisão).
- [ ] Cada dado a coletar responde uma dúvida concreta do projeto ou justifica outra necessidade de informação (tabela de análise de I01).
- [ ] Parte A identifica dados e perfis de coleta de forma específica.
- [ ] Aspectos éticos são contextualizados para o projeto e convertidos em material aplicável (Parte C).
- [ ] Há uma técnica completa por integrante e técnicas distintas.
- [ ] Questionário está incluído entre as técnicas.
- [ ] Questionário publicado on-line, com link funcional no documento — **pendente**: preencher {{URL}} e a data de publicação.
- [ ] Cada instrumento possui objetivo, público, procedimento e conteúdo integral.
- [ ] Perguntas evitam indução e coletam apenas dados necessários.
- [ ] Está claro como os dados serão analisados e usados no design.
- [ ] Coleta aplicada e resultados registrados na rastreabilidade — pendente (após a publicação).
