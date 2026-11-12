# Entrega 4 — Cenários de análise/problema

**Data:** 08/09/2026 · **Revisada em:** 12/11/2026   
**Status:** `🟩 concluída (revisada após feedback)`  
**Responsabilidade:** 1 solução completa por integrante

> **Revisão de 12/11/2026, a partir do [feedback da Entrega 04](../feedbaks/Feedback_Professor_Entrega04_Equipe21.md).** Mudanças em relação à versão de 08/09/2026:
>
> 1. **As questões cobrem os sete elementos.** Cada cenário tem agora uma questão para cada elemento característico: ambiente/contexto, atores, objetivos, planejamento, ações, eventos e avaliação. O elemento aparece numa coluna própria.
> 2. **Perguntas que repetiam o cenário inicial foram reformuladas.** Cada uma passou a perguntar pela lacuna específica que faltava no inicial.
> 3. **As respostas estão marcadas na narrativa** com o número da questão (`[Q1]`, `[Q2]`…). A Q5 antiga de C01 (encaminhamento e passagem de plantão), que ficara sem resposta, agora é respondida.
> 4. **C02 virou um episódio concreto.** Tem lugar, hora, origem do sinal, a mudança específica sob suspeita, a ordem das consultas, o resultado encontrado e a dificuldade de decidir. O título mudou de “Configurar pipeline e validar desempenho” para “Aumento de alertas depois de uma alteração do pipeline”.
> 5. **Os elementos extraídos vêm só do que está narrado.** O quadro foi refeito e agora considera atores apenas as pessoas.
> 6. **C01 e C02 se ligam no texto.** O chamado que Thiago abre em C01 é a notificação que Vanessa recebe em C02. C02 aprofunda a **investigação reativa**; uma troca planejada de modelo fica fora deste cenário. A linha R02 de `RASTREABILIDADE.md` foi alinhada.
>
> Detalhes de prática que nenhuma coleta confirmou continuam marcados como hipótese `[H]`.

## Objetivo da atividade

Descrever situações atuais em que o usuário tenta alcançar um objetivo e encontra dificuldades. O cenário de análise/problema deve tornar visível **o contexto, os atores, as ações e as rupturas**, sem antecipar a interface que será projetada. Como o TCC não previa interface, os cenários descrevem como o profissional lida **hoje** com alertas, logs e configurações do IDS; a interface da disciplina só aparece nos cenários de interação (Entrega 09).

**Os sete elementos usados nas questões:**

| Elemento | O que investiga |
|---|---|
| Ambiente/contexto | Onde, quando e em que condições a situação ocorre |
| Atores | As **pessoas** envolvidas e o papel de cada uma (sistemas e equipamentos são recursos, não atores) |
| Objetivos | O que a pessoa quer alcançar e o que fica fora da sua alçada |
| Planejamento | O que a pessoa **pensa em fazer** para atingir o objetivo, antes de agir |
| Ações | O que ela **efetivamente faz** |
| Eventos | Ocorrências externas ou respostas do ambiente que mudam a situação |
| Avaliação | Como ela interpreta a situação e os resultados obtidos |

## Cenário C01 — Alerta de tráfego anômalo durante operação

**Autor(a):** Lucas Kerr - 22.123.032-9   
**Persona(s) relacionada(s):** P01   
**Necessidade relacionada:** R01   
**Situação concreta da Entrega 1 relacionada:** H14 H20 H26   
**Hipóteses ainda presentes:** H14 H26 H30 H31

**Origem do cenário:** aprofunda a situação concreta da Entrega 1 (4.5, H14), em que Thiago percebe lentidão nos servidores Web durante o plantão noturno e não consegue decidir se é pico legítimo ou ataque.

### 1. Cenário inicial

Thiago, analista de SOC nível 2, está no plantão noturno escrevendo a análise de uma ocorrência anterior quando o IDS registra uma sequência de conexões classificadas como suspeitas a partir de um mesmo segmento de rede. Thiago abre o console e encontra milhares de linhas de log, misturando as classificações do modelo com o restante do tráfego. Ele não sabe se está diante de um pico legítimo de acessos ou de uma varredura/DoS. Para descobrir, alterna entre o console, consultas manuais e seus próprios scripts para reunir origem, destino, serviço e volume de cada conexão. Enquanto não consegue decidir, a lentidão continua e ele não sabe dizer à operação se alguém deve agir.

### 2. Questões de refinamento

Cada questão foi confrontada com o cenário inicial. A coluna “Lacuna” registra o que **ainda não** está no texto.

| # | Elemento | Questão | Lacuna no cenário inicial | Fonte/forma de obter resposta |
|---|---|---|---|---|
| Q1 | Ambiente/contexto | Em que estado fica a análise que Thiago estava escrevendo quando o alerta chega, e o que ele precisa para retomá-la depois? | O inicial diz **o que** ele fazia, mas não o efeito da interrupção nem o custo da retomada | Entrega 03, seção 3 (interrupções frequentes no SOC); jornada, etapas 1 e 7. Verificação na Entrega 07 |
| Q2 | Atores | Quem, além de Thiago, participa do episódio: quem cobra a resposta, quem executa uma contenção, quem recebe o caso no turno seguinte e quem responde pelo IDS? | O inicial cita só “a operação”, sem dizer quem é nem o que cada pessoa espera dele | Entrega 03 (P02 e contexto social); H18 |
| Q3 | Objetivos | Que decisão cabe a Thiago e o que fica fora da sua alçada? | O inicial sugere que ele precisa “resolver” a lentidão, o que contradiz o recorte (ele interpreta e encaminha; não contém) | Entrega 01, quadro “limite entre detectar, interpretar e conter” (2.4); Entrega 03, quadro “Onde termina a análise e onde começa a contenção” |
| Q4 | Planejamento | O que Thiago já sabe do ambiente e, com base nisso, o que decide verificar primeiro? | O inicial lista os dados que ele reúne (origem, destino, serviço, volume), mas não o que ele já conhece nem **por que** escolhe olhar o histórico e o comportamento habitual | Entrega 01 (4.3, H13, H30); jornada, etapa 3 |
| Q5 | Ações | O que Thiago faz para passar o caso adiante — à infraestrutura, à operação e ao próximo turno — quando não consegue chegar a uma conclusão? | O inicial termina na indecisão e não mostra nenhum encaminhamento nem registro | Entrega 03, jornada, etapas 5–7; H18 e H31 |
| Q6 | Eventos | Que acontecimentos durante a investigação mudam a situação ou aumentam a pressão sobre Thiago? | O inicial só registra que “a lentidão continua” | Entrega 03, seção 3; H29 |
| Q7 | Avaliação | Como Thiago interpreta o que encontrou, o que ele pensa sobre a confiabilidade do próprio IDS e quanto custa errar em cada direção? | O inicial diz que ele “não sabe”, mas não explica por que a informação reunida não basta nem o que pesa na decisão | Entrega 01, 4.4 (tabela de erros); H12, H27 |

### 3. Cenário refinado

O conteúdo novo aparece entre colchetes com o número da questão que responde: **[Qn: …]**. O restante é o texto do cenário inicial, preservado.

Thiago, analista de SOC nível 2, está no plantão noturno escrevendo a análise de uma ocorrência anterior quando, às 02h40, o IDS registra uma sequência de conexões classificadas como suspeitas a partir de um mesmo segmento de rede. **[Q1: a análise está pela metade. O que ele já concluiu está anotado em parte no chamado e em parte só na própria memória, e ele sabe que, se largar o texto agora, vai ter de reconstruir o raciocínio depois.]** **[Q3: o que cabe a Thiago não é resolver o problema na rede, e sim decidir se aquelas conexões correspondem a um incidente real. A decisão tem três saídas: descartar como falso positivo, confirmar como incidente e encaminhar, ou marcar como indefinido e continuar investigando. Bloquear ou isolar o segmento cabe ao plantonista de infraestrutura, a pedido dele.]**

**[Q4: Thiago sabe que aquele segmento atende o portal interno usado pelo atendimento e que o portal costuma ter picos no começo da manhã, não de madrugada. Por isso decide não começar pelo volume total: quer saber primeiro se as origens já tinham se comunicado antes com o portal e se o volume destoa do habitual daquele horário.]** Thiago abre o console e encontra milhares de linhas de log, misturando as classificações do modelo com o restante do tráfego. Ele não sabe se está diante de um pico legítimo de acessos ou de uma varredura/DoS. Para descobrir, alterna entre o console, consultas manuais e seus próprios scripts para reunir origem, destino, serviço e volume de cada conexão. **[Q4: o histórico de comunicação e o comportamento habitual não estão no console. Ele roda um script próprio que extrai do log as contagens dos últimos sete dias e consulta a captura de pacotes para ver o conteúdo de algumas conexões. Monta cada consulta à mão e guarda de cabeça o que já viu enquanto passa de uma ferramenta para outra `[H]`.]**

**[Q6: às 03h05, a supervisora do atendimento escreve no chat do SOC perguntando se pode reiniciar o servidor do portal, que continua lento. Pouco depois, o mesmo padrão de conexões aparece vindo de um segundo host do segmento.]** **[Q7: as contagens mostram que algumas origens nunca tinham falado com o portal, mas o volume por origem é baixo, mais parecido com tráfego de atualização automática do que com uma varredura. A classificação do IDS não diz o que a levou a marcar as conexões. Thiago também lembra que, nos últimos dias, o IDS tem marcado como suspeitas conexões que antes passavam como normais. Ele não sabe se o tráfego mudou ou se alguém alterou a configuração, e nada do que consulta indica qual modelo está ativo nem desde quando. O erro custa nos dois sentidos: se descartar uma varredura real, a atividade pode evoluir sem resposta; se pedir um bloqueio indevido, a infraestrutura pode cortar o tráfego legítimo do portal e parar o atendimento.]**

Enquanto não consegue decidir, a lentidão continua e ele não sabe dizer à operação se alguém deve agir. **[Q2, Q5: às 03h40, sem conseguir confirmar nem descartar, Thiago marca o caso como indefinido. Responde à supervisora que não reinicie o portal ainda e que nenhum bloqueio foi pedido. Avisa o plantonista de infraestrutura, por telefone, que pode precisar de uma ação no segmento e que vai mandar um chamado se confirmar. Abre também um chamado na fila da administração do IDS, dirigido a Vanessa, que só lerá de manhã: “o IDS está marcando como suspeitas conexões do segmento do portal que antes passavam; não consegui confirmar nenhuma; houve mudança no modelo ou nos parâmetros?”.]** **[Q5: às 06h50, escreve a passagem de plantão para a analista do turno da manhã. Lista os dois hosts, as contagens que levantou e a suspeita sobre o IDS. Os critérios que usou e as consultas que montou ficam fora da nota: estão nos scripts, no histórico do terminal e na cabeça dele `[H]`. A análise interrompida às 02h40 continua pela metade.]**

### 4. Elementos extraídos

O quadro lista apenas o que está narrado no cenário refinado.

| Elemento | Evidência no cenário |
|---|---|
| Ambiente/contexto | Plantão noturno no SOC, de 02h40 a 06h50. Uma análise anterior fica interrompida e pela metade. O portal do atendimento está lento durante toda a investigação. |
| Atores | Thiago (P01, analista SOC L2); supervisora do atendimento, que pergunta se pode reiniciar o portal; plantonista de infraestrutura, avisado por telefone; Vanessa (P02), destinatária do chamado sobre o IDS; analista do turno da manhã, que recebe a passagem de plantão. |
| Objetivos | Decidir se as conexões correspondem a um incidente real (três saídas: falso positivo, incidente, indefinido). Não interromper um serviço legítimo por engano. Deixar o caso compreensível para quem continua. Bloqueio e isolamento ficam fora da alçada de Thiago. |
| Planejamento | Começar pelo histórico de comunicação e pelo comportamento habitual, e não pelo volume total, porque sabe que o portal não costuma ter pico de madrugada. |
| Ações | Interromper a análise; abrir o console; rodar o script que extrai as contagens de sete dias; consultar a captura de pacotes; responder à supervisora; avisar o plantonista de infraestrutura; marcar o caso como indefinido; abrir chamado para a administração do IDS; escrever a passagem de plantão. |
| Eventos | Alerta do IDS às 02h40; pergunta da supervisora às 03h05; mesmo padrão vindo de um segundo host; lentidão contínua do portal. |
| Avaliação | Origens novas, mas com volume baixo, parecido com atualização automática. A classificação não diz o critério. Suspeita de mudança no IDS, sem como saber qual modelo está ativo. O erro custa nos dois sentidos. |
| Problemas/rupturas | Contexto disperso entre console, script, captura e memória. Impossível atribuir a mudança de comportamento ao tráfego ou à configuração. Critérios da decisão não entram no registro. Análise anterior não é retomada. |
| Consequências | Caso fica indefinido até o turno seguinte enquanto o portal segue lento. A passagem de plantão sai incompleta, o que torna Thiago um gargalo. A suspeita sobre o IDS chega a Vanessa sem dados que ela possa conferir. |

### 5. Implicações para as próximas entregas

- Decompor A02 (investigar uma conexão sinalizada) desde a chegada do alerta até o registro do caso, **incluindo a saída “indefinido”**, que neste cenário é a que de fato ocorre.
- Tratar **interrupção e retomada** como parte da tarefa, não como exceção; e tratar **encaminhamento e passagem de plantão** como subtarefas cujo produto é lido por outra pessoa.
- Verificar com analistas reais (Entrega 07): (a) quais ferramentas usam hoje e em que ordem; (b) se reunir histórico e comportamento habitual é de fato o ponto mais custoso; (c) se a saída do modelo basta para o julgamento; (d) como ficam sabendo hoje de uma mudança de configuração; (e) o que registram na passagem de plantão.
- **Ligação com C02:** o chamado aberto às 03h40 é o sinal que inicia o cenário de Vanessa. A análise de tarefas deve mapear **o que Thiago sabe e o que Vanessa precisa receber** quando a suspeita recai sobre o modelo.
- **Fora desta análise:** a execução da contenção, que ocorre fora do recorte.

## Cenário C02 — Aumento de alertas depois de uma alteração do pipeline

**Autor(a):** Marcela Nalesso - 22.222.011-3   
**Persona(s) relacionada(s):** P02   
**Necessidade relacionada:** R02   
**Situação concreta da Entrega 1 relacionada:** H05, H10, H18   
**Hipóteses ainda presentes:** H05, H10, H27, H31

**Origem do cenário:** aprofunda H05 (a administradora ajusta parâmetros e escolhe o modelo). O episódio começa pelo sinal que sai de C01. É uma **investigação reativa**: Vanessa reage a um sinal de problema. Uma troca de modelo planejada com antecedência não faz parte deste cenário.

### 1. Cenário inicial

Vanessa, administradora de infraestrutura e da plataforma de SOC, recebe uma notificação de que a rede vem apresentando mais alertas do que o habitual e que a qualidade das ocorrências detectadas mudou após a atualização dos parâmetros de monitoramento. Como responsável pelo pipeline de captura e pelo classificador ativo, ela precisa verificar se o algoritmo em uso continua adequado ao comportamento real da rede, se a carga de processamento está equilibrada e se a operação permanece estável. O problema é que essa validação não depende de um único dado: ela exige comparar indicativos de desempenho, histórico operacional e comportamento atual do tráfego para decidir se a alteração foi benéfica ou se o ambiente passou a produzir falso alarmes e ruído para a equipe. A decisão não é simplesmente técnica; ela impacta diretamente a confiabilidade da detecção e a qualidade do trabalho dos analistas que acompanham a rede.

### 2. Questões de refinamento

| # | Elemento | Questão | Lacuna no cenário inicial | Fonte/forma de obter resposta |
|---|---|---|---|---|
| Q1 | Ambiente/contexto | Onde Vanessa está, em que momento recebe o sinal e por qual canal ele chega? | O inicial diz que ela “recebe uma notificação”, sem dizer de onde, quando nem como | Entrega 03, ficha de P02 e seção 3; ligação com C01 |
| Q2 | Atores | Quem produziu o sinal, quem é afetado pela decisão e a quem Vanessa precisa responder? | O inicial cita “os analistas” de forma genérica e não identifica ninguém | Entrega 03 (P01, contexto social); C01; H18 |
| Q3 | Objetivos | Qual alteração específica está sob suspeita e o que exatamente Vanessa precisa decidir sobre ela? | O inicial fala em “atualização dos parâmetros” sem dizer qual nem quando | Entrega 01, H05; Entrega 08 (pipeline em dois estágios) |
| Q4 | Planejamento | Como Vanessa pretende distinguir uma mudança no tráfego de um problema na configuração, e por onde decide começar? | O inicial lista o que precisa ser comparado, mas não mostra como ela pensa a investigação | Entrega 03, ficha de P02; H10 |
| Q5 | Ações | O que ela consulta, em que ordem, e **que referência usa** para comparar? | O inicial repete que é preciso “comparar desempenho, histórico e tráfego”, mas não diz contra o quê | H05, H27; Entrega 07 (verificação) |
| Q6 | Eventos | Que acontecimentos externos aparecem durante a análise e complicam a interpretação? | Ausente no inicial | Entrega 03, seção 3; H18 |
| Q7 | Avaliação | Como ela interpreta o que encontrou, e o que **muda** em relação ao risco que já conhecia (falsos alarmes, ruído)? | O inicial já cita falsos alarmes e ruído. Faltam a perda de desempenho, o risco de deixar de sinalizar uma ameaça e o que impede a decisão | Entrega 01, H10; C01 |

### 3. Cenário refinado

O conteúdo novo aparece entre colchetes com o número da questão que responde: **[Qn: …]**. Os fatos do cenário inicial foram preservados.

Vanessa, administradora de infraestrutura e da plataforma de SOC, recebe uma notificação de que a rede vem apresentando mais alertas do que o habitual e que a qualidade das ocorrências detectadas mudou após a atualização dos parâmetros de monitoramento. **[Q1: é terça-feira, 08h10. Ela está na sala da equipe de infraestrutura, em outro andar, longe do SOC, e lê os e-mails antes da reunião das 9h.]** **[Q2, Q1: a notificação são duas mensagens. A primeira é o relatório diário automático do IDS: a madrugada teve cerca de três vezes mais alertas que a média da semana anterior. A segunda é o chamado que Thiago, analista do plantão noturno, abriu às 03h40 na fila da administração do IDS, perguntando se o modelo ou os parâmetros tinham mudado (cenário C01).]**

**[Q3: Vanessa sabe qual alteração está em jogo, porque foi ela quem a fez. Na sexta-feira à tarde, para reduzir a carga do equipamento embarcado, aumentou a janela de agregação do estágio 1, o detector que separa o tráfego anômalo antes da classificação. Precisa decidir se mantém o ajuste, se o corrige ou se volta à configuração anterior. O modelo do estágio 2 não foi trocado.]** Como responsável pelo pipeline de captura e pelo classificador ativo, ela precisa verificar se o algoritmo em uso continua adequado ao comportamento real da rede, se a carga de processamento está equilibrada e se a operação permanece estável.

**[Q4: ela pensa em duas explicações e quer separá-las antes de mexer em qualquer coisa. Se o tráfego mudou, os alertas teriam subido em todos os segmentos. Se o problema for o ajuste, a subida teria começado logo depois da alteração de sexta e se concentraria onde o tráfego é mais intermitente. Decide começar pelas datas: comparar a contagem diária de alertas antes e depois de sexta.]** O problema é que essa validação não depende de um único dado: ela exige comparar indicativos de desempenho, histórico operacional e comportamento atual do tráfego para decidir se a alteração foi benéfica ou se o ambiente passou a produzir falso alarmes e ruído para a equipe. **[Q5: Vanessa abre a planilha em que anota as mudanças do pipeline `[H]` e confirma a data e o valor anterior da janela. Em seguida, roda o script que exporta do log a contagem diária de alertas por segmento e cola o resultado na mesma planilha. Depois abre o painel de monitoramento do embarcado, onde vê que a carga caiu de cerca de 85% para 60%, como pretendia. Para saber se os alertas novos são reais, procura nos chamados do SOC quantos foram confirmados como incidente. Encontra o de Thiago, outros dois marcados como “indefinido” e nenhum confirmado. A única referência de desempenho do modelo que ela tem é a do conjunto de teste usado no treinamento, que não reflete o tráfego desta semana.]**

**[Q6: no meio da análise, um colega lembra no chat da equipe que o portal do atendimento recebeu uma nova versão na segunda-feira. A subida de alertas está concentrada justamente no segmento do portal. Às 08h45, a analista do turno da manhã pergunta se deve continuar tratando aqueles alertas como suspeitos.]**

A decisão não é simplesmente técnica; ela impacta diretamente a confiabilidade da detecção e a qualidade do trabalho dos analistas que acompanham a rede. **[Q7: Vanessa conclui que a subida começou no sábado, depois do seu ajuste. Mas a nova versão do portal na segunda também pode ter mudado o tráfego daquele segmento, e ela não consegue separar os dois efeitos com o que tem. O ganho de carga é real; o custo dele não está medido. Se reverter, perde a folga do embarcado justo quando o volume de tráfego cresce, e o desempenho da captura pode cair. Se mantiver, os analistas continuam gastando a madrugada com alertas que não se confirmam, e um ataque real pode passar despercebido no meio do ruído. Como os vereditos dos analistas não ficam registrados de um jeito que ela consiga contar, não sabe quantos dos alertas novos são falsos. Às 9h, ainda sem decisão, responde à analista da manhã que está investigando, e percebe que nem ela nem Thiago tinham como saber que a janela do estágio 1 tinha mudado na sexta.]**

### 4. Elementos extraídos

O quadro lista apenas o que está narrado no cenário refinado. Pipeline, embarcado, rede e IDS aparecem como **recursos**, não como atores.

| Elemento | Evidência no cenário |
|---|---|
| Ambiente/contexto | Terça-feira, de 08h10 a 9h, na sala da infraestrutura, longe do SOC. Uma alteração feita na sexta à tarde já está em produção há três dias. |
| Atores | Vanessa (P02); Thiago (P01), autor do chamado; colega de infraestrutura, que lembra a nova versão do portal; analista do turno da manhã, que pergunta como tratar os alertas. |
| Objetivos | Decidir se mantém, corrige ou reverte o aumento da janela de agregação do estágio 1, sem perder a redução de carga à toa e sem deixar os analistas expostos a ruído ou a ataques não sinalizados. |
| Planejamento | Separar “mudança no tráfego” de “problema no ajuste” antes de agir; começar pelas datas, comparando a contagem diária de alertas antes e depois de sexta. |
| Ações | Ler o relatório diário e o chamado; consultar a planilha de mudanças; exportar a contagem diária de alertas por segmento; abrir o painel de carga do embarcado; procurar nos chamados os alertas confirmados; responder à analista da manhã. |
| Eventos | Relatório com alertas três vezes acima da média; chamado de Thiago; aviso da nova versão do portal na segunda; pergunta da analista da manhã às 08h45. |
| Avaliação | A subida começou depois do ajuste, mas coincide com a nova versão do portal. O ganho de carga é real e o custo não está medido. Não há contagem de vereditos para dizer quantos alertas são falsos. A referência de desempenho disponível (conjunto de teste) não serve para o tráfego atual. |
| Recursos/informações | Relatório diário do IDS; chamados do SOC; planilha de mudanças `[H]`; script de exportação do log; painel de carga do embarcado; métricas do conjunto de teste do treinamento. |
| Problemas/rupturas | Informações espalhadas em cinco lugares. Falta uma linha de base do desempenho em produção. Vereditos dos analistas não são contáveis. Impossível isolar o efeito do ajuste do efeito da nova versão do portal. Os analistas não sabiam da alteração. |
| Consequências | Decisão adiada enquanto a madrugada seguinte se aproxima. Risco de reverter um ganho real ou de manter ruído e mascarar um ataque. Analistas continuam sem saber se devem confiar nos alertas do segmento. |

### 5. Implicações para as próximas entregas

- Modelar a tarefa de Vanessa (T01) **a partir do sinal recebido**, com as alternativas reais de decisão: manter, ajustar parâmetros, trocar o modelo e reverter. Considerar que “manter” também precisa ser registrado e comunicado.
- Tratar como problema de IHC a **ausência de referência de comparação** (linha de base em produção, antes/depois da alteração) e a **ausência de vereditos contáveis**, que ligam o trabalho de Thiago ao de Vanessa.
- Tratar a **comunicação da alteração aos analistas** como parte da tarefa (R03): neste cenário, ninguém no SOC sabia que a janela tinha mudado.
- Verificar com administradores reais (Entrega 07): onde registram mudanças; que referência usam para julgar uma alteração; como separam efeitos de tráfego e de configuração; como recebem o retorno dos analistas.
- **Fora desta análise:** o treinamento de modelos e a calibração técnica do algoritmo em si.

## Checklist

- [x] Há um cenário completo por integrante.
- [x] Cada cenário tem título, ator, objetivo, contexto e problema.
- [x] O cenário possui origem rastreável na Entrega 1 ou justifica claramente a inclusão de uma nova situação.
- [x] O texto descreve a situação atual, sem antecipar a solução.
- [x] Para TCC sem interface original, o cenário descreve uma prática humana plausível relacionada à contribuição técnica, e não “a falta de uma tela”.
- [x] Questões de refinamento acrescentam informação nova e cobrem os sete elementos.
- [x] O refinamento mostra claramente o que foi adicionado e qual questão cada trecho responde.
- [x] Cenários são diferentes o suficiente para cobrir objetivos/problemas relevantes.
- [x] Cada cenário está ligado a persona/necessidade na matriz de rastreabilidade.
