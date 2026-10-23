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
| {{...}} | {{H01/H02/...}} | {{...}} | {{...}} |

#### De quem coletar?

| Perfil/stakeholder | Critério de inclusão | Relação com persona/público |
|---|---|---|
| {{...}} | {{...}} | {{...}} |

#### Aspectos éticos

Analise voluntariedade, consentimento, minimização de dados, privacidade, riscos, gravação, anonimização, armazenamento e descarte. Não responda apenas “sim, por causa da LGPD”: explique **quais dados e riscos existem neste projeto**.

> Repita A02, A03...

## Parte B — ferramentas de coleta

> Cada integrante deve preparar uma técnica/instrumento completo. As técnicas devem ser diferentes entre si e **questionário deve estar entre as técnicas escolhidas**, conforme o enunciado da disciplina.

### Instrumento I01 — {{nome da técnica}}

**Autor(a):** Marcela Nalesso — 22.222.011-3   
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
