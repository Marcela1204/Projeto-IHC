# Entrega 7 — Coleta de dados, necessidades e aspectos éticos

**Data:** 22/10/2026  
**Status:** `🟨 em andamento`   

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

**Autor(a):** Lucas Kerr do Amaral — 22.123.032-9   

#### Que dados coletar?

| Dado/informação | Hipótese/lacuna relacionada | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| {{...}} | {{H01/H02/...}} | {{...}} | {{...}} |

#### De quem coletar?

| Perfil/stakeholder | Critério de inclusão | Relação com persona/público |
|---|---|---|
| {{...}} | {{...}} | {{...}} |

#### Aspectos éticos

Analise voluntariedade, consentimento, minimização de dados, privacidade, riscos, gravação, anonimização, armazenamento e descarte. Não responda apenas “sim, por causa da LGPD”: explique **quais dados e riscos existem neste projeto**.

---

### A02 — Marcela Nalesso

**Autor(a):** Marcela Nalesso — 22.222.011-3   

#### Que dados coletar?

| Dado/informação | Hipótese/lacuna relacionada | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| Como a troca de classificador ou ajuste de configuração é feita na prática | H05, H22, H27 | A rotina real pode não corresponder ao que a equipe imagina; a interface precisa respeitar o processo | Área de configuração, sinal de mudança de modelo, confirmação antes de aplicar |
| Quais métricas o administrador observa antes de decidir | H05, H27 | A decisão de manter, ajustar ou reverter configurações depende de indicadores mais do que de uma única métrica | Comparação entre modelo atual e candidato, painel de validação e revisão de impacto |
| Como ele interpreta “impacto”, “desempenho” e “segurança” no contexto operacional | H05, H27, H28 | O vocabulário do domínio pode exigir abstrações e tradução visual para reduzir erro | Termos e legendas do painel, etiquetas de ação e explicações sobre risco |
| Frequência e criticidade de alterações na configuração do IDS | H22, H29 | Isso define se a ação deve ser tratada como tarefa rotineira ou de alerta prioritário | Prioridade visual, fluxo de confirmação e possibilidade de reversão |
| Necessidade de histórico e rastreio de mudanças | H31, H27 | O administrador pode precisar saber quando um modelo mudou, por quem e por qual motivo | Indicador de “tempo desde promoção”, histórico de versões e trilha de decisão |

#### De quem coletar?

| Perfil/stakeholder | Critério de inclusão | Relação com persona/público |
|---|---|---|
| Administrador de infraestrutura / segurança operacional | Atua na manutenção de IDS, regras, políticas e parametrização | P02 — Vanessa Toledo, fluxo de configuração e validação |
| Analista de rede / SOC com rotina de parametrização | Já teve contato com ajustes de sensibilidade, tráfego e alertas | Papel complementar, importante para entender o ponto de contato entre configuração e investigação |
| Gestor de TI ou responsável por estabilidade da rede | Acompanha impacto operacional e decisão de mudança | Stakeholder de contexto, principalmente para avaliar risco, mudança e continuidade |

#### Aspectos éticos

A pesquisa com administradores envolve dados sobre configuração de rede, regras, taxa de alertas e impacto em infraestrutura crítica. Embora não sejam necessariamente dados pessoais, esses elementos podem revelar arquitetura de rede, design de firewall, políticas internas e vulnerabilidades operacionais, sendo sensíveis para a organização. Portanto, a coleta deve enfatizar o processo de decisão e não detalhes de infraestrutura que permitam mapear uma rede em produção.

O consentimento deve informar que a pesquisa não exige exposição de dados confidenciais e que o participante pode omitir informações que considere sensíveis. O participante deve decidir se autoriza gravação de áudio, gravação de tela, ou apenas resposta em formulário. O registro de telas deve evitar mostrar nomes de hosts, sub-redes, senhas, endpoints internos ou dados de clientes.

Para garantir minimização, os dados devem ser anonimizados por meio de códigos e substituição de nomes, endereços e identificadores. A análise deve considerar apenas os padrões de decisão, critérios de avaliação e linguagem necessária para o design, e não a arquitetura completa do ambiente. O armazenamento deve ser controlado, com acesso restrito ao grupo, e o descarte deve ocorrer após a conclusão da disciplina ou período acadêmico previsto.

> Repita A02, A03...

## Parte B — ferramentas de coleta

> Cada integrante deve preparar uma técnica/instrumento completo. As técnicas devem ser diferentes entre si e **questionário deve estar entre as técnicas escolhidas**, conforme o enunciado da disciplina.

### Instrumento I01 — Questionário estruturado

**Autor(a):** Marcela Nalesso — 22.222.011-3  
**Técnica:** questionário  
**Objetivo:** mapear o perfil dos usuários, sua rotina de operação, seu vocabulário, a frequência de alertas e os critérios que usam para decidir sobre uma ocorrência ou uma alteração de configuração.  
**Público:** analistas de SOC, administradores de rede/segurança e profissionais que realizam monitoramento ou triagem de incidentes.

#### Procedimento padronizado de aplicação

1. Preparação: definir público-alvo e versão final do questionário; garantir que as perguntas sejam neutras, curtas e adaptadas ao domínio de segurança de redes.
2. Apresentação/consentimento: explicar objetivo da pesquisa, duração estimada, voluntariedade, uso acadêmico dos dados e garantia de anonimização.
3. Aplicação: questionário autoaplicável, em formato digital ou impresso; tempo estimado de 8 a 12 minutos; evitar interferência do entrevistador.
4. Encerramento: agradecer a participação, confirmar que o participante pode solicitar exclusão dos dados e informar como a síntese será devolvida.
5. Armazenamento/anonimização: armazenar respostas em planilha ou formulário sem identificação direta; codificar respostas por participante e remover nomes, redes e dados sensíveis.

#### Instrumento

1. Qual é o seu papel principal hoje?  
   a) Analista de SOC  
   b) Administrador de rede/segurança  
   c) Gestor de TI  
   d) Outro: _______

2. Há quanto tempo você atua nessa função?  
   a) Menos de 1 ano  
   b) 1 a 3 anos  
   c) 3 a 5 anos  
   d) Mais de 5 anos

3. Com que frequência você acompanha alertas ou logs de rede?  
   a) Diariamente  
   b) Algumas vezes por semana  
   c) Em plantões ou situações de crise  
   d) Raramente

4. Em sua rotina, qual é a atividade mais frequente?  
   a) Monitorar o estado geral da rede  
   b) Investigar uma ocorrência sinalizada  
   c) Ajustar regras, parâmetros ou modelos  
   d) Registrar/encaminhar decisão  
   e) Outra: _______

5. O que você normalmente consulta para decidir se uma ocorrência é relevante?  
   a) Volume de tráfego  
   b) Origem/destino da conexão  
   c) Severidade do alerta  
   d) Histórico de ocorrências  
   e) Comparação com comportamento anterior  
   f) Outro: _______

6. Qual dessas informações você considera indispensável para avaliar um alerta? (marque até 3)  
   a) Origem  
   b) Destino  
   c) Protocolo/serviço  
   d) Severidade  
   e) Confiabilidade da classificação  
   f) Histórico de alertas  
   g) Contexto do fluxo  
   h) Nenhuma das anteriores

7. Em uma situação de rotina, como você avalia a urgência de uma ocorrência?  
   a) Somente pela severidade do sistema  
   b) Avalio origem, destino e impacto potencial  
   c) Considero o histórico anterior  
   d) Depende do contexto do momento  
   e) Não tenho critério fixo

8. Você costuma lidar com situações em que precisa decidir rapidamente sem muita análise detalhada?  
   a) Sim, frequentemente  
   b) Sim, ocasionalmente  
   c) Raramente  
   d) Nunca

9. Quando uma decisão precisa ser tomada rapidamente, o que mais lhe falta?  
   a) Resumo claro da situação  
   b) Histórico do caso  
   c) Comparação com comportamento normal  
   d) Explicação do classificação do sistema  
   e) Nenhuma das anteriores

10. O que você acha mais útil em uma interface de monitoramento?  
   a) Indicadores resumidos  
   b) Filtros por origem/destino/protocolo  
   c) Comparações temporais  
   d) Detalhamento da ocorrência  
   e) Registro da decisão

11. O sistema precisa mostrar o que está “fora do padrão agora” sem exigir que você pesquise muito manualmente?  
   a) Sim, muito importante  
   b) Importante  
   c) Pouco importante  
   d) Não sei

12. Em sua experiência, a mudança de modelo, regra ou configuração costuma ser uma tarefa simples, delicada ou arriscada?  
   a) Simples  
   b) Delicada  
   c) Arriscada  
   d) Depende da situação

13. Você considera importante saber “quem mudou o classificador” e “há quanto tempo ele está em produção”?  
   a) Sim, muito importante  
   b) Importante  
   c) Pouco importante  
   d) Não sei

14. Para você, qual informação deve aparecer junto de um alerta para reduzir erro humano?  
   a) Categoria prevista  
   b) Nível de confiança  
   c) Critério de decisão  
   d) Severidade  
   e) Histórico do caso  
   f) Outro: _______

15. Você costuma registrar a decisão tomada sobre uma ocorrência?  
   a) Sempre  
   b) Frequentemente  
   c) Às vezes  
   d) Raramente  
   e) Nunca

16. O registro de decisão e de encaminhamento seria útil para o seu trabalho?  
   a) Sim, muito útil  
   b) Útil  
   c) Pouco útil  
   d) Não sei

17. Qual tipo de informação torna a interface mais confiável para você?  
   a) Explicação textual da classificação  
   b) Contexto dos dados  
   c) Detalhes do comportamento do fluxo  
   d) Comparação com uma linha de base  
   e) Nenhuma das anteriores

18. Você usa algum dashboard ou ferramenta de monitoramento hoje? Qual?  
   a) Sim: _______  
   b) Não

19. O que piora a experiência atual de monitoramento para você?  
   a) excesso de alertas  
   b) falta de contexto  
   c) dificuldade de comparar tendências  
   d) pouca visibilidade do histórico  
   e) ausência de explicação da classificação  
   f) outro: _______

#### Como os dados serão analisados

Os dados do questionário serão analisados por estatística descritiva, com distribuição de frequências por perfil e comparação entre respostas de analistas e administradores. Também serão identificados padrões recorrentes em relação a critérios de decisão, pressão operacional, necessidade de histórico e preferências de síntese. As respostas abertas serão codificadas em categorias temáticas, como “urgência”, “contexto”, “filtros”, “histórico”, “explicação”, “riscos de configuração” e “necessidade de rastreabilidade”.

## Síntese

O questionário busca reduzir as lacunas sobre a rotina de operação, a linguagem do domínio, a urgência de decisão e os critérios que tornam uma ocorrência relevante. Ele tem como foco principal validar ou refinar as hipóteses H04, H05, H07, H11, H12, H28, H29, H30 e H31, além de confirmar se a interface precisa priorizar síntese visual, filtros, histórico, registro da decisão e clareza na mudança de algoritmo. Os dados coletados servirão para decidir se o design deve enfatizar observação de rede, investigação de ocorrência, configuração e comparação de modelos, e para orientar atualizações na rastreabilidade da Entrega 1.

--- 

### Instrumento I02 — {{nome da técnica}}

**Autor(a):** Lucas Kerr do Amaral — 22.123.032-9     
**Técnica:** questionário / entrevista semiestruturada / observação / grupo focal / outra autorizada  
**Objetivo:** {{...}}  
**Público:** {{...}}

#### Procedimento padronizado de aplicação

1. {{preparação}}
2. {{apresentação/consentimento}}
3. {{aplicação}}
4. {{encerramento}}
5. {{armazenamento/anonimização}}

#### Instrumento

Cole aqui o questionário/roteiro completo ou forneça link **mais uma cópia textual no repositório**.

#### Como os dados serão analisados

{{ex.: distribuição de respostas, codificação temática, agrupamento de problemas}}

## Síntese

Explique quais lacunas de conhecimento sobre usuários o conjunto de técnicas pretende reduzir. Indique explicitamente quais hipóteses da Entrega 1 deverão ficar **sustentadas, refutadas ou refinadas** após a análise dos dados. Quando os dados forem coletados/analisados, atualize o histórico em `RASTREABILIDADE.md`.

## Checklist

- [ ] Hipóteses/lacunas prioritárias da Entrega 1 foram revisitadas.
- [ ] Se o escopo de IHC foi derivado de TCC técnico, a coleta investiga a plausibilidade do usuário, tarefa e contexto adotados.
- [ ] Perguntas não pressupõem que dashboard, CRUD, filtros ou relatórios sejam necessários; investigam a necessidade.
- [ ] Cada dado a coletar responde uma dúvida concreta do projeto ou justifica outra necessidade de informação.
- [ ] Parte A identifica dados e perfis de coleta de forma específica.
- [ ] Aspectos éticos são contextualizados para o projeto.
- [ ] Há uma técnica completa por integrante e técnicas distintas.
- [ ] Questionário está incluído entre as técnicas.
- [ ] Cada instrumento possui objetivo, público, procedimento e conteúdo integral.
- [ ] Perguntas evitam indução e coletam apenas dados necessários.
- [ ] Está claro como os dados serão analisados e usados no design.
