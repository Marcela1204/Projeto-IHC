# Entrega 1 — Conhecendo o projeto, o usuário e o problema

**Data:** 13/08/2026  
**Status:** `🟩 concluída`
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

Tecnologias de Machine Learning para Detecção de Intrusões em Redes de Computadores: Uma Pesquisa Exploratória e Experimental.

## 0.3 Orientador(a)

Leonardo Anjoletto Ferreira.

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

> **Três níveis de afirmação usados neste documento** (revisão a partir do feedback da Entrega 01, item 1):
>
> 1. **Resultado técnico relatado** — `[F]` com medição ou fonte. Ex.: acurácia de 99,7% e tempo de inferência de ~0,003 s da Decision Tree sobre o dataset NSL-KDD (MVP 1).
> 2. **Capacidade prevista no TCC** — `[F] (capacidade definida no TCC)`: decisão interna do projeto, já formalizada no escopo, que não exige comprovação externa. Ex.: o pipeline permitirá alternar o classificador ativo.
> 3. **Benefício de uso hipotético** — `[H]`: efeito esperado sobre o trabalho humano (compreender mais rápido, errar menos, decidir com mais segurança). Só pode ser sustentado por investigação com usuários (Entrega 07) e por avaliação de usabilidade (Entregas 12–14).
>
> Desempenho computacional pertence ao nível 1 e **não demonstra, sozinho**, um item do nível 3. A limitação registrada em 4.6 — experimentos em dataset estático, pendentes de validação com tráfego real — acompanha todas as conclusões das seções 1 e 13.


## 1.1 Explique o TCC em uma frase, sem citar linguagem de programação, framework ou banco de dados.

Propomos um sistema inteligente de segurança de redes que classifica o tráfego em tempo real e sinaliza possíveis tentativas de invasão, apresentando o resultado a um profissional que o interpreta e decide o encaminhamento.

> **Nota de revisão:** a redação anterior dizia “para garantir máxima precisão”. A acurácia obtida no MVP 1 é um resultado experimental em dataset estático (4.6), não uma garantia do sistema em operação.

## 1.2 Qual situação, atividade ou problema do mundo real motivou o TCC?

> <b>[F]</b> O avanço das redes de computadores e a crescente digitalização de serviços têm ampliado significativamente a exposição de sistemas a ameaças cibernéticas. Esse crescimento é acompanhado por um aumento expressivo no volume de dados trafegados, que passou de aproximadamente 16 GB por usuário ao mês em 2017 para cerca de 50 GB mensais em 2022. Esse cenário contribui diretamente para a ampliação da superfície de ataque, refletindo no aumento da quantidade e da sofisticação de ameaças, como negações de serviço, varreduras de rede e acessos não autorizados.
- Fonte: A. Thakkar e R. Lohiya, “A survey on intrusion detection system: feature selection, model, performance measures, application perspective, challenges, and future research directions,” Artificial Intelligence Review, vol. 54, pp. 4529–4593, 2021. doi: 10.1007/s10462-021-10037-9

> <b>[F]</b> Os impactos de falhas de segurança tornam-se cada vez mais críticos, sendo que mais de 14 bilhões de registros de dados foram vazados desde 2013, além de prejuízos financeiros significativos, como os 29,8 bilhões de dólares perdidos em golpes telefônicos apenas no ano de 2020.
- Fonte: Z. Azam, M. M. Islam e M. N. Huda, “Comparative Analysis of Intrusion Detection Systems and Machine Learning-Based Model Analysis Through Decision Tree,” 2023. doi: 10.1109/2023.3296444

> <b>[F]</b> Um dos maiores desafios atuais da segurança em redes está relacionado aos ataques de Zero−Day, que exploram vulnerabilidades ainda desconhecidas pelos sistemas de defesa. Por não possuírem assinaturas previamente registradas, esses ataques são difíceis de identificar por métodos tradicionais, funcionando como ameaças invisíveis até que sejam descobertas.
- Fonte: W. S. Admass, Y. Y. Munaye e A. A. Diro, “Cyber security: State of the art, challenges and future directions,” 2023. doi: 10.1016/2023.10031

> <b>[F]</b> Casos reais, como a Operação Aurora, demonstram o potencial destrutivo dessas ameaças, incluindo roubo de dados sensíveis e comprometimento de infraestruturas críticas.
- Fonte: W. S. Admass, Y. Y. Munaye e A. A. Diro, “Cyber security: State of the art, challenges and future directions,” 2023. doi: 10.1016/2023.10031

## 1.3 Qual é a **capacidade/contribuição central** produzida pelo TCC?

Classificar o tráfego de uma rede de computadores em tempo real, sinalizando possíveis tentativas de invasão, com um conjunto reduzido de atributos. Nos experimentos do MVP 1, a redução de dimensionalidade manteve acurácia superior a 95% sobre o dataset NSL-KDD.

## 1.4 O que se espera que esteja diferente **para pessoas, organizações ou processos** se essa contribuição for bem-sucedida?

**Nível 1 — resultado técnico relatado:**

- [F] O tempo de inferência medido no MVP 1 para a Decision Tree foi de aproximadamente 0,003 s por amostra, sobre o dataset NSL-KDD. Isso descreve o **custo computacional da classificação** e não o tempo que uma pessoa leva para perceber um alerta, compreender sua relevância e decidir o próximo passo.
  - Fonte: [MVP1 — resultados de desempenho dos classificadores](../assets/01_dados_mvps/mvp1.pdf)

**Nível 2 — capacidade prevista no TCC:**

- [F] (capacidade definida no TCC) A cada conexão analisada o sistema associa uma **categoria prevista** (Normal, DoS, Probe, R2L, U2R) e um **grau de confiança**, em fluxo contínuo.
- [F] (capacidade definida no TCC) O pipeline foi projetado para executar em plataforma embarcada, o que delimita o custo de infraestrutura do **processamento** — ver 9.3 para a distinção entre equipamento de processamento e equipamento de interação.

**Nível 3 — benefício de uso hipotético:**

- [H01] A consolidação das ocorrências em um painel visual **poderá** reduzir o tempo que o analista leva para identificar a origem e o tipo de uma ocorrência, em comparação com a leitura de logs brutos. Não há evidência disso; a verificação está prevista para as Entregas 12–14 (ver também H26).
- [H02] A execução em hardware limitado **poderá** reduzir o custo de monitoramento em redes e ambientes de IoT. O efeito dessa restrição sobre a interação é discutido em 9.3.


## 1.5 O que é mérito técnico/científico do TCC e o que seria uma possível aplicação prática?

| Nível 1/2 — mérito técnico ou capacidade prevista | Nível 3 — possível valor em uso (hipótese) |
|---|---|
| [F] Classificação de cada conexão em fluxo contínuo, com tempo de inferência de ~0,003 s medido no MVP 1 | [H01] O analista poderá perceber uma ocorrência mais cedo do que lendo logs manualmente. Não é uma comparação demonstrada com outros sistemas: nenhum concorrente foi cronometrado |
| [F] Redução de atributos: seleção de 16 a 18 *features* e uso de PCA mantendo acurácia superior a 95% sobre o NSL-KDD | [F] (capacidade) Viabiliza o processamento contínuo em hardware embarcado. Não afirmamos efeito sobre o esforço do analista |
| [F] (capacidade) Pipeline modular de ML: comparativo entre DT, RF, KNN, SVM e LR para classificação de tráfego | [F] (capacidade) A troca do classificador ativo está prevista no TCC. [H27] Que essa troca seja útil e compreensível para o perfil escolhido é hipótese; quem a realiza está discutido em 7.3 |
| [F] (capacidade) Agrupamento das ameaças nas macrocategorias DoS, Probe, R2L e U2R | [H21] A categorização poderá ajudar o analista a decidir o que investigar primeiro. A adequação dessas quatro macrocategorias ao trabalho real não foi verificada |


---

# 2. Entendendo as pessoas envolvidas

## 2.1 Quem interage diretamente com o produto, se já existe interface prevista?

[H03] Analistas de segurança da informação (SOC), administradores de rede e pesquisadores/gestores de TI.

## 2.2 Quem poderia **usar, configurar, administrar, operar, interpretar ou tomar decisões** a partir da contribuição técnica?

Considere perfis profissionais e stakeholders, não apenas consumidores finais.

| Perfil | Relação com a contribuição | O que faria | Status/evidência |
|---|---|---|---|
| Analista de Segurança (SOC) | Operar e interpretar | Observar o estado do tráfego no painel, inspecionar uma conexão sinalizada, julgar se a classificação corresponde a um incidente e **encaminhar** a resposta. Não executa a contenção pela interface — ver o quadro no fim da seção 2 | [H04] papel suposto; nenhum analista foi entrevistado ou observado até aqui |
| Administrador de Rede | Configurar e administrar | Ajustar parâmetros de captura, selecionar o classificador ativo e configurar a plataforma física/embarcada. A troca de modelo pertence a este perfil; sua relação com o fluxo do analista está explicada em 7.3 | [H05] papel suposto |
| Gestor de Segurança | Tomar decisões | Consultar resultados consolidados e decidir sobre investimento em infraestrutura | [H06] papel suposto. **Decisão de recorte:** permanece como *stakeholder*, sem persona nem tela própria na disciplina (ver Entrega 03). Essa decisão delimita o projeto; ela não refuta a hipótese de que gestores consultem relatórios |


## 2.3 Existem pessoas afetadas que não usariam a interface diretamente?

| Stakeholder                     | Como é afetado                                                                                   | Usa interface? | Status/evidência |
| ------------------------------- | ------------------------------------------------------------------------------------------------ | -------------- | ---------------- |
| Usuários finais da rede | São afetados pela disponibilidade dos serviços e pela exposição dos seus dados. A manutenção do serviço e a proteção dos dados são o **resultado pretendido** | Não | [H] Resultado esperado, não consequência assegurada pela existência do sistema |
| Diretoria / Clientes da empresa | São afetados por prejuízo financeiro e dano de reputação decorrentes de vazamento ou indisponibilidade. A redução desses prejuízos é o resultado pretendido | Não | [H] Resultado esperado; depende da eficácia da detecção **e** da resposta humana e organizacional que vem depois dela |


## 2.4 Que características desses perfis podem influenciar a interação?

- [H28] **Familiaridade com ferramentas semelhantes:** analistas de SOC provavelmente já operam ferramentas de monitoramento e triagem. A seção 6 documenta a **existência** dessas ferramentas; ela não comprova a familiaridade do público específico deste projeto, nem que a solução seja “uma melhoria do trabalho já existente”. Investigação na Entrega 07.
- [H29] **Pressão de tempo:** a literatura descreve a resposta a incidentes como sensível ao tempo, mas não sabemos qual é a janela real de decisão do analista nem como ele distribui o tempo entre perceber, investigar e decidir. A expressão “decisões instantâneas” foi retirada: ela antecipava uma medida que o projeto ainda precisa levantar.
- [H07] **Vocabulário técnico:** supomos que o usuário compreende conceitos de rede (portas, protocolos, pacotes, *flags* SYN) e ainda assim precisa que esses dados cheguem pré-processados e resumidos. São duas afirmações distintas e nenhuma foi verificada.
- [H08] **Carga informacional sob pressão:** supomos que, durante uma ocorrência ativa, a interface deve evitar excesso de dados visuais e destacar o que exige ação. É hipótese de design, a ser testada nas Entregas 12–14.



**Quadro complementar — limite entre detectar, interpretar e conter**

> Acrescentado pela equipe na revisão (feedback E01, item 2), **sem criar pergunta nova** na numeração do professor. Serve para ajustar o **compromisso declarado** pelo documento; nenhuma funcionalidade nova foi acrescentada ao projeto.

| Etapa | Quem/o que realiza | Resultado produzido | Está no recorte de IHC? |
|---|---|---|---|
| **Classificar** | Modelo de ML do TCC | Categoria prevista (Normal, DoS, Probe, R2L, U2R) e grau de confiança, associados a uma conexão/fluxo | Sim — a interface **apresenta** esse resultado |
| **Interpretar** | Analista de Segurança | Julgamento sobre se a classificação corresponde a uma ocorrência real, considerando origem, destino, serviço, volume e histórico | Sim — é o foco do projeto de IHC |
| **Decidir o encaminhamento** | Analista de Segurança | Descartar como falso positivo, confirmar como incidente, ou escalar/solicitar ação a outro responsável | Sim — a interface registra a decisão |
| **Conter** (bloquear, isolar, derrubar serviço) | Firewall/IPS, equipe de infraestrutura ou administrador — **fora da interface** | Alteração efetiva no tráfego da rede | **Não.** O recorte não prevê ação de bloqueio pela interface |

**Classificação ≠ incidente.** O que o modelo produz é uma *classificação*: um rótulo probabilístico atribuído a um fluxo. Um *incidente* existe quando um profissional confronta essa classificação com o contexto e a confirma. São objetos diferentes e a interface precisa mantê-los distintos.

**O que “validar” significa neste projeto:** validar é o analista confrontar a classificação com o contexto da conexão e **registrar seu julgamento** — falso positivo, incidente confirmado ou indefinido (exige mais investigação). Validar não é executar uma contenção, nem é o modelo confirmar a si mesmo.

**Onde o texto foi corrigido:** as expressões “conter ameaças” e “detectar e mitigar invasões” foram substituídas nas seções 2.2, 4.4, 7.3, 7.4, 9.2 e 13.

---


# 3. Entendendo objetivos e atividades

## 3.1 O que o usuário está tentando conseguir no mundo real?

- [H09] Garantir um acesso mais seguro a uma rede de computadores, e evitar vazamento de dados permitindo uma resposta rápida a incidentes.

- [H10] Manter a rede operacional e segura, identificando e mitigando ameaças antes que comprometam a disponibilidade, integridade ou confidencialidade dos dados.

> **Nota (feedback E01, item 2):** “mitigar” aqui descreve o objetivo do usuário **no mundo real**, que não se esgota na interface. O que a interface deste projeto apoia é perceber, interpretar e decidir o encaminhamento — ver o quadro no fim da seção 2.

## 3.2 Quais são as atividades mais importantes?

| ID | Atividade — o que a pessoa faz | Quem realiza | Frequência/criticidade inicial | Status/evidência |
|---|---|---|---|---|
| A01 | **Observar o estado da rede** — acompanhar o fluxo agregado e perceber quando algo foge do padrão | Analista de Segurança | Contínua durante o turno | [H11] Frequência **estimada pela equipe**. Nenhum turno foi observado |
| A02 | **Investigar uma conexão sinalizada** — abrir a ocorrência, examinar origem, destino, serviço, volume e categoria prevista, julgar se corresponde a um incidente e registrar a decisão | Analista de Segurança | Episódica, mas **a mais crítica** | [H12] Criticidade **estimada pela equipe** a partir da consequência de erro descrita em 4.4 |
| A03 | **Ajustar o classificador ativo** — trocar o modelo de ML em execução conforme o perfil do ambiente | Administrador de Rede (sobre a sobreposição com o analista, ver 7.3) | [?] **Desconhecida.** “Mensalmente” era uma estimativa sem origem e foi retirada | [F] (capacidade definida no TCC) a alternância do classificador está prevista no pipeline. [H05/H27] Quem a realiza, com qual objetivo e com qual frequência permanece lacuna |

> **Nota de revisão (feedback E01, item 3):** a coluna “Status/evidência” continha descrições de atividade, sem indicar se o conteúdo era fato, hipótese ou lacuna. As descrições foram movidas para a coluna da atividade e a coluna de status passou a classificar cada afirmação. Os nomes “Monitoramento”, “Gerenciamento” e “Configuração” foram substituídos por verbo + objeto, para preparar a análise de tarefas da Entrega 05.
>
> **Alcance da fonte:** o [MVP1](../assets/01_dados_mvps/mvp1.pdf) sustenta **o que o sistema faz** (pipeline de classificação e comparativo entre algoritmos). Ele não comprova a frequência com que um profissional realizaria cada atividade, nem que uma função seja necessária para um determinado perfil.


## 3.3 Qual atividade parece mais frequente? Por quê?

[H11] A01 (observar o estado da rede). O fluxo de pacotes chega ininterruptamente à infraestrutura — isso é um fato sobre a rede. Que a **pessoa** acompanhe esse fluxo de forma contínua é a hipótese: pode ser que ela só olhe o painel quando um alerta a chama. Investigação na Entrega 07.

## 3.4 Qual parece mais crítica? Que consequência existe se for mal executada?

[H12] A02 (investigar uma conexão sinalizada). Se o analista descartar como falso positivo uma classificação que correspondia a um incidente real, a ocorrência evolui sem resposta — exfiltração (R2L/U2R) ou indisponibilidade. O erro oposto também custa: escalar um alerta indevido pode levar alguém, **fora da interface**, a interromper um serviço legítimo. Ver o detalhamento em 4.4.

---

# 4. Entendendo o problema ou processo atual

## 4.1 Como essas atividades são realizadas hoje, antes da interface imaginada na disciplina?

**O que sabemos:**

- [F] Existe um conjunto amplo de ferramentas em uso para essa atividade: logs de rede, captura de pacotes, consoles de linha de comando e IDS/SIEM — Snort, Suricata, Zeek, Wazuh, Security Onion, Cisco Secure, Palo Alto, Sophos, Windows Defender, ClamAV, Fortinet, Splunk, Elastic e Datadog, entre outros. O levantamento está na seção 6 e é aprofundado na Entrega 02.
- [F] Parte dessas ferramentas opera predominantemente por assinaturas e regras (Snort, Suricata). **Isso não se aplica indistintamente a todas:** Zeek faz análise comportamental, Wazuh e Elastic correlacionam eventos de múltiplas fontes e as plataformas comerciais combinam várias técnicas. A caracterização anterior — “baseados exclusivamente em regras e assinaturas fixas” — generalizava indevidamente e foi corrigida.

**O que ainda não sabemos — hipótese de processo atual:**

- [H30] Sequência **suposta pela equipe**, a ser verificada na Entrega 07: (1) o profissional **recebe um indício** — um alerta da ferramenta, uma reclamação de lentidão ou uma anomalia percebida num painel; (2) **consulta informações** em uma ou mais ferramentas para reunir o contexto da conexão; (3) **interpreta** se o indício corresponde a uma ocorrência real; (4) **decide o encaminhamento** — descartar, escalar ou solicitar ação. Nenhuma etapa dessa sequência foi observada: ela é a hipótese que estrutura as Entregas 04 e 05.
- [?] Quais ferramentas o público específico do projeto usa hoje, em qual ordem e com qual esforço.


## 4.2 O que é difícil, demorado, confuso, repetitivo, arriscado ou pouco transparente?

- [F] **Limitação da tecnologia de detecção:** sistemas que dependem de assinatura prévia não identificam ataques inéditos (Zero-Day).
  - Fonte: W. S. Admass, Y. Y. Munaye e A. A. Diro, “Cyber security: State of the art, challenges and future directions,” 2023. doi: 10.1016/2023.10031
- [F] **Limitação da tecnologia de detecção:** a literatura aponta volume elevado de dados e alta taxa de falsos positivos em abordagens tradicionais de detecção de anomalias.
  - Fonte: Z. Azam, M. M. Islam e M. N. Huda, 2023. doi: 10.1109/2023.3296444
- [H13] **Dificuldade de interação:** correlacionar dezenas de métricas brutas (taxa de erro SYN, contagem de portas, bytes por fluxo) exige que o analista mantenha o contexto na memória enquanto alterna entre telas e consultas. **Atividade:** A02, investigar uma conexão sinalizada. **Contexto:** durante o turno, com outras ocorrências competindo por atenção. Investigação na Entrega 07.

> **Nota de revisão (feedback E01, item 4):** os dois primeiros itens são limitações **da tecnologia de detecção**, não do trabalho humano. Um problema de IHC não se sustenta sobre uma lacuna de mercado atribuída a todas as alternativas: o problema que este projeto estuda é o **H13**, ancorado numa atividade e num contexto.


## 4.3 Que informações o profissional precisa interpretar para tomar decisão?

**O que o sistema disponibiliza:**

- [F] (capacidade definida no TCC) Categoria prevista da anomalia (Normal, DoS, Probe, R2L, U2R) e nível de confiança do modelo.
- [F] (capacidade definida no TCC) Origem e destino da conexão, serviços utilizados, volume de bytes enviados e recebidos — atributos presentes no fluxo analisado.
  - Fonte: [MVP1 — atributos selecionados do NSL-KDD](../assets/01_dados_mvps/mvp1.pdf)

**O que ainda não sabemos:**

- [?] Se essas informações **bastam** para o julgamento do analista, ou se ele precisa de histórico do ativo, comparação com o comportamento habitual ou consulta a outra fonte. Essa é a diferença entre o que o modelo produz e o que a pessoa precisa interpretar. Investigação na Entrega 07.


## 4.4 O que acontece quando a atividade falha ou quando o resultado é interpretado incorretamente?

A consequência depende de **qual** erro ocorre e **em qual etapa** (ver o quadro no fim da seção 2):

| Erro | Onde ocorre | Consequência imediata | Consequência se a decisão humana acompanhar o erro |
|---|---|---|---|
| **Falso negativo do modelo** — ataque classificado como tráfego normal | Classificação | Nenhuma ocorrência chega ao analista | [H] A atividade pode evoluir sem ser percebida: elevação de privilégio, exfiltração ou indisponibilidade |
| **Falso positivo do modelo** — tráfego legítimo classificado como ataque | Classificação | Uma ocorrência é apresentada ao analista | O analista **pode descartá-la na interpretação** (A02). O custo imediato é o tempo gasto investigando |
| **Erro de interpretação do analista** | Interpretação (A02) | Um incidente real é descartado, ou uma ocorrência legítima é escalada indevidamente | [H] Se um incidente for descartado, a consequência é a do falso negativo. Se uma ocorrência indevida for escalada e alguém **fora da interface** executar um bloqueio, serviços legítimos podem ser interrompidos |

> **Nota de revisão (feedback E01, item 2):** a redação anterior era “Falso Positivo (Tráfego legítimo bloqueado)”, ligando a classificação incorreta diretamente ao bloqueio. Entre uma coisa e outra existem ao menos duas etapas — a interpretação do analista e a execução por outro sistema ou responsável. A distinção importa para o design: o custo do falso positivo do modelo é **absorvido pela interpretação**, e é exatamente aí que a interface pode ajudar ou atrapalhar.


## 4.5 Conte uma situação concreta.

[H14] **Situação hipotética construída pela equipe — não é um caso observado.**

Durante o plantão noturno, o analista **Thiago** percebe lentidão pontual nos servidores Web. Ele abre o console tradicional e encontra milhares de linhas de log cruas. Sem saber se é um pico legítimo de acessos ou uma varredura/DoS, alterna entre consultas e filtros manuais para reunir o contexto da conexão. Enquanto não consegue decidir, a ocorrência segue em curso e ele não sabe dizer à operação se deve ou não agir.

> **Limites desta narrativa (feedback E01, itens 3, 6 e Recomendações):**
>
> - O personagem foi uniformizado como **Thiago**, coerente com a persona P01 da Entrega 03. Antes aparecia como “Cleitin” aqui e “Lucas” na seção 10.
> - A duração de **40 minutos foi retirada** do corpo da narrativa. Era um número inventado para ilustrar o problema e **não pode servir de linha de base** para medir a melhoria da interface. Se uma linha de base for necessária, terá de vir de observação (Entrega 07) ou ser medida no próprio teste de usabilidade (Entregas 12–14).
> - O cenário continua útil para discutir o problema; ele não documenta uma ocorrência real.


## 4.6 Que evidência existe hoje?

| Evidência/fonte                           | O que sustenta                                                                                                             | Limitação                                                                                |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Experimentos com dataset NSL-KDD no MVP 1 | Demonstra alta taxa de acurácia (99,7%) da Decision Tree e tempo de inferência rápido (0,003s) para 18 atributos           | Avaliação realizada em dataset estático, pendente de validação com tráfego real dinâmico |
| Revisão bibliográfica do artigo           | Confirma que modelos tradicionais geram altos falsos positivos e que a redução de dimensionalidade é chave para tempo real | Foco primariamente acadêmico e conceitual.                                               |
<br>
Fonte: [MVP1](../assets/01_dados_mvps/mvp1.pdf)

---

# 5. Entendendo o contexto de uso

## 5.1 Onde e em quais situações a interação poderia ocorrer?

[H15] Em salas de centro de operações de segurança (SOC), ambientes de TI corporativos ou estações de trabalho de administradores de rede, sob operação normal ou em situações de crise/incidente crítico.

## 5.2 Em quais dispositivos/equipamentos?

[H16] Monitores e workstations de trabalho (para visualização do dashboard) conectados a servidores centrais ou placas embarcadas de monitoramento em tempo real

## 5.3 Existem condições físicas relevantes?

[H17] Uso contínuo em ambientes com múltiplos monitores, iluminação controlada (uso comum de modo escuro/Dark Mode) e pressão de tempo para tomadas de decisão sob incidentes.

## 5.4 Existem fatores sociais ou organizacionais?

[H18] Hierarquia operacional onde o analista L1 monitora os alertas iniciais, o analista L2 investiga a fundo e o gestor avalia os relatórios consolidados de conformidade e segurança.

## 5.5 Existe necessidade de histórico, rastreabilidade ou auditoria?

[H31] Provavelmente sim. A retenção de histórico de ocorrências e de métricas do modelo para auditoria e conformidade é uma prática plausível e recorrente em ambientes corporativos, mas **não levantamos** a exigência específica do contexto estudado: qual retenção, para quem e com qual finalidade. Marcar isso como fato equivaleria a tratar uma prática profissional como comprovada. Investigação na Entrega 07.

## 5.6 Um erro pode produzir consequência relevante? Qual?

[F] Sim. Casos relatados na literatura (ver 1.2) associam intrusões não identificadas a prejuízo financeiro e a comprometimento de infraestruturas críticas. O detalhamento de **qual** erro produz **qual** consequência está em 4.4; a magnitude varia com o ambiente e não foi medida para o contexto deste projeto.
<br>
Fonte: [MVP1](../assets/01_dados_mvps/mvp1.pdf)

---

# 6. Entendendo mercado e alternativas existentes

> Nesta entrega faça apenas um **levantamento inicial**. A análise aprofundada ocorre na Entrega 2.

> **Nota de revisão (feedback E01, item 4):** o que segue é um levantamento, não uma comparação. Nenhuma afirmação de **superioridade** da proposta é feita aqui: os fluxos concretos das alternativas são examinados na Entrega 02. A existência de cada ferramenta é verificável `[F]`; o que cada público faz com ela e o quanto conhece é hipótese `[H]`.

## 6.1 Como pessoas resolvem problemas semelhantes hoje?

| Alternativa atual                   | Quem usa                            | Para quê                                                     | Status/evidência |
| ----------------------------------- | ----------------------------------- | ------------------------------------------------------------ | ---------------- |
| IDSs tradicionais (Snort, Suricata) | [H] Analistas / administradores de rede | Monitorar tráfego com base em regras e assinaturas | [F] a ferramenta existe e opera por regras; [H28] que este público a use é suposição |
| Plataformas de correlação (Wazuh, Elastic, Security Onion) | [H] Equipes de SOC | Reunir eventos de várias fontes e investigar ocorrências | [F] a ferramenta existe; [H28] a adoção pelo público do projeto é suposição |
| Dashboards genéricos (Grafana, Metabase) | [H] Equipes de TI / DevOps | Visualizar métricas de infraestrutura e logs agregados | [F] a ferramenta existe; [H] o uso pelo perfil escolhido não foi verificado |
| Scripts em Python / notebooks | [H] Pesquisadores / cientistas de dados | Treinar e validar modelos de ML *offline* | [F] é a prática do próprio TCC (MVP 1); [H] sua ocorrência na rotina de um SOC não foi verificada |


Fonte: [MVP1](../assets/01_dados_mvps/mvp1.pdf)

## 6.2 Existem produtos que atuam na mesma área, mesmo sem serem equivalentes ao TCC?

[F] Sim. Ferramentas comerciais como Splunk, Elastic SIEM, Datadog, Snort, Suricata, Cisco Secure, Zeek, Wazuh, ClamAV, Palo Alto, Sophos, Windows Defender, Security Onion, Fortinet IDS e outros, além de soluções de NIDS com módulo de IA.

## 6.3 Quais interfaces profissionais esse público já conhece?

[H] Supomos que painéis de monitoramento (Grafana, Metabase), consoles de SIEM e ferramentas de gestão de logs façam parte do repertório desse público. **Não há evidência** disso no material reunido: conhecer a existência de uma interface não é o mesmo que saber que o público-alvo a usa. Ver H28; investigação na Entrega 07.

## 6.4 O que essas soluções parecem fazer bem?

[H19] **Presença observável:** gráficos de linha do tempo, filtros e integração de múltiplas fontes aparecem nessas ferramentas. **Julgamento não verificado:** que elas façam isso *bem*, do ponto de vista do analista, exige avaliar o fluxo — feito na Entrega 02.

## 6.5 O que parecem fazer mal, dificultar ou não atender?

[H20] Supomos alta complexidade de configuração, dependência de atualização de assinaturas e poluição visual por alertas irrelevantes. **Nenhum desses pontos foi medido**; críticas de complexidade encontradas na Entrega 02 não comprovam, por si, excesso de alertas irrelevantes. São coisas distintas.

## 6.6 Que padrões de interface ou vocabulário parecem familiares a esse público?

[H21] Gráficos de rosca para distribuição de tráfego, linhas do tempo para taxa de pacotes, cartões numéricos com indicadores e tabelas com código de cor de severidade **aparecem** nas ferramentas levantadas. Que o usuário esteja **habituado** a eles é outra afirmação: encontrar um componente numa interface não demonstra familiaridade de quem a usa. Investigação na Entrega 07.

---

# 7. Derivando o escopo de IHC da disciplina

## 7.1 Escolha o caminho do projeto

### Caminho A — TCC já possui interface

O TCC contempla o desenvolvimento de um protótipo de IDS em tempo real acoplado a um dashboard para gerenciamento e monitoramento da segurança da rede. O recorte de IHC focará na interface de monitoramento e controle operacional do IDS, permitindo ao usuário acompanhar o tráfego em tempo real, visualizar a classificação do modelo (Decision Tree e outros), inspecionar detalhes dos incidentes detectados e alternar/configurar os modelos de ML em execução.

## 7.2 Qual perfil será priorizado no projeto de IHC?

Analista de Segurança de Rede (SOC Analyst).

**Por que esse perfil foi escolhido?** Pois é a pessoa responsável pela tomada de decisão rápida e contínua no monitoramento diário da infraestrutura, sofrendo o impacto direto da usabilidade do painel sob cenários de ataque em tempo real.

## 7.3 Qual objetivo desse usuário será priorizado?

Interpretar uma conexão sinalizada pelo modelo e **decidir o encaminhamento** — descartar como falso positivo, confirmar como incidente ou escalar — com o apoio das informações que o sistema disponibiliza.

**Núcleo do recorte e possibilidades secundárias (feedback E01, item 5):**

| | Atividades | Perfil | Justificativa |
|---|---|---|---|
| **Núcleo** | A01 (observar o estado da rede) e A02 (investigar uma conexão sinalizada) | Analista SOC | A02 é a atividade mais crítica [H12] e A01 a mais frequente [H11]; juntas formam o fluxo de interpretação que o projeto estuda |
| **Secundária** | A03 (ajustar o classificador ativo) | Administrador de Rede | Entra no projeto **porque a troca de modelo altera o que o analista vê**: a categoria prevista e a confiança passam a vir de outro classificador. A interface precisa comunicar **qual modelo** produziu cada resultado. Quem decide trocar é o administrador (P02, Entrega 03), com o objetivo de adequar a detecção ao perfil do ambiente |
| **Fora do núcleo** | Importação de datasets, comparação de algoritmos, exportação de métricas, monitoramento de hardware (seção 8) | Administrador / pesquisa | Permanecem registradas como levantamento. Não são compromisso de implementação |

> **O que mudou:** o objetivo anterior incluía “monitorar a performance dos algoritmos de detecção” como objetivo **do analista**. Esse objetivo pertence ao administrador e foi movido para a linha secundária. O painel deve ajudar alguém a compreender uma situação e decidir o que fazer — não exibir tudo o que o algoritmo consegue produzir.


## 7.4 Que interface será explorada na disciplina?

Complete:

> Para fins da disciplina de IHC, será projetada uma interface que permita ao **Analista de Segurança de Rede** utilizar a capacidade do modelo de classificar tráfego em categorias (Normal, DoS, Probe, R2L, U2R) com grau de confiança associado, para **perceber uma ocorrência, interpretá-la e decidir o encaminhamento**, no contexto de monitoramento de um Centro de Operações de Segurança (SOC).
>
> **Fora do recorte:** executar a contenção — bloqueio, isolamento, derrubada de serviço — que ocorre em outro sistema ou por outro responsável (ver o quadro no fim da seção 2).

> **Nota de revisão:** a formulação anterior era “detectar e mitigar invasões cibernéticas” e prometia alta precisão e baixo tempo de resposta como características da interface. Essas duas métricas descrevem o classificador, não a interação; e “mitigar” excedia o que F01–F03 descrevem.


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

> **Duas perguntas distintas (feedback E01, item 3):** uma função pode estar **definida no TCC** e sua **adequação ao trabalho humano** continuar em investigação. As duas últimas colunas separam essas perguntas.

| Possibilidade | Pode fazer sentido? | Objetivo/tarefa que justificaria | A função já está definida no TCC? | É necessária/útil para o analista SOC? |
|---|---|---|---|---|
| Dashboard/visão geral | Sim — **núcleo** | Perceber o estado da rede e decidir se há algo a investigar (A01) | [F] Sim, o dashboard consta do MVP 2 | [H11/H08] Hipótese |
| Alertas/ocorrências | Sim — **núcleo** | Receber o indício que inicia a investigação (A02) | [F] Sim, a classificação gera a ocorrência | [H08] Hipótese |
| Histórico com busca/filtros | Sim — **núcleo** | Restringir o conjunto de conexões para investigar uma ocorrência (A02) | [F] Sim, os atributos de filtragem existem no pipeline | [H13] Hipótese |
| Explicabilidade/detalhamento | Sim — **núcleo** | Dar ao analista elementos para julgar a classificação (A02) | [?] Exibir os atributos mais relevantes é tecnicamente possível com árvore de decisão, mas **o formato dessa explicação ainda não está definido** no TCC | [H] Hipótese; ver RC03 na Entrega 02 |
| Configuração/parametrização | Sim — secundária | Alternar o classificador ativo (A03, administrador) | [F] Sim, o pipeline modular está definido | [H05/H27] Hipótese: quem faz, quando e por quê ainda não se sabe |
| Comparação de resultados | Talvez — secundária | Escolher qual classificador manter ativo (A03, administrador) | [F] Sim, o *benchmark* entre DT, RF, KNN, SVM e LR faz parte do TCC | [H] Hipótese: o *benchmark* é um resultado de pesquisa; que o administrador precise compará-lo **em operação** não foi verificado |
| Acompanhamento de processamento | Talvez — secundária | Verificar se a plataforma embarcada suporta a carga (A03, administrador) | [F] Sim, métricas de hardware são coletadas | [H02] Hipótese; ver 9.3 |
| Auditoria/logs | Talvez — secundária | Registrar as decisões do analista para revisão posterior | [?] Não previsto explicitamente no TCC | [H31] Hipótese; ver 5.5 |
| Relatório/resultados | Talvez — **fora do núcleo** | Consolidar ocorrências para registro ou comunicação | [F] Métricas de acurácia/F1 existem no TCC | [H06] O destinatário natural seria o gestor, que **não é persona deste projeto** |
| Entrada/upload/seleção de dados | Talvez — **fora do núcleo** | Escolher a fonte de captura ou importar dataset de teste | [F] Previsto no pipeline experimental | [?] Importar dataset é atividade de pesquisa, não do analista em turno |
| Administração/configurações globais | Talvez | Definir limites de alerta ou de captura | [?] Não definido | [H22] Hipótese |
| Ajuda/documentação | Talvez | Explicar as classes de ataque e os atributos exibidos | [?] Não previsto no TCC | [H25] Hipótese |
| Usuários/perfis/permissões | Não | — | [?] Não previsto | [H23] Decisão de recorte da disciplina |
| CRUD de entidade do domínio | Não | — | Não se aplica | [H24] O domínio é fluxo contínuo de eventos, não cadastro de dados estáticos |

Fonte das capacidades técnicas listadas: [MVP1](../assets/01_dados_mvps/mvp1.pdf). O documento sustenta a coluna “já está definida no TCC”; ele **não** sustenta a coluna de necessidade.


> **Atenção:** “login + dashboard + CRUD” não é uma solução universal. Cada padrão deve surgir de uma tarefa real.

---

# 9. Benefícios e ações iniciais

## 9.1 Qual benefício concreto o projeto de IHC pretende oferecer?

| Benefício esperado                           | Problema/necessidade                                                           | Usuário                          | Status/evidência |
| -------------------------------------------- | ------------------------------------------------------------------------------ | -------------------------------- | ---------------- |
| Redução no tempo entre perceber uma ocorrência e decidir o encaminhamento | Dificuldade em correlacionar métricas brutas sob pressão (H13) | Analista de Segurança | [H26] Benefício de uso hipotético (nível 3). Será avaliado nas Entregas 12–14, com linha de base medida no próprio teste — não com o tempo fictício do cenário H14 |
| Clareza sobre qual modelo produziu cada classificação e o que muda ao trocá-lo | Falta de visibilidade sobre a origem do resultado que o analista interpreta | Administrador de Rede (executa) / Analista (é afetado) | [H27] Benefício de uso hipotético (nível 3) |


## 9.2 Que ações o usuário deverá conseguir realizar?

| ID  | O usuário precisa conseguir...                                                         | Para alcançar...                                            | Prioridade inicial |
| --- | -------------------------------------------------------------------------------------- | ----------------------------------------------------------- | ------------------ |
| F01 | Perceber o estado atual do tráfego e a existência de conexões sinalizadas | Decidir se há algo a investigar agora (A01) | Alta |
| F02 | Inspecionar os atributos de uma conexão sinalizada, a categoria prevista e a confiança do modelo | Julgar se a classificação corresponde a um incidente e registrar a decisão (A02) | **Alta** — revisada nesta entrega |
| F03 | Alternar o classificador ativo e saber **qual modelo produziu** cada classificação exibida | Adequar a detecção ao ambiente (A03, administrador) e dar ao analista a origem do resultado que interpreta | Média — atividade secundária, de outro perfil |

> **Nota de revisão (feedback E01, item 5):** F02 estava com prioridade **média**, o que contradizia A02/H12 — a atividade identificada como a mais crítica — e o próprio objetivo de “validar”. Como o erro de interpretação é onde a consequência é maior (4.4), **F02 passa a Alta**. F01 continua Alta por frequência. F03 permanece Média e ganhou um segundo propósito: tornar visível ao analista qual classificador originou o resultado.
>
> Nenhuma dessas três ações inclui executar contenção — ver o quadro no fim da seção 2.


## 9.3 Tecnologias/restrições já definidas no TCC

A tecnologia aparece **agora**, depois do entendimento do uso.

| Tecnologia/restrição | Por que existe | Efeito **percebido pelo usuário** na interação |
|---|---|---|
| Modelos em Python / Scikit-Learn | Definido no TCC para treinamento e inferência dos classificadores | [?] Nenhum efeito direto sobre o usuário foi identificado. A escolha da biblioteca é interna ao projeto e não precisa aparecer na interface |
| **Processamento** em sistema embarcado | Requisito do TCC: classificar o tráfego na borda da rede | **Nenhum efeito direto na interface.** O embarcado executa a classificação; ele não renderiza a tela |
| **Acesso à interface** por workstation/navegador | Decorrência de 5.2: o analista não opera a partir do embarcado | [H02] Se a interface consultar o embarcado em tempo real, a frequência de atualização pode ficar limitada pela capacidade daquele equipamento. **O efeito percebido seria a latência entre o fato na rede e sua exibição na tela** — esse é o ponto a investigar |

> **Nota de revisão (feedback E01, Recomendações):** a tabela anterior misturava equipamento de **processamento** com equipamento de **interação**. A restrição do embarcado afeta o usuário apenas se e quando produzir atraso no que ele vê; é esse efeito percebido que interessa à disciplina, não a arquitetura de implementação.


---

# 10. Hipóteses e dúvidas prioritárias

| ID | Hipótese/dúvida | Por que importa | Onde poderá ser investigada | O que essa etapa poderá sustentar |
|---|---|---|---|---|
| H01 | O painel reduzirá o tempo entre perceber uma ocorrência e decidir o encaminhamento. | É o benefício de uso central do projeto (nível 3). | **Entregas 12–14** (avaliação de usabilidade) | **Só a avaliação mede tempo de tarefa.** As Entregas 02 e 05 ajudam a *compreender* o problema e a modelar a tarefa, mas não demonstram redução de tempo. H01 e H26 são a mesma afirmação em dois momentos: H01 a enuncia, H26 a encaminha para a avaliação |
| H02 | Viabilidade operacional em hardware limitado/embarcado. | O efeito que interessa à IHC é a latência percebida na tela (9.3). | Entrega 08 (restrições e metas de usabilidade) | Metas de tempo de resposta da interface |
| H03 | Os perfis diretos são analista SOC, administrador e gestor. | Define os atores centrais. | Entrega 03 | Decisão de quais perfis viram persona; não comprova a existência dos papéis no mercado |
| H04 | O analista monitora o tráfego e interpreta ocorrências em tempo real. | Define o papel operacional estudado. | Entrega 03 / 05, verificação na Entrega 07 | A Entrega 03 constrói a persona; apenas a Entrega 07 traz dado sobre o papel real |
| H05 | O administrador ajusta parâmetros de captura e escolhe o classificador. | Define o papel administrativo e a origem de A03. | Entrega 03 / 05, verificação na Entrega 07 | Quem decide trocar o modelo, em qual situação e com quais informações |
| H06 | O gestor consulta resultados consolidados e decide investimentos. | Define se há necessidade de visão executiva. | Entrega 07 | **Estado: aberta.** Não criar persona de gestor é uma **decisão de recorte** deste projeto; ela não refuta a hipótese sobre a atividade do gestor |
| H07 | Analistas dominam termos técnicos e ainda assim precisam de síntese visual. | Evita expor dados brutos sem síntese. | Entrega 07 | São duas afirmações e precisam ser verificadas separadamente |
| H08 | Sob pressão, a interface deve reduzir ruído visual e destacar severidade. | Evita sobrecarga cognitiva em situações críticas. | Entregas 06 e 12–14 | É hipótese **de design**: só um teste com usuários a sustenta |
| H09 | O usuário busca acesso seguro e resposta rápida para evitar vazamento. | Motivação de negócio do usuário. | Entrega 04 | Cenários-problema; não é evidência empírica |
| H10 | O usuário precisa manter a rede operacional mitigando ameaças. | Objetivo contínuo de proteção. | Entrega 04 / 05 | Idem |
| H11 | Observar o estado da rede (A01) é a atividade mais frequente. | Define qual tela é a visualização padrão. | Entrega 07 (observação/coleta) | Frequência só se estabelece observando ou perguntando |
| H12 | Investigar uma conexão sinalizada (A02) é a atividade mais crítica. | Define onde o erro do usuário custa mais. | Entrega 04 / 07 | Consequência de erro, discutida em 4.4 |
| H13 | Correlacionar métricas brutas sem síntese visual é difícil para o analista. | **É o problema de IHC do projeto.** | Entrega 02 (fluxos das alternativas) e Entrega 07 (o analista) | A Entrega 02 mostra como as ferramentas tratam a correlação; só a Entrega 07 diz se isso é difícil **para a pessoa** |
| H14 | Cenário hipotético: **Thiago** investiga uma lentidão sem conseguir decidir. | Cenário de referência para discutir o problema. | Entrega 04 | **Não é linha de base.** A duração de 40 min foi retirada: era ficção e não pode medir melhoria |
| H15 | A interação ocorre em salas de SOC ou estações sob pressão. | Contexto físico de uso. | Entrega 03 (descrição) e Entrega 07 (verificação) | A Entrega 03 **descreve** o contexto suposto; não o comprova |
| H16 | O sistema será usado em workstations e monitores conectados a embarcados. | Define o porte dos dispositivos. | Entrega 03 / 08 | **Refinada, não refutada:** o processamento segue no embarcado; o que mudou é que a **interface** será acessada por notebook/desktop. Ver 9.3 |
| H17 | O ambiente exige uso contínuo, múltiplos monitores e modo escuro. | Conforto visual prolongado. | Entregas 06 e 12–14 | O **objetivo** é legibilidade e conforto; modo escuro é **uma alternativa** a testar, não uma decisão decorrente da hipótese |
| H18 | Existe hierarquia operacional (L1 tria, L2 investiga, gestor avalia). | Organiza os papéis no contexto social. | Entrega 07 | **Estado: aberta.** Retirar o gestor do elenco de personas é decisão de recorte e **não refuta** a existência da hierarquia no contexto estudado |
| H19 | As alternativas exibem bem linhas do tempo e filtros. | Convenções a preservar. | Entrega 02 | A **presença** do componente é observável; que ele funcione **bem** é julgamento e exige analisar o fluxo |
| H20 | As alternativas pecam por complexidade e excesso de alertas irrelevantes. | Pontos fracos a evitar. | Entrega 02 e Entrega 07 | Críticas de complexidade **não comprovam** excesso de alertas irrelevantes: são afirmações distintas |
| H21 | O usuário está habituado a gráficos de rosca, indicadores e tabelas coloridas. | Vocabulário visual do projeto. | Entrega 07 | Encontrar o componente numa interface concorrente **não demonstra** familiaridade de quem a usa |
| H22 | Configurações globais (limites de alerta) cabem no escopo. | Delimita a parametrização. | Entrega 05 / 07 | — |
| H23 | Gestão de usuários/permissões não é prioritária para o recorte. | Delimita o escopo pedagógico. | **Decisão da equipe**, registrada aqui | A **Entrega 07 é de coleta de dados**, não de “Escopo de Interação” — referência corrigida. Uma decisão de escopo não se investiga, se registra |
| H24 | CRUD tradicional não se aplica a um domínio de fluxo contínuo. | Evita padrão inadequado. | Entrega 05 | — |
| H25 | Uma tela de ajuda com guia de ataques ajudaria iniciantes. | Suporte instrucional. | Entregas 05 / 06 / 12–14 | — |
| H26 | A interface reduzirá o tempo de identificação de ocorrências. | Proposta de valor do projeto de IHC. | Entregas 12–14 | Encaminhamento de H01. A linha de base será medida no próprio teste, **não** retirada do cenário H14 |
| H27 | A interface tornará clara a troca de modelos e sua consequência. | Avalia a compreensão do controle modular. | Entregas 07 e 12–14 | Quem troca, por quê e o que precisa ver para entender o efeito |
| H28 | Analistas de SOC já estão familiarizados com ferramentas semelhantes. | Define o que a interface pode pressupor. | Entrega 07 | *Nova nesta revisão* — substitui um `[F]` indevido de 2.4 |
| H29 | O analista decide sob pressão de tempo; a janela de decisão é curta. | Define as metas de usabilidade (Entrega 08). | Entrega 07 | *Nova nesta revisão* — substitui “decisões instantâneas” em 2.4 |
| H30 | O processo atual segue a sequência indício → consulta → interpretação → encaminhamento. | É a hipótese de processo que estrutura as Entregas 04 e 05. | Entrega 07 | *Nova nesta revisão* — substitui a generalização de 4.1 |
| H31 | Há necessidade de retenção de histórico para auditoria e conformidade. | Define se o histórico entra no recorte. | Entrega 07 | *Nova nesta revisão* — substitui um `[F]` indevido de 5.5 |


Registre em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).

---

# 11. Síntese da equipe

| Pergunta | Síntese atual |
|---|---|
| Qual é a contribuição central do TCC? | [F] Um modelo de ML otimizado que **classifica** o tráfego de rede em tempo real, com conjunto reduzido de atributos |
| O TCC já previa interface? | [F] Sim: um dashboard para gerenciamento e monitoramento da segurança da rede (MVP 2) |
| Quem é o usuário prioritário de IHC? | [F] (decisão da equipe) Analista de Segurança de Rede (analista SOC) |
| O que ele precisa alcançar? | [H04/H12] Interpretar uma conexão sinalizada e decidir o encaminhamento. **Não** executar a contenção — ver o quadro no fim da seção 2 |
| Qual problema/atividade será estudado? | [H13] A dificuldade de correlacionar métricas brutas ao investigar uma ocorrência (A02), sob pressão de tempo |
| Como isso acontece hoje? | [H30] Hipótese de processo: o profissional recebe um indício, consulta informações em uma ou mais ferramentas, interpreta e decide o encaminhamento. [?] A rotina real do público-alvo não foi observada |
| Qual é o contexto de uso? | [H15/H17] SOC e ambientes corporativos de rede, com pressão de tempo e uso prolongado de telas |
| Que interface/recorte será explorado? | [F] (decisão da equipe) Painel de observação do tráfego e de investigação de uma conexão sinalizada, com indicação de qual classificador produziu cada resultado |
| Como a interface se relaciona ao TCC? | [F] Já fazia parte do escopo previsto (0.5 e 7.5) |
| **Quais pontos ainda são hipóteses?** | **Praticamente tudo o que afirmamos sobre pessoas.** As incertezas que mais afetam o recorte são: <br>• **O problema existe como o descrevemos?** H13 (dificuldade de correlacionar) e H30 (como o processo acontece hoje) — nenhum analista foi observado. <br>• **O usuário é quem supomos?** H04, H05, H28 e H29 — papéis, familiaridade e janela de decisão são suposições. <br>• **A prioridade entre atividades está certa?** H11 (A01 mais frequente) e H12 (A02 mais crítica) são estimativas da equipe. <br>• **A solução produz o benefício prometido?** H01 e H26 (tempo) e H27 (clareza da troca de modelo) — só serão sustentados nas Entregas 12–14. <br>• **As convenções visuais são familiares?** H19, H20 e H21 — a Entrega 02 observa as interfaces, não os usuários. <br>• **O que o modelo entrega basta para decidir?** Lacuna `[?]` registrada em 4.3. <br><br>Permanecem como **decisões de recorte**, e não hipóteses: H06 e H18 (gestor e hierarquia fora do elenco de personas), H23 (sem gestão de permissões) e H24 (sem CRUD) |


### Delimitação

**Dentro do escopo de IHC:** painel de observação do tráfego em tempo real; apresentação das ocorrências por categoria (DoS, Probe, R2L, U2R) com grau de confiança; detalhamento de uma conexão sinalizada para interpretação; registro da decisão do analista; indicação de qual classificador está ativo e controle para alternar entre eles (atividade secundária, do administrador).

**Fora do escopo de IHC:** execução de contenção pela interface (bloqueio, isolamento, derrubada de serviço — ver o quadro no fim da seção 2); virtualização de SO; configuração de baixo nível dos adaptadores de rede físicos; treinamento *offline* dos modelos; gestão de usuários e permissões (H23); relatórios executivos para gestor (H06, decisão de recorte).

**Dentro do escopo formal do TCC:** pipeline de captura de dados, seleção de atributos, treinamento e *benchmark* de modelos em hardware embarcado **e o dashboard de gerenciamento e monitoramento da segurança da rede**, já declarado em 0.5 e 7.5 como parte prevista (MVP 2).

> **Nota de revisão (feedback E01, item 7):** a enumeração anterior do escopo formal listava apenas pipeline e experimentos, omitindo o dashboard que as seções 0.5 e 7.5 declaram previsto. A inconsistência foi corrigida **sem ampliar** o compromisso: o que o TCC prevê é o dashboard; a interface detalhada na disciplina continua sendo artefato de aprendizagem de IHC.

**Interface da disciplina será implementada no TCC?** O dashboard já estava previsto na evolução da arquitetura do TCC (MVP 2). A incorporação das **decisões de interação** tomadas na disciplina depende de decisão da equipe e do orientador.

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

1. **Problema/atividade humana:** em uma rede corporativa, o analista de segurança precisa decidir, em meio a um volume grande de conexões, quais merecem investigação — e reunir o contexto de cada uma custa tempo e atenção.
2. **Contribuição técnica do TCC:** um modelo de *Machine Learning* leve que classifica o tráfego em tempo real e associa a cada conexão uma categoria prevista e um grau de confiança.
3. **Como uma pessoa poderia utilizar essa contribuição:** por um painel que apresenta essas classificações com o contexto da conexão, para que o analista **interprete** a situação e **decida o encaminhamento** mais cedo do que leria logs brutos — um benefício ainda a ser avaliado (H26).

> **Nota de revisão (feedback E01, itens 1 e 2):** a redação anterior terminava em “identificar e conter ameaças na rede instantaneamente”. “Conter” está fora do recorte (quadro no fim da seção 2) e “instantaneamente” confundia o tempo de inferência do modelo com o tempo de trabalho da pessoa. A limitação de 4.6 — resultados obtidos em dataset estático — vale também para esta síntese.


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
