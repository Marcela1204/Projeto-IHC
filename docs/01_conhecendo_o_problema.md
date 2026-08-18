# Entrega 1 — Conhecendo o projeto, o usuário e o problema

**Data:** 13/08/2026  
**Status:** 🟨 em andamento  
**Responsabilidade:** 1 solução consolidada por equipe

## Objetivo da atividade

Reinterpretar o tema do TCC sob a perspectiva de Interação Humano-Computador e construir um **entendimento comum entre os integrantes da equipe**.

A disciplina utiliza preferencialmente o tema do TCC para os exercícios de IHC. Isso vale tanto para TCCs que já preveem uma interface quanto para trabalhos cujo resultado principal é algoritmo, modelo, API, biblioteca, análise de dados, infraestrutura, estudo experimental ou outro artefato técnico.

> **Importante:** a interface projetada na disciplina é um artefato de aprendizagem de IHC. Ela **não se torna automaticamente uma obrigação do TCC**. Sua incorporação ao trabalho de conclusão depende de decisão da equipe e do orientador.

Antes de preencher, leia [`../GUIA_ESCOPO_IHC.md`](../GUIA_ESCOPO_IHC.md).

Nesta primeira semana a equipe **não deve começar desenhando telas**. Primeiro deverá compreender:

- o que o TCC realmente produz;
- quem poderia obter valor dessa contribuição;
- quais pessoas interagem, administram, configuram, interpretam ou são afetadas;
- o que essas pessoas precisam alcançar;
- como atividades relacionadas acontecem hoje;
- problemas, limitações e contexto;
- alternativas existentes;
- qual recorte de interação fará sentido para a disciplina.

Ao final desta entrega, a equipe deve diferenciar:

- **tema do TCC** × **escopo formal do TCC** × **escopo de IHC da disciplina**;
- **objetivo do projeto** × **objetivo do usuário**;
- **problema do usuário** × **solução tecnológica**;
- **fato conhecido** × **hipótese** × **lacuna de conhecimento**;
- **capacidade técnica** × **forma de uso dessa capacidade**;
- **funcionalidade** × **atividade/resultado que o usuário precisa alcançar**;
- **usuário direto** × **stakeholders**.

---

## Como classificar as respostas

Sempre que a resposta fizer uma afirmação sobre usuários, problemas, atividades, necessidades, contexto ou mercado, use:

- **[F] Fato conhecido** — existe evidência/fonte.
- **[H] Hipótese** — afirmação plausível que ainda precisa ser investigada.
- **[?] Não sabemos ainda** — lacuna relevante.

Quando usar `[F]`, informe a origem. Hipóteses prioritárias devem receber IDs (`H01`, `H02`...) e também ser registradas em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).

> **Exemplo:** `[H] H01 — DBAs considerariam útil comparar automaticamente o plano atual de execução com uma recomendação produzida pelo algoritmo.`

Uma hipótese explicitada é melhor do que uma suposição escondida.

---

# 0. Identificação do TCC e da equipe

## 0.1 Membros

| Nome completo | Matrícula | GitHub |
|---|---:|---|
| Lucas Kerr do Amaral | 221230329 | Adelgrin |
| Marcela Nalesso | 222220113 | Marcela1204 |

## 0.2 Título atual do TCC

Tecnologias de Machine Learning para Detecção de Intrusões em Redes de Computadores: Uma Pesquisa Exploratória e Experimental

## 0.3 Orientador(a)

Leonardo Anjoletto Ferreira

## 0.4 Qual é o resultado principal atualmente previsto no TCC?

Marque e descreva:

- [ ] sistema/aplicação interativa;
- [ ] algoritmo;
- [X] modelo de IA/ML/LLM;
    - Utilização de modelos de classificação supervisionada para análise dos dados da rede.
- [ ] biblioteca/API/framework;
- [ ] análise de dataset;
- [X] estudo/benchmark/avaliação experimental;
    - Experimento de um sistema inteligente de redes em regime de tempo real.
- [X] infraestrutura/backend;
    - Utilização de sistemas de virtualização.
- [X] componente embarcado/IoT;
    - Processamento e controle de uma plataforma embarcada, para coletar dados dos sensores e processar as informações em tempo real.
- [X] outro: Indicadores.
    - Avaliar através de tabelas, gráficos e evidências o nível de segurança da rede.

## 0.5 O TCC já previa desenvolvimento de interface com usuário?

- [X] Sim, a interface já faz parte do TCC.
- [ ] Parcialmente; existe alguma interação, mas ainda não está bem definida.
- [ ] Não. O TCC é predominantemente técnico e não previa interface.

**Explique o que está formalmente previsto no TCC:** Desenvolvimento de um sistema de detecção de intrusão baseado em algoritmos de classificação supervisionada, com visualização em dashboard para gerenciamento e monitoramento da segurança de rede.

> Esta resposta serve para separar o compromisso do TCC do projeto da disciplina. Mesmo quando a opção for **não**, a equipe irá definir uma interface para exercitar IHC.

---

# 1. Entendendo a contribuição do projeto

## 1.1 Explique o TCC em uma frase, sem citar linguagem de programação, framework ou banco de dados.

Propomos um sistema inteligente de segurança de redes que identifica e alerta invasões cibernéticas em tempo real, para garantir máxima precisão do tráfego de dados analisado.

## 1.2 Qual situação, atividade ou problema do mundo real motivou o TCC?

> <b>[F]</b> O avanço das redes de computadores e a crescente digitalização de serviços têm ampliado significativamente a exposição de sistemas a ameaças cibernéticas. Esse crescimento é acompanhado por um aumento expressivo no volume de dados trafegados, que passou de aproximadamente 16 GB por usuário ao mês em 2017 para cerca de 50 GB mensais em 2022. Esse cenário contribui diretamente para a ampliação da superfície de ataque, refletindo no aumento da quantidade e da sofisticação de ameaças, como negações de serviço, varreduras de rede e acessos não autorizados.
- Fonte: A. Thakkar e R. Lohiya, “A survey on intrusion detection system: feature selection, model, performance measures, application perspective, challenges, and future research directions,” Artificial Intelligence Review, vol. 54, pp. 4529–4593, 2021. doi: 10.1007/s10462-021-10037-9)

> <b>[F]</b> Os impactos de falhas de segurança tornam-se cada vez mais críticos, sendo que mais de 14 bilhões de registros de dados foram vazados desde 2013, além de prejuízos financeiros significativos, como os 29,8 bilhões de dólares perdidos em golpes telefônicos apenas no ano de 2020.
- Fonte: Z. Azam, M. M. Islam e M. N. Huda, “Comparative Analysis of Intrusion Detection Systems and Machine Learning-Based Model Analysis Through Decision Tree,” 2023. doi: 10.1109/2023.3296444

> <b>[F]</b> Um dos maiores desafios atuais da segurança em redes está relacionado aos ataques de Zero−Day, que exploram vulnerabilidades ainda desconhecidas pelos sistemas de defesa. Por não possuírem assinaturas previamente registradas, esses ataques são difíceis de identificar por métodos tradicionais, funcionando como ameaças invisíveis até que sejam descobertas.
- Fonte: W. S. Admass, Y. Y. Munaye e A. A. Diro, “Cyber security: State of the art, challenges and future directions,” 2023. doi: 10.1016/2023.10031

> <b>[F]</b> Casos reais, como a Operação Aurora, demonstram o potencial destrutivo dessas ameaças, incluindo roubo
de dados sensíveis e comprometimento de infraestruturas críticas.
- Fonte: W. S. Admass, Y. Y. Munaye e A. A. Diro, “Cyber security: State of the art, challenges and future directions,” 2023. doi: 10.1016/2023.10031

## 1.3 Qual é a **capacidade/contribuição central** produzida pelo TCC?

Detectar tentativas de invasão cibernética em uma rede de computadores em tempo real, reduzindo a dimensionalidade dos dados sem perder precisão.

## 1.4 O que se espera que esteja diferente **para pessoas, organizações ou processos** se essa contribuição for bem-sucedida?

- [F] Eficiência no monitoramento em tempo real: Adoção de modelos de baixo tempo de inferência (como Decision Tree com tempo de teste de ~0,003s) viabiliza a detecção instantânea em redes de alto tráfego.  <!-- (Fonte: ???) -->
- [H] Redução do tempo de resposta a incidentes (MTTR): A consolidação dos eventos em um painel modular e visual permitirá que equipes de cibersegurança identifiquem a origem e o tipo de ataque sem precisar analisar logs brutos.
- [H] Viabilidade operacional em hardware limitado: A otimização para plataformas embarcadas reduz os custos de infraestrutura para monitoramento de redes e ambientes de IoT.

## 1.5 O que é mérito técnico/científico do TCC e o que seria uma possível aplicação prática?

| Mérito/contribuição técnica | Possível aplicação/valor em uso |
|---|---|
| [H] Monitoramento em tempo real | [H] Garantia de resposta mais rápida a incidentes comparada com sistemas semelhantes |
| [F] Redução de atributos e otimização: Seleção de 16 a 18 features e uso de PCA mantendo acurácia superior a 95% | [H] Processamento leve para ajudar o processamento em tempo real |
| [F] Pipeline modular de ML: Comparativo entre algoritmos (DT, RF, KNN, SVM, LR) para classificação de tráfego | [H] Painel de controle que permite ao analista trocar o algoritmo de detecção conforme o perfil da rede |
| [F] Agrupamento e classificação de ataques: Agrupamento das ameaças nas macrocategorias DoS, Probe, R2L e U2R | [H] Dashboard de segurança com visualização de riscos categorizados e alertas em tempo real |
<!-- (Fonte: ???) -->
---

# 2. Entendendo as pessoas envolvidas

## 2.1 Quem interage diretamente com o produto, se já existe interface prevista?

Se não houver interface prevista no TCC, escreva `NÃO SE APLICA AO ESCOPO ORIGINAL` e prossiga para 2.2.

[H] Analistas de segurança da informação (SOC), administradores de rede e pesquisadores/gestores de TI.

## 2.2 Quem poderia **usar, configurar, administrar, operar, interpretar ou tomar decisões** a partir da contribuição técnica?

Considere perfis profissionais e stakeholders, não apenas consumidores finais.

| Perfil | Relação com a contribuição | O que faria | Status/evidência |
|---|---|---|---|
| Analista | Gerenciador | Interage diretamente com a interface | [F] |
| Diretor | Contratante | Contrata o serviço e verifica a diminuição em casos de vazamento | [F] |
| Analista de Segurança | Operar e Interpretar | Monitorar o tráfego em tempo real no dashboard, avaliar alertas de invasão e conter ameaças | [H] |
| Administrador de Rede | Configurar e Administrar | Ajustar parâmetros de captura de rede, selecionar algoritmos ativos e configurar a plataforma física/embarcada | [H] |
| Gestor de Segurança | Tomar decisões | Visualizar relatórios consolidados, avaliar taxas de ataque e decidir sobre investimentos em infraestrutura | [H] |
<!-- (Fonte: ???) -->

## 2.3 Existem pessoas afetadas que não usariam a interface diretamente?

| Stakeholder | Como é afetado | Usa interface? | Status/evidência |
|---|---|---|---|
| Contribuintes | Garante a segurança para o uso da rede | Não | Usuário desta mesma rede |
| Usuários finais da rede | Têm seus serviços mantidos (disponibilidade) e seus dados protegidos contra vazamentos | Não | [F] |
| Diretoria / Clientes da empresa | Evitam prejuízos financeiros e danos de reputação decorrentes de sequestro ou vazamento de dados | Não | [F] |
<!-- (Fonte: ???) -->

## 2.4 Que características desses perfis podem influenciar a interação?

- [H] Analistas de SOC estão acostumados a gerenciar redes com ferramentas similares, para estes casos o sistema implementado é uma melhoria do trabalho já existente.
- [F] Exigência de resposta rápida: O contexto de cibersegurança exige tomar decisões instantâneas para conter ataques em andamento.  
- [H] Familiaridade com palavras técnicas: O usuário compreende conceitos de rede (portas, protocolos, pacotes, flags SYN), mas necessita que esses dados venham pré-processados e visualmente resumidos.
- [H] Muita informação ao mesmo tempo: Sob ataque ativo, a interface deve evitar excesso de dados visuais desnecessários e priorizar alertas de alta severidade.
<!-- (Fonte: ???) -->
---

# 3. Entendendo objetivos e atividades

## 3.1 O que o usuário está tentando conseguir no mundo real?

- [H] Garantir um acesso mais seguro a uma rede de computadores, e evitar vazamento de dados permitindo uma resposta rápida a incidentes.

- [H] Manter a rede operacional e segura, identificando e mitigando ameaças antes que comprometam a disponibilidade, integridade ou confidencialidade dos dados.

## 3.2 Quais são as atividades mais importantes?

| ID | Atividade/objetivo | Quem realiza | Frequência/criticidade inicial | Status/evidência |
|---|---|---|---|---|
| A01 | Monitoramento | Analista de Segurança | Constante | Análise do tráfego de rede em tempo real para identificar anomalias |
| A02 | Gerenciamento | Analista de Segurança | Constante | Análise de detalhes de um alerta de ataque (origem, categoria DoS/Probe/R2L/U2R) |
| A03 | Configuração | Administrador | Mensalmente | Alternância do modelo de Machine Learning ativo conforme exigência do ambiente |

## 3.3 Qual atividade parece mais frequente? Por quê?

[H] A01, pois os fluxos de pacotes chegam ininterruptamente na infraestrutura e exigem observação contínua de métricas agregadas de saúde da rede

## 3.4 Qual parece mais crítica? Que consequência existe se for mal executada?

[H] A02, Se for mal executada ou demorada, um ataque destrutivo (como exfiltração de dados R2L/U2R) pode se consolidar na rede, gerando vazamento de dados sensíveis ou indisponibilidade total dos serviços.

---

# 4. Entendendo o problema ou processo atual

## 4.1 Como essas atividades são realizadas hoje, antes da interface imaginada na disciplina?

[F] Análise manual/semi-automatizada por meio de logs de rede, ferramentas de captura de pacotes, consoles de linha de comando ou sistemas IDS tradicionais baseados exclusivamente em regras e assinaturas fixas (tais como Snort, Suricata, Cisco Secure, Zeek, Wazuh, ClamAV, Palo Alto, Sophos, Windows Defender, Security Onion e outros)
<!-- (Fonte: ???) -->

## 4.2 O que é difícil, demorado, confuso, repetitivo, arriscado ou pouco transparente?

- [F] Incapacidade de identificar ataques inéditos (Zero-Day) por falta de assinatura prévia.  
- [F] Volume excessivo de dados trafegados e alta quantidade de falsos positivos gerados por sistemas legados de detecção de anomalias.  
- [H] Dificuldade de correlacionar dezenas de métricas de rede brutas (como taxas de erro SYN ou contagem de portas) sem uma ferramenta de síntese visual
<!-- (Fonte: ???) -->

## 4.3 Que informações o profissional precisa interpretar para tomar decisão?

- [F] Tipo e protocolo do tráfego (TCP, UDP, ICMP), serviço acessado, volume de bytes enviados/recebidos e duração da conexão.  
- [F] Taxa de erros de conexão (ex: rerror_rate, serror_rate), frequência de acesso ao mesmo host/porta e flags de autenticação (logged_in).  
- [F] Categoria prevista da anomalia (Normal, DoS, Probe, R2L, U2R) e nível de confiança do modelo.
<!-- (Fonte: ???) -->

## 4.4 O que acontece quando a atividade falha ou quando o resultado é interpretado incorretamente?

- [F] Falso Negativo (Ataque ignorado): Invasores ganham controle da rede, elevam privilégios ou causam indisponibilidade de serviços essenciais.  
- [F] Falso Positivo (Tráfego legítimo bloqueado): Serviços do negócio são interrompidos indevidamente, gerando sobrecarga nas equipes de TI para liberar acessos.
<!-- (Fonte: ???) -->

## 4.5 Conte uma situação concreta.

[H] Durante o plantão noturno, o analista Lucas observa uma lentidão pontual nos servidores Web. Ele abre o console tradicional e se depara com milhares de linhas de log cruas. Sem saber se é um pico legítimo de acessos ou um ataque de Probe/DoS, ele leva 40 minutos filtrando o tráfego manualmente. Nesse intervalo, a invasão se consolida, resultando na queda do serviço e no vazamento de credenciais.

## 4.6 Que evidência existe hoje?

| Evidência/fonte | O que sustenta | Limitação |
|---|---|---|
| Experimentos com dataset NSL-KDD no MVP 1 | Demonstra alta taxa de acurácia (99,7%) da Decision Tree e tempo de inferência rápido (0,003s) para 18 atributos | Avaliação realizada em dataset estático, pendente de validação com tráfego real dinâmico |
| Revisão bibliográfica do artigo | Confirma que modelos tradicionais geram altos falsos positivos e que a redução de dimensionalidade é chave para tempo real | Foco primariamente acadêmico e conceitual. |
<!-- (Fonte: ???) -->

---

# 5. Entendendo o contexto de uso

## 5.1 Onde e em quais situações a interação poderia ocorrer?

[H] Em salas de centro de operações de segurança (SOC), ambientes de TI corporativos ou estações de trabalho de administradores de rede, sob operação normal ou em situações de crise/incidente crítico.

## 5.2 Em quais dispositivos/equipamentos?

[H] Monitores e workstations de trabalho (para visualização do dashboard) conectados a servidores centrais ou placas embarcadas de monitoramento em tempo real

## 5.3 Existem condições físicas relevantes?

[H] Uso contínuo em ambientes com múltiplos monitores, iluminação controlada (uso comum de modo escuro/Dark Mode) e pressão de tempo para tomadas de decisão sob incidentes.

## 5.4 Existem fatores sociais ou organizacionais?

[H] Hierarquia operacional onde o analista L1 monitora os alertas iniciais, o analista L2 investiga a fundo e o gestor avalia os relatórios consolidados de conformidade e segurança.

## 5.5 Existe necessidade de histórico, rastreabilidade ou auditoria?

[F] Sim, a retenção de históricos de tentativas de invasão e métricas de acerto do modelo é fundamental para auditorias de segurança e conformidade da infraestrutura
Fonte: ???

## 5.6 Um erro pode produzir consequência relevante? Qual?

[F] Sim. A não identificação de uma intrusão (falso negativo) pode acarretar perdas financeiras massivas e comprometimento de infraestruturas críticas.
Fonte: ???

---

# 6. Entendendo mercado e alternativas existentes

> Nesta entrega faça apenas um **levantamento inicial**. A análise aprofundada ocorre na Entrega 2.

## 6.1 Como pessoas resolvem problemas semelhantes hoje?

| Alternativa atual | Quem usa | Para quê | Status/evidência |
|---|---|---|---|
| IDSs Tradicionais | Analistas / Administradores de rede | Monitorar tráfego com base em regras e assinaturas estáticas | [F] |
| Dashboards Genéricos (ex: Grafana, Metabase) | Equipes de TI / DevOps | Visualizar métricas de infraestrutura e logs agregados | [F] |
| Scripts em Python / Notebooks | Pesquisadores / Cientistas de Dados |Treinar e validar modelos de ML offline | [F] |

## 6.2 Existem produtos que atuam na mesma área, mesmo sem serem equivalentes ao TCC?

[F] Sim. Ferramentas comerciais como Splunk, Elastic SIEM, Datadog, Snort, Suricata, Cisco Secure, Zeek, Wazuh, ClamAV, Palo Alto, Sophos, Windows Defender, Security Onion e outros, além de soluções de NIDS com módulo de IA.
Fonte: ???

## 6.3 Quais interfaces profissionais esse público já conhece?

[F] Painéis de monitoramento como Grafana e Metabase, sistemas como CasaOS e ferramentas de gerenciamento de logs.
Fonte: ???

## 6.4 O que essas soluções parecem fazer bem?

[H] Exibir gráficos de linha de tempo de tráfego, permitir filtros avançados e integrar múltiplas fontes de dados.

## 6.5 O que parecem fazer mal, dificultar ou não atender?

[H] Apresentam alta complexidade de configuração, exigem atualização constante de assinaturas para novos ataques e geram poluição visual com excesso de alertas irrelevantes.

## 6.6 Que padrões de interface ou vocabulário parecem familiares a esse público?

[H] Gráficos de rosca/pizza para distribuição de tráfego (Normal vs. Ataques), linhas do tempo para taxas de pacotes, cartões numéricos com KPIs (Acurácia, Latência, Alertas Ativos) e tabelas com códigos de cores de severidade.

---

# 7. Derivando o escopo de IHC da disciplina

## 7.1 Escolha o caminho do projeto

### Caminho A — TCC já possui interface

O TCC contempla o desenvolvimento de um protótipo de IDS em tempo real acoplado a um dashboard para gerenciamento e monitoramento da segurança da rede. O recorte de IHC focará na interface de monitoramento e controle operacional do IDS, permitindo ao usuário acompanhar o tráfego em tempo real, visualizar a classificação do modelo (Decision Tree e outros), inspecionar detalhes dos incidentes detectados e alternar/configurar os modelos de ML em execução.

## 7.2 Qual perfil será priorizado no projeto de IHC?

Analista de Segurança de Rede (SOC Analyst).

**Por que esse perfil foi escolhido?** Pois é a pessoa responsável pela tomada de decisão rápida e contínua no monitoramento diário da infraestrutura, sofrendo o impacto direto da usabilidade do painel sob cenários de ataque em tempo real.

## 7.3 Qual objetivo desse usuário será priorizado?

Identificar, categorizar e validar tentativas de intrusão cibernética em tempo real, monitorando a performance dos algoritmos de detecção.

## 7.4 Que interface será explorada na disciplina?

Complete:

> Para fins da disciplina de IHC, será projetada uma interface que permita ao Analista de Segurança de Rede utilizar a capacidade do algoritmo de ML de classificar tráfego em tempo real com alta precisão e baixo tempo de resposta para detectar e mitigar invasões cibernéticas, no contexto de monitoramento de um Centro de Operações de Segurança (SOC).

## 7.5 Qual é a relação dessa interface com o TCC?

- [X] Já fazia parte do TCC.
- [ ] É um aprofundamento de algo parcialmente previsto.
- [ ] É uma extensão conceitual criada para a disciplina.
- [ ] É um protótipo demonstrativo de aplicação potencial.
- [ ] Outra: {{...}}.

> **Declaração:** a interface desenvolvida nesta disciplina é um artefato de aprendizagem de IHC baseado no tema do TCC. Sua inclusão ou implementação no TCC somente ocorrerá se isso for posteriormente decidido pela equipe e pelo orientador.

---

# 8. Levantando possibilidades de interação — sem desenhar ainda

A equipe pode registrar possibilidades para investigação. **Não significa que todas serão implementadas.**

Marque apenas as que parecem plausíveis e explique o objetivo correspondente.

| Possibilidade | Pode fazer sentido? | Objetivo/tarefa que justificaria | Evidência atual |
|---|---|---|---|
| Dashboard/visão geral | Sim | Exibir saúde da rede, volume de tráfego e proporção entre tráfego normal e ataques | [F] |
| Configuração/parametrização | Sim | Selecionar e alterar o algoritmo de ML ativo no pipeline em tempo real | [F] |
| Entrada/upload/seleção de dados | Sim | Escolher fontes/interfaces de captura de rede ou importar conjuntos de dados para teste | [F] |
| Acompanhamento de processamento | Sim | Monitorar métricas de hardware/sistema (CPU, RAM, latência e tempo de teste do modelo) | [F] |
| Relatório/resultados | Sim | Exportar históricos de ataques e métricas consolidadas de acurácia/f1-score | [F] |
| Histórico com busca/filtros | Sim | Filtrar conexões por protocolo, tipo de ataque (DoS, Probe, R2L, U2R) e horário | [F] |
| Comparação de resultados | Sim | Comparar métricas de performance entre algoritmos (ex: Decision Tree vs. Random Forest) | [F] |
| Explicabilidade/detalhamento | Sim | Exibir os atributos mais relevantes (ex: src_bytes, count, dst_host_srv_count) que levaram o modelo a classificar o ataque. | [F] |
| Administração/configurações globais | Talvez | Definir limites de alerta ou limites de captura de pacotes | [H] |
| Usuários/perfis/permissões | Não | Não é prioridade central para o recorte pedagógico do escopo de IHC | [H] |
| CRUD de entidade do domínio | Não | O domínio é voltado a fluxo contínuo de eventos/logs, não cadastro de dados estáticos | [H] |
| Auditoria/logs | Sim | Registrar ações efetuadas pelo analista mediante logs do sistema | [F] |
| Alertas/ocorrências | Sim | Notificar visualmente quando ataques de alto risco (R2L/U2R) forem detectados | [F] |
| Ajuda/documentação | Talvez | Oferecer guia com descrição das classes de ataque para analistas iniciantes | [H] |

<!-- (Fonte: ???) --> @Adelgrin E @Marcela1204

> **Atenção:** “login + dashboard + CRUD” não é uma solução universal. Cada padrão deve surgir de uma tarefa real.

---

# 9. Benefícios e ações iniciais

## 9.1 Qual benefício concreto o projeto de IHC pretende oferecer?

| Benefício esperado | Problema/necessidade | Usuário | Status/evidência |
|---|---|---|---|
| Redução no tempo de identificação de ataques | Dificuldade em analisar logs cruos de rede sob ataque ativo | Analista de Segurança | [H] |
| Clareza na troca de modelos e diagnósticos | Falta de visibilidade sobre qual modelo de ML performa melhor no tráfego atual | Administrador de Rede / Analista |[H]|

## 9.2 Que ações o usuário deverá conseguir realizar?

| ID | O usuário precisa conseguir... | Para alcançar... | Prioridade inicial |
|---|---|---|---|
| F01 | Visualizar a taxa de tráfego de rede e detecção de ataques em tempo real | Avaliar o estado atual de segurança da infraestrutura | Alta |
| F02 | Inspecionar os atributos detalhados de uma conexão sinalizada como ataque | Confirmar a veracidade do incidente (evitar falso positivo) | Média |
| F03 | Alternar o algoritmo de classificação (ex: Decision Tree, Random Forest) via interface | Otimizar a detecção de acordo com os recursos disponíveis | Média |

## 9.3 Tecnologias/restrições já definidas no TCC

A tecnologia aparece **agora**, depois do entendimento do uso.

| Tecnologia/restrição | Por que existe | Possível impacto na interação |
|---|---|---|
| Modelos em Python / Scikit-Learn | Definido para treinamento e inferência dos classificadores no TCC | A interface precisa comunicar-se de forma eficiente com o backend para não introduzir latência visual |
| Execução em Sistema Embarcado | Requisito do TCC para rodar a solução em tempo real na borda | Exige uma interface web leve e responsiva, sem consumo excessivo de recursos da máquina |

---

# 10. Hipóteses e dúvidas prioritárias

| ID | Hipótese/dúvida | Por que importa | Como poderá ser investigada |
|---|---|---|---|
| H01 | {{...}} | {{...}} | Entrega 2/3/7/... |
| H02 | {{...}} | {{...}} | {{...}} |
| H03 | {{...}} | {{...}} | {{...}} |

Registre em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).

---

# 11. Síntese da equipe

| Pergunta | Síntese atual |
|---|---|
| Qual é a contribuição central do TCC? | Um sistema/modelo otimizado de ML capaz de detectar invasões em tráfego de rede em tempo real |
| O TCC já previa interface? | Sim, previa um dashboard para gerenciamento e monitoramento da segurança da rede |
| Quem é o usuário prioritário de IHC? | Analista de Segurança de Rede (SOC Analyst) |
| O que ele precisa alcançar? | Detectar e validar ameaças à rede de forma rápida e precisa |
| Qual problema/atividade será estudado? | O monitoramento de tráfego e a interpretação de alertas de anomalia |
| Como isso acontece hoje? | Por análise manual de logs ou IDSs baseados em regras rígidas |
| Qual é o contexto de uso? | Centros de Operações de Segurança (SOC) e ambientes corporativos de rede |
| Que interface/recorte será explorado? | Dashboard de monitoramento de tráfego em tempo real e controle de algoritmos do IDS |
| Como a interface se relaciona ao TCC? | Já fazia parte do escopo previsto no TCC |
| Quais pontos ainda são hipóteses? | xxx |
<!-- Aqui precisa colocar [F], [H] ou [?]-->

### Delimitação

**Dentro do escopo de IHC:** Projeto do dashboard de monitoramento em tempo real, visualização de alertas por categoria (DoS, Probe, R2L, U2R), painel de métricas dos modelos e controles para alternar classificadores.
**Fora do escopo de IHC:** Virtualização de SO, configuração de baixo nível dos adaptadores de rede físicos e treinamento offline dos modelos de IA. 
**Dentro do escopo formal do TCC:** Pipeline de captura de dados, seleção de atributos, treinamento e benchmark de modelos em hardware embarcado. 
**Interface da disciplina será implementada no TCC?** Sim — A interface dashboard já estava prevista na evolução da arquitetura do TCC (MVP 2).

---

# 12. Como esta entrega alimenta as próximas

- **Entrega 2:** verifica mercado, concorrentes e interfaces profissionais representativas.
- **Entrega 3:** detalha perfis e contexto.
- **Entrega 4:** aprofunda situações problemáticas.
- **Entrega 5:** modela tarefas centrais.
- **Entrega 6:** experimenta alternativas em baixa fidelidade.
- **Entrega 7:** investiga hipóteses com dados.
- **Entrega 8:** define restrições e metas de usabilidade.
- **Entregas 9–11:** transformam o recorte em modelo de interação e protótipo.
- **Entregas 12–14:** avaliam a interface construída na disciplina.

A Entrega 1 é uma **fotografia inicial do conhecimento**. Ela pode e deve ser revisada quando surgirem evidências.

---

# 13. Relação com INOVA e comunicação do projeto

Prepare uma explicação de até três frases:

1. **Problema/atividade humana:** Organizações enfrentam volume massivo de conexões e ataques cibernéticos sofisticados, tornando a análise manual de redes lenta, propensa a falhas e estressante para analistas de segurança.
2. **Contribuição técnica do TCC:** Desenvolvemos um modelo e pipeline inteligente de Machine Learning leve e otimizado para detectar tentativas de invasão em tempo real.
3. **Como uma pessoa poderia utilizar essa contribuição:** Através de um dashboard de monitoramento que traduz dados complexos de tráfego em alertas visuais diretos, permitindo identificar e conter ameaças na rede instantaneamente.

Essa síntese ajuda a apresentar o projeto para público não especializado sem reduzir seu mérito técnico.

---

# Checklist de qualidade

- [ ] Está clara a diferença entre tema do TCC, escopo formal do TCC e escopo de IHC.
- [ ] A equipe declarou se o TCC já previa interface.
- [ ] Se não previa, foi derivado um usuário plausível e um objetivo de uso.
- [ ] A interface de IHC não foi apresentada como obrigação automática do TCC.
- [ ] A contribuição do TCC foi descrita sem começar por tecnologias de implementação.
- [ ] Usuários diretos e stakeholders foram diferenciados.
- [ ] Foram considerados profissionais que configuram, administram, interpretam ou decidem, quando pertinente.
- [ ] Objetivo do usuário não foi confundido com objetivo do projeto.
- [ ] Processo/problema atual foi descrito antes da solução.
- [ ] Existe situação concreta de uso/problema.
- [ ] Contexto físico, social/organizacional, dispositivos e consequências de erro foram considerados.
- [ ] Mercado/alternativas existentes foram levantados inicialmente.
- [ ] Possibilidades como dashboard, relatório, histórico, filtros e CRUD foram tratadas como hipóteses de solução, não como requisitos automáticos.
- [ ] Cada possibilidade de interface tem um objetivo/tarefa que poderia justificá-la.
- [ ] Afirmações relevantes estão marcadas `[F]`, `[H]` ou `[?]`.
- [ ] Hipóteses prioritárias receberam IDs e foram para a rastreabilidade.
- [ ] O recorte de IHC é viável para modelar, prototipar e avaliar no semestre.
- [ ] A equipe consegue explicar problema humano → contribuição computacional → forma de uso.
