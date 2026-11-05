# Entrega 14 — Avaliação de usabilidade por observação de usuários

**Data:** 30/10/2026  
**Status:** `🟨 em andamento`  
**Responsabilidade:** solução consolidada por equipe. O número de participantes finais observados deve ser igual ao número de integrantes, conforme o modelo da disciplina; recomenda-se que cada integrante seja responsável por conduzir/analisar ao menos um participante.

## Objetivo da atividade

Observar usuários representativos realizando tarefas reais ou realisticamente simuladas para identificar problemas de eficácia, eficiência, compreensão e satisfação que não podem ser inferidos apenas por inspeção.

> **Participantes finais não devem ser membros da equipe.** Um integrante pode participar do teste piloto apenas para validar roteiro/equipamentos, sem contar na amostra final.

### Quando o usuário é um perfil profissional especializado

Em TCCs técnicos, o público pode ser DBA, analista, pesquisador, administrador, técnico ou outro especialista. Priorize participantes que possuam relação real com as tarefas. Se não for possível recrutar o perfil ideal, qualquer participante aproximado/proxy deve ser **justificado previamente e tratado como limitação**; não apresente o resultado como equivalente ao de especialistas reais.

O teste avalia a **interação com o protótipo**. Não é necessário que o participante valide o desempenho científico do algoritmo. Resultados simulados podem ser usados quando declarados e coerentes com a tarefa.

Tarefas podem envolver, por exemplo, interpretar um dashboard, configurar uma análise, encontrar uma execução no histórico usando filtros, comparar resultados, gerar relatório, revisar alerta ou administrar permissões.

## A. Fluxograma do processo — equipe

![Fluxograma](../assets/14_testes/fluxograma_avaliacao.svg)

O fluxograma deve representar, no mínimo: planejamento → recrutamento → consentimento → preparação → execução das tarefas/observação → pós-teste → consolidação/análise → recomendações.

> O arquivo SVG acima ainda é o *placeholder* do modelo e será substituído pela versão desenhada do fluxo abaixo. Enquanto isso, o processo planejado é:

```text
PREPARAÇÃO
 1. Planejamento ── metas da Entrega 08 (MU01–MU08, MU10–MU12, MQ01–MQ08)
 │                  perguntas QA01–QA14 da Entrega 12
 │                  tarefas UT01–UT07 + gabarito + critérios de sucesso (seção B, passo 5)
 ├─ 2. Recrutamento ── triagem de 2 participantes (1 por perfil) pelos critérios do passo 2
 │                     proxy? → registrar a condição e a limitação
 ├─ 3. Preparação do material ── protótipo F01/F02 com recorte congelado (checagem de prontidão)
 │                               TCLE, pré-teste, cartões de tarefa, planilha, SEQ, SUS, roteiro pós-teste
 └─ 4. Teste piloto ── 1 sessão por roteiro (P01 e P02), fora da amostra
       └─ ajustes? ── sim → revisar instruções/tempos-limite/protótipo → volta a 3
                   └─ não → segue
COLETA DE DADOS (U01 antes de U02; ~50 min cada, sala virtual)
 5. Abertura padronizada → 6. Consentimento (TCLE) ── não aceita → encerra, nada é registrado
 │                                                 └─ aceita → liga gravação (se autorizada)
 7. Pré-teste (perfil mínimo)
 8. Tarefas com observação (sem think aloud contínuo) ── por tarefa: cartão → execução → planilha → SEQ
 │     └─ em UT02: interrupção provocada (protocolo MU10)
 9. SUS → 10. Entrevista pós-teste → 11. Encerramento
INTERPRETAÇÃO E CONSOLIDAÇÃO
 12. Revisão das gravações e das duas planilhas (moderador + observador) → codificação de erros e falas
 13. Consolidação por participante (seção C) e por tarefa (seção D) → comparação indicativa com as metas
RELATO E RECOMENDAÇÕES
 14. Problemas PU01, PU02… → achados AU01… com severidade → recomendações (seção E)
 15. Comparação com a avaliação heurística (seção F) → conclusão (seção G)
 16. Atualização da rastreabilidade (Entregas 01, 05, 06, 08–11 e RASTREABILIDADE.md)
```

## B. Procedimento de preparação e execução — equipe

### Passo 1 — Objetivos e versão avaliada

**Objetivo do teste.** Verificar, com usuários de fora da equipe, se a camada de interação projetada nas Entregas 09–11 permite que (a) o analista (perfil P01) perceba o que está fora do padrão, interprete alertas com incerteza e registre um veredito que outra pessoa entenda (**T02**, cenário **CI01**, fluxos PF01/PF03), e que (b) a administradora (perfil P02) diagnostique a queda de qualidade, compare candidato e modelo em produção e decida a troca sabendo a consequência e o caminho de volta (**T01**, cenário **CI02**, fluxos PF02/PF03). O teste mede **interação** — compreensão, eficácia, eficiência e satisfação —, **não** a acurácia, o recall ou o tempo de inferência do pipeline, avaliados no TCC (Entrega 08, delimitação).

**Versão/commit/Figma:** protótipo Figma da Entrega 11 — fluxo **F01** (Lucas: D03 → **D04 — Registro do veredito e encaminhamento**) e fluxo **F02** (Marcela: **D05 — Comparação de modelos e troca** e **D06 — Histórico de trocas**), que reproduzem D01–D03 com recorte de dados **congelado**. Link do protótipo: {{URL do Figma — Entrega 11}}; versão congelada para os testes: {{data/versão do arquivo Figma}}; commit do repositório na data do teste: {{hash}}.  
**O que é simulado (declarado ao participante):** os dados exibidos são de laboratório do TCC, não de uma rede em produção; o registro do veredito, o encaminhamento, a promoção e a reversão do modelo **não executam nada** — são simulados no protótipo (Entrega 08, delimitação; na operação real a promoção continua pela ferramenta de linha de comando do pipeline).  
**Metas de usabilidade relacionadas:** MU01–MU08, MU10–MU12 e MQ01–MQ08 (Entrega 08, seção 3), por meio das perguntas de avaliação **QA01–QA14** que a Entrega 12 encaminha a este teste:

| Pergunta (Entrega 12) | Meta(s) | Tarefa(s) que a respondem |
|---|---|---|
| QA01 | MU01 | UT02 |
| QA02 | MU02 | UT02 |
| QA03 | MU03 | UT02 |
| QA04 | MU04 + MQ01 | UT01 |
| QA05 | MU05 | UT02 |
| QA06 | MU06 + MQ02 + MQ04 | UT02, UT03 |
| QA07 | MU07 + MQ06 | UT05 |
| QA08 | MU08 | UT05 |
| QA09 | MU10 + MQ03 | UT02 (interrupção) |
| QA10 | MU11 (SEQ) | todas, após cada tarefa |
| QA11 | MU12 (SUS) | fim de cada sessão |
| QA12 | MQ05 | UT04 |
| QA13 | MQ07 | UT06 |
| QA14 | MQ08 | UT02 (produz o registro), UT07 (outra pessoa lê o registro) |

**MU09** (contraste) é verificada por inspeção na Entrega 13 e não é medida aqui.

**Prontidão do protótipo — o que precisa existir antes do piloto** (cada tarefa depende desses estados; um “link morto” invalida a medida):

| Requisito do protótipo | Tarefa que depende | Verificado? |
|---|---|---|
| D03 com o recorte congelado: indicadores do topo com referência ao período anterior, último dado/estado da coleta, série temporal com o pico, tabela de alertas | UT01, UT02 | {{sim/não}} |
| D03 com recorte por período e por origem, contagem “N de M” e suspensão da atualização com lembrete | UT02 | {{sim/não}} |
| Detalhe de alerta com contexto da conexão, motivo do sinal, quem decidiu e incerteza; três alertas-alvo (ver “Gabarito”) | UT02, UT03 | {{sim/não}} |
| D04 com resumo antes de registrar, aviso de incerteza alta, confirmação com autor/horário, opção de desfazer, encaminhamento e passagem de plantão | UT02, UT07 | {{sim/não}} |
| Estado da investigação preservado ao voltar à tela (período, filtros, suspensão, alertas examinados) | UT02 (interrupção) | {{sim/não}} |
| Indicação do modelo ativo e de desde quando em todos os dashboards | UT03 | {{sim/não}} |
| Estado “sem dados” (coleta parada) distinguível de “nenhum alerta” | UT04 | {{sim/não}} |
| Alertas não confirmados, saúde do pipeline (coleta, atraso, carga) e D06 com a troca v6 → v7 | UT05 | {{sim/não}} |
| D05 com dois candidatos — v8 aprovado e um candidato reprovado no cenário benigno —, efeito previsto, carga prevista e confirmação com motivo | UT05 | {{sim/não}} |
| Reversão com confirmação e registro em D06; aviso de troca aos analistas | UT06 | {{sim/não}} |

### Passo 2 — Participantes

**Amostra.** A equipe tem 2 integrantes; conforme o modelo da disciplina, serão realizados **2 testes finais**, um por perfil: **U01** (perfil P01 — Thiago, tarefa T02), conduzido por Lucas, e **U02** (perfil P02 — Vanessa, tarefa T01), conduzido por Marcela. As metas da Entrega 08 foram escritas para 5 participantes por perfil (“80%” = 4 de 5); com **n = 1 por perfil**, os resultados são relatados como “x de n” e as metas são tratadas como **indicativas** — servem para apontar onde a interação falhou, não para afirmar que a meta foi atingida (ver seção D).

**Critérios de inclusão — P01 (U01, T02):** experiência profissional ou de estágio em monitoramento de rede/segurança (SOC, NOC, resposta a incidentes) **ou** estudante dos últimos anos de Computação/Sistemas/Engenharia com disciplina ou projeto em segurança de redes e uso de alguma ferramenta de monitoramento (SIEM, IDS, painéis do tipo Grafana/Kibana).  
**Critérios de inclusão — P02 (U02, T01):** experiência em administração de sistemas/infraestrutura **ou** em ML aplicado (já treinou ou avaliou um classificador e conhece precisão, recall e taxa de falso positivo).  
**Critérios de exclusão (ambos):** integrantes da equipe; quem participou da construção dos protótipos, do *walkthrough* da Entrega 06 ou da inspeção heurística da Entrega 13; o orientador do TCC; quem já viu o recorte congelado; menores de 18 anos.  
**Participante *proxy*:** quem atende só a parte “estudante” dos critérios, sem prática em operação, é registrado como **proxy** já na triagem e o resultado é tratado como limitação (seção G). A possibilidade de proxy foi prevista nas Entregas 07 e 08. Como há um único participante por perfil, a equipe prioriza, nesta ordem: profissional da área → estagiário/monitor com prática → estudante (proxy).

| ID | Perfil | Critérios que justificam participação | Integrante responsável |
|---|---|---|---|
| U01 | P01 — analista de SOC (T02). Participante a recrutar; sem nome real: {{perfil resumido após a triagem; proxy sim/não}} | Critérios de inclusão P01 verificados na triagem: {{experiência declarada}} | Lucas Kerr do Amaral — 22.123.032-9 (moderador); Marcela Nalesso (observadora) |
| U02 | P02 — administradora da plataforma (T01). Participante a recrutar; sem nome real: {{perfil resumido após a triagem; proxy sim/não}} | Critérios de inclusão P02 verificados na triagem: {{experiência declarada}} | Marcela Nalesso — 22.222.011-3 (moderadora); Lucas Kerr do Amaral (observador) |

**Recrutamento:** convite a contatos profissionais dos integrantes na área de segurança/infraestrutura e a estudantes de Computação da instituição, com triagem por mensagem usando as perguntas do pré-teste (passo 6). **U01 é realizado antes de U02**, porque U02 lê o registro produzido por U01 (UT07). Datas das sessões: {{dd/mm/aaaa}}.

### Passo 3 — Consentimento e privacidade

- Termo/registro de consentimento: modelo da disciplina em [`../instrumentos/termo_consentimento_modelo.md`](../instrumentos/termo_consentimento_modelo.md), preenchido para este teste conforme o quadro abaixo (estrutura dos TCLE de exemplo em `../aulas/`: procedimento, riscos, benefícios e custos, confidencialidade, voluntariedade, declaração). O aceite é registrado por formulário eletrônico com cópia ao participante, **antes** de qualquer gravação. Registros de aceite: {{link para pasta restrita — a preencher}}.
- Gravação de tela/áudio/vídeo: **tela e áudio, sim, somente se autorizado** em campo próprio do termo; **vídeo da câmera, não**. Finalidade: conferir tempos, erros e falas na consolidação. Sem autorização, a sessão ocorre apenas com as anotações da planilha.
- Forma de anonimização: IDs `U01` e `U02` atribuídos na triagem; a relação ID–nome fica só com os integrantes, fora do repositório. No repositório entram apenas planilhas e trechos de fala transcritos sob o ID, sem empresa, cargo exato ou instituição de trabalho. Os dados do protótipo são de laboratório, sem IPs de pessoas reais (Entrega 08, LGPD). O registro de U01 lido por U02 em UT07 é o que U01 escreveu no protótipo, sem identificação de U01.
- Local e período de armazenamento: gravações e termos em pasta de nuvem institucional com acesso restrito aos dois integrantes; **descarte das gravações ao fim da disciplina** (critério da Entrega 07); planilhas anonimizadas permanecem no repositório.

**Termo adaptado a este teste** (texto a ser lido e aceito pelo participante):

| Item do termo | Conteúdo |
|---|---|
| Projeto | Projeto de IHC da disciplina CC8122 — camada de interação de um IDS com aprendizado de máquina (TCC), com painéis de monitoramento e telas de decisão |
| Atividade | Teste de usabilidade com observação, em sala virtual |
| Responsáveis | Lucas Kerr do Amaral e Marcela Nalesso; contato institucional: {{e-mail institucional da equipe}}; docente da disciplina: {{nome}} |
| Convite e objetivo | Avaliar se as telas de um protótipo ajudam a investigar alertas de rede (ou a decidir sobre a troca de um modelo de detecção). **Estamos avaliando o protótipo, não a sua capacidade.** Não há respostas certas ou erradas sobre você |
| O que será solicitado | Responder a um questionário curto de perfil; realizar de 4 a 5 tarefas no protótipo e comentar suas decisões ao fim de cada uma; responder a uma pergunta de facilidade após cada tarefa, a um questionário final de 10 itens e a uma entrevista curta. Duração aproximada: 50 minutos. Em uma das tarefas pode haver uma breve interrupção proposital |
| Simulação | Os dados são de laboratório e nenhuma ação no protótipo tem efeito real em rede ou sistema |
| Registros | Gravação de **tela e áudio** somente com autorização marcada neste termo (sim/não). Finalidade: análise da sessão pela equipe. Acesso: apenas os dois responsáveis. Descarte: ao fim da disciplina. O texto que você escrever no protótipo poderá ser lido, sem identificação, por outro participante |
| Riscos e desconfortos | Mínimos: cansaço ou desconforto de ser observado. A sessão pode ser pausada ou encerrada a qualquer momento. Não pedimos informações da sua empresa, rede ou clientes; se citar alguma, ela será omitida da transcrição |
| Benefícios e custos | Sem custo e sem remuneração. A participação contribui para a melhoria do protótipo |
| Confidencialidade | Resultados publicados apenas com identificador anônimo (U01, U02); nome e organização não serão identificados |
| Voluntariedade | Participação voluntária; é possível desistir a qualquer momento, sem justificativa e sem prejuízo; os dados de quem desistir são descartados se assim pedir |
| Declaração | Declaro ter mais de 18 anos, ter recebido informações suficientes e concordar em participar. Autorizo gravação de tela e áudio: ( ) sim ( ) não |

### Passo 4 — Teste piloto

**Data:** {{dd/mm/aaaa — a realizar antes de U01}}  
**Planejamento:** uma sessão piloto por roteiro, completa e cronometrada. O piloto do roteiro P01 é conduzido por Lucas e o do P02 por Marcela; o participante do piloto é o outro integrante ou um colega de turma que não será U01/U02 — em ambos os casos **não conta** na amostra final.  
**O que foi validado:** roteiro, duração, entendimento das instruções, protótipo, gravação. Itens específicos: (1) os cartões de tarefa não revelam rótulos de controles; (2) todos os estados da tabela de prontidão (passo 1) funcionam e não há links mortos; (3) a interrupção de UT02 cabe em ~1 min e o estado volta intacto; (4) tempos-limite e duração total (~50 min); (5) a gravação capta tela e áudio na sala virtual; (6) moderador e observador classificam do mesmo modo sucesso, erro e ajuda (comparar as duas planilhas do piloto); (7) recalibrar os valores de MU04, MU05, MU08 e MU10, como previsto na Entrega 08, **sem mudar o que cada meta mede**.  
**Mudanças após piloto:** {{a preencher após o piloto}}

### Passo 5 — Tarefas

As tarefas derivam de T01/T02 (Entrega 05), dos cenários CI01/CI02 e dos objetivos O01–O13 (Entrega 09), e seguem os IDs UT01–UT07 da Entrega 12. Os cartões apresentam a situação e o objetivo **sem** nomear telas, botões ou rótulos (D03, D04, “Registrar”, “Promover”, “margem” etc.). A ordem é fixa por perfil, porque segue a sequência de trabalho do cenário:

- **U01 (P01):** UT01 → UT02 → UT03 → UT04.
- **U02 (P02):** UT04 → UT03 (só itens a e b) → UT05 → UT06 → UT07.

**Situação comum apresentada a U01 (lida antes de UT01):** “Você é analista de segurança em um plantão noturno. A equipe usa um sistema de detecção que classifica conexões de rede e mostra os resultados nestas telas. Você estava escrevendo o relatório de outro caso e agora vai olhar o sistema.”  
**Situação comum apresentada a U02 (lida antes de UT04):** “Você é responsável pela plataforma de detecção que os analistas usam. Hoje de manhã você vai verificar se o modelo que classifica as conexões continua adequado.”

| ID | Cenário/instrução apresentada | Critério de sucesso | Métricas | Ligação com modelo |
|---|---|---|---|---|
| UT01 | “Antes de voltar ao seu relatório, você quer saber se está acontecendo algo diferente do normal na rede agora. Diga em voz alta o que você concluiu e, se houver algo, desde quando.” (A tela inicial já está aberta.) | **Total:** sem abrir a tabela nem um alerta, diz que o volume de ataques está acima do período anterior e indica **quando** começou (por volta das 19h, tolerância ±15 min). **Parcial:** acerta o “há algo”, mas não o “quando”, ou só chega lá abrindo a tabela. **Falha:** diz que está normal, cita só a contagem bruta sem referência (“tem 1,6 mil ataques”) ou excede 2 min | sucesso, tempo (MU04), erros, ajudas, fala (MQ01), SEQ · **QA04, QA10** | T02/A01 · O01 · CI01 [1, 2] · F01 (D03) |
| UT02 | “Os alertas vêm de um mesmo segmento de rede. Investigue o período do aumento e decida, para cada um dos três alertas indicados neste cartão, se é ataque, se não é, ou se não dá para afirmar. Deixe a decisão registrada com o motivo, encaminhe à equipe que fará o bloqueio o que for preciso e deixe pronto o que o próximo turno precisa saber.” (O cartão identifica os três alertas pela hora e pela origem — ver Gabarito.) Interrupção provocada durante a tarefa (passo 6) | **Total:** recorta período e origem; registra os três vereditos **coerentes com o gabarito**, cada um com justificativa; encaminha o caso à infraestrutura e deixa a passagem de plantão com o alerta indefinido em aberto; sem erro crítico; sem ajuda. **Parcial:** registra os três, mas com um veredito incoerente não crítico, justificativa ausente, encaminhamento/passagem incompletos, ou com ajuda. **Falha:** não registra algum veredito, comete erro crítico (MU03) ou excede 15 min | sucesso (MU01), vereditos coerentes (MU02), erros críticos (MU03), tempo por alerta (MU05), retomada (MU10, MQ03), fala ao explicar cada alerta (MQ02), registro produzido (MQ08), ajudas, SEQ · **QA01, QA02, QA03, QA05, QA06, QA09, QA14, QA10** | T02/A02 e 3.1 · O02, O03, O05, O06, O07 · CI01 [3–6, 9–11] · F01 (D03 → D04) |
| UT03 | “Antes de seguir, responda com base no que está na tela: (a) nesta linha [o moderador aponta um alerta já classificado], quem decidiu a classificação? (b) há quanto tempo o modelo que está classificando estas conexões está em uso? (c) o volume de ataques destes últimos dias está maior que o normal — o que, na sua opinião, pode explicar isso?” (c) só para U01; pergunta aberta, sem sugerir a troca | **(a)** estágio indicado na linha do recorte congelado: {{estágio da linha escolhida}}. **(b)** desde 27/10, há três dias. **(c)** levanta, **sem indução**, a hipótese da troca de modelo recente. Cada item é certo/errado; sem ajuda | acertos (MU06), fala (MQ02, MQ04), tempo, SEQ · **QA06, QA10** | O03, O04 · CI01 [6, 7] · F01/F02 (D01–D03) |
| UT04 | “Você volta a olhar o sistema e um dos quadros está vazio. O que isso quer dizer para você? O que você faria?” | **Total:** diz que a coleta parou (ou que não chegam dados), que isso **não** significa ausência de alertas e indica a quem recorrer. **Parcial:** suspeita da coleta, mas não descarta “sem alertas”. **Falha:** interpreta como “nenhum alerta”/“rede tranquila” ou excede 2 min | sucesso, tempo, fala (MQ05), SEQ · **QA12, QA10** | O01/O09 · CI01 [12] · F01 e F02 (estado “sem dados”) |
| UT05 | “Os analistas comentaram que muitos alertas da última semana não se confirmaram. Descubra o que está acontecendo e decida se algum dos modelos candidatos disponíveis deve substituir o modelo atual. Se decidir trocar, faça a troca; a janela de manutenção já foi autorizada pelo coordenador. Explique em voz alta o que encontrou e por que decidiu assim.” | **Total:** (1) identifica a subida da proporção de alertas não confirmados após a troca de 27/10 e descarta coleta/equipamento (coleta ativa, atraso ~40 s, carga 62%); (2) **promove o v8**, citando o cenário e a métrica que decidiram (benigno; fração do benigno marcada como ataque 0,21 → 0,04, máximo 0,05) e o efeito/custo para os analistas (≈ 35% menos alertas; dois ataques de força bruta do conjunto de teste deixariam de ser sinalizados); (3) **não promove** o candidato reprovado, citando cenário benigno e taxa de falso positivo 0,215 acima do máximo 0,05; (4) confirma a troca com motivo registrado. **Parcial:** decisões corretas sem o motivo completo (cenário + métrica) ou sem considerar o custo, diagnóstico incompleto, ou com ajuda. **Falha:** não decide, promove o candidato reprovado (erro crítico de T01), não conclui a troca ou excede 10 min | sucesso, decisões + motivo (MU07, MQ06), tempo total de T01 (MU08), erros, ajudas, SEQ · **QA07, QA08, QA10** | T01 (1–4) · O08, O09, O10, O11, O12, O13 · CI02 [1–7, 10] · F02 (D05, D06) |
| UT06 | “É o dia seguinte. Você concluiu que a troca de ontem não teve o efeito esperado. Faça o que for preciso e diga como a equipe fica sabendo.” | **Total:** reverte para o modelo anterior com confirmação e indica onde a troca fica registrada (histórico de trocas) e que os analistas são avisados; não manifesta receio de “quebrar a produção”. **Parcial:** reverte, mas não sabe dizer onde fica registrado/como a equipe é avisada, ou com ajuda. **Falha:** não encontra o caminho de reversão ou excede 5 min | sucesso, tempo, fala (MQ07), ajudas, SEQ · **QA13, QA10** | T01 (4.3, 5) · O12, O13 · CI02 [7–9] · F02 (D05, D06) |
| UT07 | Aplicada a U02, ao fim das tarefas: “Um analista do turno anterior deixou este registro [o moderador mostra **somente** o registro e o encaminhamento produzidos por U01 em UT02, sem o protótipo]. Qual foi a conclusão dele? Com base em quê?” | **Total:** reproduz a conclusão e ao menos um elemento da base registrada. **Falha:** não consegue dizer a conclusão ou a base. (Se U01 não tiver concluído o registro, o moderador usa um registro-padrão preparado pela equipe e anota isso como limitação) | sucesso, fala (MQ08) · **QA14** | O05, O06 · CI01 [10, 11] · F01 (D04) |

**Gabarito dos três alertas de UT02** (definido antes do teste, no recorte congelado):

| Alerta | Característica no recorte | Veredito do gabarito | Erro crítico (MU03) | Identificação no protótipo |
|---|---|---|---|---|
| A-1 “claro” | Classificado como ataque pelo modelo supervisionado com incerteza **baixa**; origem sem histórico com o destino; volume mais incomum que 99% do habitual do destino | **ataque** | registrar como **benigno** | {{hora e origem da linha no F01}} |
| A-2 “margem pequena” | Classificado como ataque, mas com incerteza **alta** (classificação perto de mudar) | **indefinido** | registrar como **ataque sem ter aberto o detalhe** do alerta. Registrar “ataque” depois de consultar o detalhe conta como veredito **incoerente**, mas não crítico | {{...}} |
| A-3 “benigno com volume alto” | Parte de uma rajada de volume alto, classificado como benigno, com origem e destino habituais (padrão do pico das 19h05 observado no *walkthrough*, Entrega 06, passo A4) | **benigno** | — (registrar ataque é veredito incoerente, não crítico) | {{...}} |

**O moderador pode esclarecer:** termos do cenário (plantão, segmento de rede, turno, janela de manutenção, coordenador) e o que é simulado. **O moderador não deve dizer:** nomes ou localização de telas, botões, filtros, colunas e indicadores; o significado de margem, incerteza, percentil ou fpr; se um veredito ou decisão está certo; que o aumento coincide com a troca de modelo.

### Passo 6 — Protocolo do moderador

1. Receber participante e explicar que **o produto está sendo avaliado, não a pessoa**.
2. Obter consentimento.
3. Aplicar perfil pré-teste mínimo necessário.
4. Ler instruções padronizadas.
5. Observar sem ensinar o caminho; registrar pedidos de ajuda separadamente.
6. Se usar *think aloud*, explicar e aplicar de forma consistente.
7. Após cada tarefa, registrar satisfação/SEQ ou escala definida.
8. Fazer pós-teste/entrevista breve.
9. Encerrar e explicar uso dos dados.

**Aplicação ao projeto** (roteiro base: [`../instrumentos/roteiro_teste_usabilidade.md`](../instrumentos/roteiro_teste_usabilidade.md)):

| Momento | Duração | O que acontece | Quem |
|---|---:|---|---|
| Antes da sessão | — | Abrir o protótipo na versão congelada em janela de navegador de **1366 × 768** (pior caso da Entrega 08: plantão remoto em notebook); voltar o protótipo ao estado inicial; testar gravação; abrir planilha, cartões de tarefa e formulários SEQ/SUS. Para U02: separar o registro produzido por U01 (UT07) | moderador + observador |
| Abertura | 3 min | Agradecer; explicar o objetivo geral **sem revelar hipóteses**; reforçar que o protótipo é avaliado, não a pessoa; dizer que os dados são de laboratório e que as ações são simuladas; explicar que pode parar a qualquer momento | moderador |
| Consentimento | 3 min | Leitura do termo (passo 3) e aceite; só então liga a gravação, se autorizada | moderador |
| Pré-teste | 3 min | Função/área e tempo de experiência; frequência de uso de SIEM/IDS/painéis de monitoramento; familiaridade com métricas de classificação (precisão, recall, taxa de falso positivo); dificuldade de distinguir cores (a classificação usa cor + texto); condição de proxy | moderador |
| Verbalização | 1 min | Conforme a Entrega 12, **não** se usa *think aloud* contínuo nas tarefas cronometradas, porque distorceria MU04, MU05, MU08 e MU10. O participante pode comentar livremente; comentários espontâneos são anotados, e a explicação de cada decisão é pedida **depois** da tarefa (retrospectiva curta). O moderador não pede que o participante fale durante a tarefa | moderador |
| Tarefas | ~25 min | Na ordem do passo 5. Para cada uma: moderador lê o cartão e o envia por escrito no chat; o observador inicia o cronômetro ao fim da leitura; ao fim, SEQ (“No geral, quão fácil ou difícil foi esta tarefa?”, 1 = muito difícil, 7 = muito fácil) e “O que tornou a tarefa fácil ou difícil?” | moderador lê; observador cronometra e preenche a planilha |
| SUS | 3 min | Questionário SUS de 10 itens (versão em português), sobre a sessão inteira | participante |
| Entrevista pós-teste | 5 min | “O que foi mais difícil?”; “Em que momento você ficou em dúvida sobre o que a tela queria dizer?”; “Você confiaria nesta tela num plantão real (U01) / para trocar o modelo em produção (U02)? Por quê?”; “O que você mudaria primeiro?”; esclarecer comportamentos anotados durante as tarefas | moderador; observador pode acrescentar perguntas |
| Encerramento | 2 min | Agradecer; confirmar uso e descarte dos dados; salvar arquivos com o ID; registrar limitações da sessão (ambiente, conexão, proxy). Em U01: salvar o registro e o encaminhamento produzidos em UT02 para UT07 | moderador + observador |

**Regras durante a tarefa.**

- **Ajuda** é qualquer intervenção do moderador sobre a interface (onde está, o que significa um elemento, se o caminho está certo) — mesma definição de MU01. É dada apenas quando o participante pede **e** está parado há mais de 1 min, ou quando pede para desistir; é registrada com o horário e o conteúdo. Esclarecer termos do cenário **não** é ajuda.
- Perguntas do participante sobre a interface são devolvidas de forma neutra (“O que você acha?”, “O que você faria se estivesse sozinho?”).
- Ao atingir o tempo-limite, o moderador encerra a tarefa (registrada como falha por tempo) e passa à próxima; quando a tarefa seguinte depende do estado da anterior (UT05 → UT06), o protótipo é posto no estado de início da próxima.

**Protocolo de interrupção (MU10, MQ03 — QA09)** — aplicado em UT02:

1. **Quando:** logo depois que U01 registrar o veredito do **primeiro** alerta e antes de abrir o segundo (estado: recorte e suspensão ativos, um alerta examinado).
2. **Como:** o moderador diz “Preciso que você pare um instante para me ajudar com outra coisa”, pede que o participante tire as mãos do mouse e deixe a tela como está, e mostra no chat um texto curto de outra ocorrência com duas perguntas simples sobre ele. Duração: **60 s** cronometrados pelo observador. O protótipo não é tocado por ninguém.
3. **Retorno:** o moderador diz “Obrigado. Pode voltar à sua tarefa e continuar de onde parou; diga em voz alta onde estava.”
4. **Medida:** o tempo de MU10 vai do fim dessa frase até a **próxima ação útil** (ação que avança a tarefa a partir do ponto em que parou — abrir o segundo alerta, por exemplo). O observador registra se o participante disse corretamente período, origem, estado da suspensão e quantos alertas já tinha examinado (MQ03), e se refez o recorte sem necessidade (erro de retomada).
5. A duração da interrupção é **descontada** do tempo do segundo alerta em MU05.

### Passo 7 — Registro e forma de análise

**Planilha.** Uma planilha por participante, no modelo de [`../instrumentos/planilha_observacao_modelo.md`](../instrumentos/planilha_observacao_modelo.md), com as colunas do modelo (início, fim, sucesso, erros, ajudas, hesitações, fala relevante, satisfação) acrescidas de: **erros críticos**, **tipo de erro** (códigos abaixo), **vereditos × gabarito** (UT02), **retomada** (UT02) e **pergunta QA** atendida. Moderador e observador preenchem planilhas separadas; divergências são resolvidas pela gravação.

**Definições adotadas** (as mesmas para os dois observadores):

| Termo | Definição |
|---|---|
| Sucesso total | Critério da tarefa atingido sem ajuda, dentro do tempo-limite |
| Sucesso parcial | Critério atingido com ajuda, ou com um elemento não crítico faltando (conforme a coluna “Critério de sucesso”) |
| Falha | Critério não atingido, abandono, tempo-limite excedido ou erro crítico |
| Erro | Ação ou interpretação verbalizada que se afasta do caminho para o objetivo e precisa ser desfeita ou corrigida. Códigos: **EI** interpretação (ler incerteza alta como confirmado, contagem como tendência, vazio como “sem alertas”), **EN** navegação (procurar a informação na tela errada), **ER** recorte (filtro ou período errado), **EG** registro (alcance ou classe errados no veredito ou na troca), **ET** retomada (refazer recorte já feito) |
| Erro crítico | T02 (definição de MU03): registrar como benigno o alerta que o gabarito define como ataque, ou registrar como ataque o alerta de margem pequena sem consultar o detalhe. T01: promover o candidato reprovado |
| Ajuda | Intervenção do moderador sobre a interface (passo 6) |
| Hesitação | Mais de 10 s sem ação nem fala, ou ida e volta entre áreas sem ação; anotada, mas **não** convertida em problema sem evidência adicional (fala, erro ou SEQ baixo) |
| Tempo | Do fim da leitura do cartão até o critério de conclusão da tarefa, medido na gravação (ou cronômetro do observador, sem gravação). MU04: até a resposta verbal com o “quando”. MU05: por alerta — o primeiro conta desde o fim da leitura do cartão (inclui o recorte); o segundo e o terceiro, desde a confirmação do registro anterior; termina na confirmação do registro (interrupção descontada). MU08: duração de UT05 (do fim da leitura à confirmação da troca) |

**Codificação das falas e problemas.** Falas e comportamentos relevantes são transcritos sob o ID do participante e agrupados por tarefa e por objetivo (O01–O13). Cada dificuldade observada vira um **problema de usabilidade (PU01, PU02…)** com: tarefa, tela, evidência quantitativa (“x de n”) e qualitativa (fala/comportamento), meta e pergunta QA afetadas. A severidade usa a escala 0–4 da Entrega 13, considerando impacto (erro crítico, falha, tempo) e persistência (repetiu-se em mais de uma tarefa); com n = 1 por perfil, a frequência entre participantes só pesa para problemas vistos nos dois perfis (UT03, UT04).

**Comparação com as metas.** Cada meta é comparada pela regra da seção D e marcada como **indicativa**: com um participante por perfil, “atendida” significa “o participante teve o desempenho previsto na meta”, não que a meta foi verificada para a população.

## C. Resultados — por participante

> **A preencher após as sessões.** Nenhuma sessão foi realizada até 30/10/2026. A estrutura abaixo é o registro que será usado.

### U01 — {{perfil resumido: P01, experiência, proxy sim/não}}

**Moderador:** Lucas Kerr do Amaral · **Observadora:** Marcela Nalesso · **Data:** {{dd/mm/aaaa}}

| Tarefa | Grau de sucesso | Erros | Tipos de erro/dificuldade | Ajudas | Tempo | Satisfação | Evidência/observação |
|---|---|---:|---|---:|---|---|---|
| UT01 | {{total/parcial/falha}} | {{n}} | {{códigos EI/EN/ER/EG/ET}} | {{n}} | {{mm:ss}} (MU04) | SEQ {{1–7}} | {{fala/comportamento — MQ01}} |
| UT02 | {{total/parcial/falha}} | {{n}} (críticos: {{n}}) | {{...}} | {{n}} | A-1 {{mm:ss}} · A-2 {{mm:ss}} · A-3 {{mm:ss}} (MU05); retomada {{ss}} s (MU10) | SEQ {{1–7}} | Vereditos A-1/A-2/A-3: {{...}} × gabarito; retomada: {{disse período/origem/suspensão? sim/não}}; encaminhamento e passagem: {{...}} |
| UT03 | {{a/b/c certos}} | {{n}} | {{...}} | {{n}} | {{mm:ss}} | SEQ {{1–7}} | (c) levantou a hipótese da troca sem indução? {{sim/não}} |
| UT04 | {{total/parcial/falha}} | {{n}} | {{...}} | {{n}} | {{mm:ss}} | SEQ {{1–7}} | {{...}} |

**SUS:** {{0–100}}  
**Link da gravação (se autorizado):** {{link restrito}}  
**Resposta pós-teste:** {{...}}

### U02 — {{perfil resumido: P02, experiência, proxy sim/não}}

**Moderadora:** Marcela Nalesso · **Observador:** Lucas Kerr do Amaral · **Data:** {{dd/mm/aaaa}}

| Tarefa | Grau de sucesso | Erros | Tipos de erro/dificuldade | Ajudas | Tempo | Satisfação | Evidência/observação |
|---|---|---:|---|---:|---|---|---|
| UT04 | {{total/parcial/falha}} | {{n}} | {{...}} | {{n}} | {{mm:ss}} | SEQ {{1–7}} | {{...}} |
| UT03 (a, b) | {{a/b certos}} | {{n}} | {{...}} | {{n}} | {{mm:ss}} | SEQ {{1–7}} | {{...}} |
| UT05 | {{total/parcial/falha}} | {{n}} (críticos: {{n}}) | {{...}} | {{n}} | {{mm:ss}} (MU08) | SEQ {{1–7}} | Decisões (v8 / reprovado) e motivos citados (MU07): {{...}} |
| UT06 | {{total/parcial/falha}} | {{n}} | {{...}} | {{n}} | {{mm:ss}} | SEQ {{1–7}} | Indicou registro e aviso à equipe? {{sim/não}}; receio manifestado? {{...}} |
| UT07 | {{total/falha}} | — | {{...}} | {{n}} | {{mm:ss}} | — | Conclusão e base reproduzidas: {{...}} |

**SUS:** {{0–100}}  
**Link da gravação (se autorizado):** {{link restrito}}  
**Resposta pós-teste:** {{...}}

> Com a decisão de 2 testes (um por integrante), não há U03 em diante.

## D. Consolidação por tarefa

> **A preencher após as sessões.** Resultados como “x de n”, com n = 1 por perfil (UT03 e UT04 têm n = 2).

| Tarefa | Taxa de sucesso | Tempo típico | Erros recorrentes | Satisfação | Meta atendida? | Problemas prioritários |
|---|---:|---|---|---|---|---|
| UT01 | {{x de 1}} | {{mm:ss}} | {{...}} | SEQ {{...}} | MU04, MQ01 (QA04): {{sim/não — indicativo}} | {{PU..}} |
| UT02 | {{x de 1}} | mediana por alerta {{mm:ss}}; retomada {{ss}} s | {{...}} | SEQ {{...}} | MU01, MU02, MU03, MU05, MU10, MQ02, MQ03 (QA01–03, QA05, QA06, QA09): {{...}} | {{...}} |
| UT03 | {{x de 2}} | {{...}} | {{...}} | SEQ {{...}} | MU06, MQ02, MQ04 (QA06): {{...}} | {{...}} |
| UT04 | {{x de 2}} | {{...}} | {{...}} | SEQ {{...}} | MQ05 (QA12): {{...}} | {{...}} |
| UT05 | {{x de 1}} | {{mm:ss}} | {{...}} | SEQ {{...}} | MU07, MU08, MQ06 (QA07, QA08): {{...}} | {{...}} |
| UT06 | {{x de 1}} | {{...}} | {{...}} | SEQ {{...}} | MQ07 (QA13): {{...}} | {{...}} |
| UT07 | {{x de 1}} | {{...}} | {{...}} | — | MQ08 (QA14): {{...}} | {{...}} |

**Regra de comparação com as metas da Entrega 08** (definida antes das sessões; todas as conclusões são indicativas):

| Meta (pergunta) | Limite (Entrega 08) | Como será calculada com os dados deste teste | Resultado |
|---|---|---|---|
| MU01 (QA01) | conclui sem ajuda (1 de 1) | U01 registra veredito nos três alertas de UT02 sem nenhuma ajuda? (x de 1) | {{...}} |
| MU02 (QA02) | ≥ 80% dos vereditos coerentes | Vereditos de U01 iguais ao gabarito ÷ 3 | {{x de 3}} |
| MU03 (QA03) | 0 erros críticos | U01 sem erro crítico em UT02? (x de 1) | {{...}} |
| MU04 (QA04) | mediana ≤ 30 s | Tempo de U01 em UT01, se a resposta estiver correta (resposta incorreta é relatada à parte) | {{...}} |
| MU05 (QA05) | mediana ≤ 3 min por alerta | Mediana dos três tempos por alerta de U01 (interrupção descontada) | {{...}} |
| MU06 (QA06) | ≥ 90% de respostas corretas | Acertos em UT03 (a) e (b) de U01 e U02 ÷ 4 | {{x de 4}} |
| MU07 (QA07) | decisão correta com motivo | Decisões de U02 em UT05 (v8 e candidato reprovado) corretas **e** com cenário + métrica citados ÷ 2 | {{x de 2}} |
| MU08 (QA08) | mediana ≤ 5 min | Tempo de U02 em UT05 | {{...}} |
| MU10 (QA09) | mediana ≤ 20 s | Tempo de retomada de U01 em UT02 | {{...}} |
| MU11 (QA10) | mediana SEQ ≥ 5,5 | Mediana do SEQ de cada participante sobre suas tarefas, e SEQ por tarefa | {{...}} |
| MU12 (QA11) | média SUS ≥ 68 | SUS de U01 e de U02 (pontuação padrão 0–100), relatados separadamente | {{...}} |
| MQ01–MQ08 (QA04, QA06, QA07, QA09, QA12–QA14) | evidência qualitativa da Entrega 08 | Para cada meta, se a evidência desejada foi observada e as falas que a sustentam ou contradizem (MQ01: UT01; MQ02: UT02/UT03; MQ03: UT02; MQ04: UT03; MQ05: UT04; MQ06: UT05; MQ07: UT06; MQ08: UT07) | {{...}} |

## E. Achados e recomendações

> **A preencher após as sessões.** Cada achado (AU) reúne um ou mais problemas de usabilidade observados (PU01, PU02…) — ver seção B, passo 7.

| ID | Achado | Evidência (quant. + qual.) | Impacto | Recomendação | Artefatos a revisar |
|---|---|---|---|---|---|
| AU01 | {{...}} (PU{{..}}) | {{x de n + fala/comportamento}} | {{severidade 0–4; meta e QA afetadas}} | {{...}} | {{MoLIC/Figma/signos/HTA...}} |

## F. Comparação com a avaliação heurística

> **A preencher após as sessões**, cruzando os problemas consolidados da Entrega 13 com os PU deste teste.

| Problema | Detectado na heurística? | Detectado por usuários? | O que aprendemos |
|---|---|---|---|
| {{...}} | {{sim/não}} | {{sim/não}} | {{...}} |

## G. Conclusão

A conclusão deve responder:

1. Quais metas de usabilidade foram atingidas?
2. Quais problemas foram recorrentes e com quais perfis/tarefas?
3. O que surpreendeu a equipe?
4. Quais mudanças são prioritárias?
5. Que limitações do teste impedem generalizações amplas?

> **A preencher após as sessões** (itens 1–4). Limitações já conhecidas antes da coleta, que a conclusão deverá retomar:
>
> - **Amostra mínima:** um participante por perfil (2 no total, igual ao número de integrantes). As metas da Entrega 08 foram ajustadas para um participante por perfil e servem como referência indicativa: um único desempenho não representa o perfil.
> - **Possível participante *proxy*:** um estudante sem prática em SOC ou em administração de plataforma não reproduz a pressão do plantão nem a responsabilidade pela produção.
> - **Simulação:** dados de laboratório congelados e ações sem efeito real; o teste não mede o efeito da latência real nem a confiança que surge quando a decisão tem consequência.
> - **Contexto:** sessão remota e agendada, sem o ruído, a iluminação e as interrupções espontâneas do SOC; a interrupção de UT02 é provocada e única.
> - **Sem *think aloud* contínuo:** preserva os tempos de MU04, MU05, MU08 e MU10, mas parte do raciocínio só é obtida na retrospectiva após a tarefa, sujeita a racionalização posterior.
> - **MQ08 com um leitor só:** a legibilidade do registro é julgada por U02, que tem o perfil de administradora e não de analista do turno seguinte.
> - **Escopo:** o teste avalia a interação; não diz nada sobre a acurácia do pipeline do TCC.

{{conclusão a preencher após as sessões}}

## Checklist

- [ ] Número de participantes finais atende ao enunciado.
- [ ] Participantes são representativos do público e não são membros da equipe.
- [ ] Se foram usados participantes proxy, a justificativa e a limitação estão explícitas.
- [ ] O teste avalia a interação; não confunde usabilidade do protótipo com desempenho técnico do TCC.
- [ ] Tarefas administrativas/analíticas usadas no teste são rastreáveis a objetivos e cenários.
- [ ] Há consentimento e anonimização.
- [ ] Foi realizado teste piloto.
- [ ] Tarefas têm critérios de sucesso definidos antes do teste.
- [ ] Moderadores não ensinaram o caminho durante a tarefa.
- [ ] Resultados estão separados por usuário e por tarefa.
- [ ] Foram registrados sucesso, erros, ajudas, tempo e satisfação quando aplicáveis.
- [ ] Conclusão combina evidência quantitativa e qualitativa.
- [ ] Achados geram recomendações e atualização da rastreabilidade.
